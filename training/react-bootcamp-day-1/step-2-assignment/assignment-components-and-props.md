---
description: >-
  Sebelum kalian mengerjakan assignment alangkah baiknya kalian untuk
  mempelajari tentang components & props
---

# Assignment - Components & Props

Tapi...... jika kalian sudah mempelajarinya yukk .. kalian bisa langsung check assignment nya .... Selamat Mengerjakan :\)

## **Question 1**

Jelaskan konsep dari Component dan Props dengan bahasa Anda sendiri !

## **Question 2**

Jelaskan secara detail maksud dari “Props itu _read-only_”!

## **Question 3**

Gunakan metoda _compose component_ untuk component Welcome ke component App di dalam div.

```text
function Welcome(props) {
 return <h1>Hello, {props.name}</h1>;
}
 
function App() {
 return (
   <div>
    
   </div>
 );
}
 
ReactDOM.render(
 <App />,
 document.getElementById('root')
);
```

## **Question 4**

Gunakan metoda _extracting component_ untuk component yang di-_wrap_ oleh elemen div UserInfo, dengan props author dari data props.author dari component Comment.

```text
function Comment(props) {
 return (
   <div className="Comment">
     <div className="UserInfo">
       <img className="Avatar"
         src={props.author.avatarUrl}
         alt={props.author.name}
       />
       <div className="UserInfo-name">
         {props.author.name}
       </div>
     </div>
     <div className="Comment-text">
       {props.text}
     </div>
     <div className="Comment-date">
       {formatDate(props.date)}
     </div>
   </div>
 );
}
```

## **Question 5**

Apa yang salah dari component di bawah ini ? Jelaskan apa yang terjadi! Dan bagaimana cara solvingnya jika error ?

```text
function Comment(props) {
 return (
     <div className="UserInfo">
       <img className="Avatar"
         src={props.author.avatarUrl}
         alt={props.author.name}
       />
       <div className="UserInfo-name">
         {props.author.name}
       </div>
     </div>
     <div className="Comment-text">
       {props.text}
     </div>
     <div className="Comment-date">
       {formatDate(props.date)}
     </div>
 );
}
```

