const mongoose  = require("mongoose");
const { stringify } = require("querystring");
const Schema = mongoose.Schema;

const listingSchema = new Schema({
 title : {
    type :String,
    required : true,
 },
 description : String,
 image: {
   type : String,
   default:
       "https://unsplash.com/photos/a-person-swimming-in-the-ocean-with-a-camera-NhWxAIs61MM",
   
 set : (v) =>
 v=== ""
 ? "https://unsplash.com/photos/a-person-swimming-in-the-ocean-with-a-camera-NhWxAIs61MM"
: v,
},

 price : Number,
 country : String,
 location : String,
});

const Listing = mongoose.model ("Listing", listingSchema);
 module.exports = Listing;# delta-pro
