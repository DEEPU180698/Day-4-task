DAY 4 TASK

1.Comparing two JSONs

let obj1={name:"Deepu",age:25};
let obj2={age:25,name:"Deepu"};
//let op=true;
// for(let i in obj1){
//     if(obj1[i]!=obj2[i]){
//         op=false;
//         break;
//     }
// }
// op?console.log("equal"):console.log("not equal");


let keys1= Object.keys(obj1);
let keys2= Object.keys(obj2);
let op=true;
//console.log(keys1);
if(keys1.length===keys2.length){
for(let i of keys1){
    // console.log(keys1[i]);
    if(obj1[i]!=obj2[i]){
        op=false;
        break;   
    }
}
}
else{
    op=false;
}
op?console.log("equal"):console.log("not equal");

2.Displaying flag of all countries in console


<!DOCTYPE html>
<html>
    <head>
        <title>Day4 task2 </title>
    </head>
    <body>
        <h1>Hello</h1>
        <h2>xml http request</h2>
        <h3>Printing all Flags</h3>
        <script>
            function handleData(){
                let data = JSON.parse(this.responseText);
                for (let i=0;i<data.length;i++){
                    console.log(data[i].flag)
                }
            }
            const req = new XMLHttpRequest();
            req.addEventListener('load',handleData);
            // req.onload = (res)=>{
            //     console.log(JSON.parse(res.srcElement.responseText));
            // }
            req.open("GET","https://restcountries.com/v3.1/all");
            req.send();
        </script>
    </body>
</html>

3.Displaying name ,region, sub region and population of all countries

<!DOCTYPE html>
<html>
    <head>
        <title>Day4 task3 </title>
    </head>
    <body>
        <h1>Hello</h1>
        <h2>xml http request</h2>
        <h3>Printing all countries names ,<br> region ,<br> sub-region ,<br> populations</h3>
        <script>
            // function handleData(){
            //     let data = JSON.parse(this.responseText);
            //     for (let i=0;i<data.length;i++){
            //         console.log(data[i].name.common);
            //         console.log(data[i].region);
            //         console.log(data[i].subregion);
            //         console.log(data[i].population);
                    
            //     }
            //}
            const req = new XMLHttpRequest();
            //req.addEventListener('load',handleData);
            req.onload = (res)=>{
                let data = JSON.parse(res.srcElement.responseText);
                for (let i=0;i<data.length;i++){
                    console.log(data[i].name.common);
                    console.log(data[i].region);
                    console.log(data[i].subregion);
                    console.log(data[i].population);
                }
            }
            req.open("GET","https://restcountries.com/v3.1/all");
            req.send();
        </script>
    </body>
</html>

