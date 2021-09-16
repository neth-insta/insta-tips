* Khmer word segmentation
```javascript
const segmenter = new Intl.Segmenter("km", {granularity: "word"});
const input = "រាត្រីសួរស្តីអ្នកទាំងអស់គ្នា";
const segments = segmenter.segment(input);

for(const {segment} of  segments){
    console.info(segment)
}
```

* English word segmentation
```javascript
const segmenter = new Intl.Segmenter("en", {granularity: "word"});
const input = "A Hello, World! program generally is a computer program that outputs or displays the message Hello, World!";
const segments = segmenter.segment(input);

for(const {segment} of  segments){
    console.info(segment)
}
```
