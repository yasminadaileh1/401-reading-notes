# API Server :space_invader:

## Express: Router Parameters :vertical_traffic_light:

- **Parameters** in routes is `app.get('/places/:city', function)`
- **middleware** on *any route* `app.get('/places/:city', getZip, function) `
-  **middleware** on *every request* `app.use(getZip)`

## Sub Documents in Mongoose :green_book:

Mongoose is a schema driven **Object Relation Mapping**(ORM), which gives us the opportunity to provide **structure** to our Mongo documents. By default, **MongoDB** are not structured by default. Mongoose takes some of that pain away from us as developers and **allows us to provide some level of rules and validation** around our data models.
Mongoose gives us the ability to take that a step further and **use a schema to describe a deeper part of a data model**. Also sharing a schema as a **sub-document** doesn’t bring in or connect the data, it simply uses the schema/rules. It’ll be up to us to **manage the actual data**. **Modeling** keeping things **separate** makes great sense, even if you have to keep a few tables in sync by hand.

**Sub-documents** example
```
var childSchema = new Schema({ name: 'string' });
var house = new Schema({ address: 'string', city: 'string', state: 'string' });

var adult = new Schema({
  // Array of subdocuments
  children: [childSchema],

  // Single nested subdocuments.
  address: house
});
```

## Joining Data/Documents in Mongo :busts_in_silhouette:

* `populate()` it's a method we can use in Mongoose to **connect 2 collections** :
 - Method 1: **physically** joining using a reference to another collection
 - Method 2: **Virtual** Population
    - Create a virtual field in a document pointed to a field in another one.
    - In `pre('find')` you do a collection “on the fly” which can be more efficient than storing the relation.

* **Pre and Post** hooks (middleware)
    - Mongoose allows you to **inject logic** at various points in the lifecycle of a data record
        - User can perform **validation**, **normalization**


#### Direct Population (References) :books:

Create a **reference column** in the collection and then when you `save`, you need to `push()` into the reference field with the **_id** of the referenced document. This results in quicker `find()` but requires a lot more management on `saves`, `updates`, `deletes`.

Example:
```
const personSchema = Schema({
  _id: Schema.Types.ObjectId,
  name: String,
  age: Number,
  stories: [{ type: Schema.Types.ObjectId, ref: 'Story' }]
});

const storySchema = Schema({
  author: { type: Schema.Types.ObjectId, ref: 'Person' },
  title: String,
  fans: [{ type: Schema.Types.ObjectId, ref: 'Person' }]
});
```

## Virtual Joins :computer:

As the records are being processed by Mongoose and can be quite slow
Example:
```
const teams = mongoose.Schema({
  name: { type:String, required:true },
}, { toObject:{virtuals:true}, toJSON:{virtuals:true} });

teams.virtual('players', {
  ref: 'players',
  localField: 'name',
  foreignField: 'team',
  justOne:false,
});

teams.pre('find', function() {
  this.populate('players');
});
```

### Additional Resources :pager:

**Bookmark / Skim** :star:

- [express router.param() middleware](https://expressjs.com/en/4x/api.html#router.param)
- [mongoose middleware](https://mongoosejs.com/docs/middleware.html)
- [mongoose sub-documents](https://mongoosejs.com/docs/subdocs.html)
- [mongoose virtual joins](https://mongoosejs.com/docs/populate.html#populate-virtuals)