
Basic example

```
const data = [
  ['firstname', 'lastname', 'email'] ,
  ['Ahmed', 'Tomi' , 'ah@smthing.co.com'] ,
  ['Raed', 'Labes' , 'rl@smthing.co.com'] ,
  ['Yezzi','Min l3b', 'ymin@cocococo.com']
];
<CSVLink data={data} >Click here to download CSV file</CSVLink>
```

Set **data props** as "Array of literal (json) objects" ;

```
const data = [
  {firstname: 'Ahmed', lastname: 'Tomi' , email: 'ah@smthing.co.com'},
  {firstname:'Raed', lastname:'Labes' , email:'rl@smthing.co.com'} ,
  {firstname:'Yezzi', lastname:'Min l3b', email:'ymin@cocococo.com'}
];
<CSVLink data={data} >Click here to download CSV file</CSVLink>
```

**Custom Headers** for "Array of literal (json) objects" :
```
const headers = [
  { label: 'First Name', key: 'firstname'},
  { label: 'Last Name', key: 'lastname'},
  { label: 'Email Address', key: 'email'},
];

const data = [
  {firstname: 'Ahmed', lastname: 'Tomi' , email: 'ah@smthing.co.com'},
  {firstname:'Raed', lastname:'Labes' , email:'rl@smthing.co.com'} ,
  {firstname:'Yezzi', lastname:'Min l3b', email:'ymin@cocococo.com'}
];
<CSVLink data={data} headers={headers}>Download with custom headers</CSVLink>
```

Add styling to your link via **style props** or **className props** :

```example

const prettyLink  = {
  backgroundColor: '#8dc63f',
  fontSize: 14,
  fontWeight: 500,
  height: 52,
  padding: '0 48px',
  borderRadius: 5,
  color: '#fff'
};
const data = [
  ['firstname', 'lastname', 'email'] ,
  ['Ahmed', 'Tomi' , 'ah@smthing.co.com'] ,
  ['Raed', 'Labes' , 'rl@smthing.co.com'] ,
  ['Yezzi','Min l3b', 'ymin@cocococo.com']
];

<span>
Download <CSVLink data={data} style={prettyLink}>CSV ⬇</CSVLink> to download CSV
</span>

```

Set the separator between cells  via **separator props**:
```example

const data = [
  ['firstname', 'lastname', 'email'] ,
  ['Ahmed', 'Tomi' , 'ah@smthing.co.com'] ,
  ['Raed', 'Labes' , 'rl@smthing.co.com'] ,
  ['Yezzi','Min l3b', 'ymin@cocococo.com']
];

<span>
Download <CSVLink data={data} separator={";"}>CSV ⬇</CSVLink>
</span>

```


Set the default **filename** of the downloaded CSV file :

```
const randomData = Array.from({length:10}, (v, k) =>
  Array.from({length:4}, (vv, kk) => Math.random().toString(36).substring(7))
);

// -----------------------Double click here👇🏼 to change the name (it is editable)
<CSVLink data={randomData} filename="another-name.csv">Download me with another name </CSVLink>
```

Add **headers**  :

```
//It is editable content : you can change code and see results on live.
const randomData = Array.from({length:10}, (v, k) =>
  Array.from({length:4}, (vv, kk) => Math.random().toString(36).substring(5))
);
const headers =['Rando-🍌', 'Rando-🍑', 'Rando-🌺', 'Rando-🍀'];

<CSVLink data={randomData} headers={headers}>Download with Headers </CSVLink>
```

**Kitchen Sink**  :

* Headers
* Custom Delimiter
* Data contains delimiter - which is replaced with a space
* Data contains new lines - which are stripped out

```
//It is editable content : you can change code and see results on live.
const headers =['First', 'Last', 'Contact'];

const data = [
  ['Dagny', 'Taggart' , 'dagny.taggart@example.com\r\ndirector.tt@example.com'] ,
  ['James', 'Taggart' , 'james.targgart@example.com'] ,
  ['Hank','Reardon', 'hank.reardon@example.com'],
  ['John','Galt', 'john.galt@example.com;atlas@example.com;prime-mover57@example.com']
];

<span>
Download <CSVLink data={data} headers={headers} separator={";"}>CSV ⬇</CSVLink>
</span>
```