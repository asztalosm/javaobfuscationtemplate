<title>Java obfuscator</title>
<style>
    :global(html){
        background-color: rgb(59, 59, 59);
        color: rgb(240, 240, 240)
    }

    #codeholder{
        text-align: left;
        min-height: 80%;
        height:20rem;
        background-color: rgb(42,42,42);
        border-color: rgb(30,30,30);
        margin: 1% 10%;
    }
    .buttonshit {
        text-align: center;
        margin: 0 auto;
        padding: 1%;
        background-color: rgb(42,42,42);
        border-color: rgb(30,30,30);
    }
    h1 {
        font-size: xx-large;
    }
</style>

<script>
    import "../app.css"
let originaljavacode = "null";
let newjavacode = originaljavacode;

let datatypes = ["int", "String", "char", "float", "double", "Scanner"];

function obfuscateVariableName() {
    firstchars = "$_ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz".split();

}

function loopvariables() {
    let lines = newjavacode.split('\n')
    for (let i = 0; i < lines.length; i++){
        console.log(lines[i]);
        if (lines[i] == "") { 
            lines.remove(i); //removes formatting code
        }
    }
}

function dogshittify() {
    let firstline = document.getElementById("codeholder").value.split("\n", 1)[0];
    console.log(firstline);
    if (firstline != "public class Main {") {
        alert("NO valid code submitted");
    } else {
        originaljavacode = document.getElementById("codeholder").value;
        newjavacode = originaljavacode;
    }
    //change variable names
    loopvariables();
}
</script>


<div class="appbg">
<h1 class="text-center">Java obfuscator</h1>
<p class="text-center">just makes your java code look like ass, why? class name should be Main, and don't include imported libraries, otherwise obfuscation won't work</p>
<textarea type="text" name="code" placeholder="Insert Java code to Dogshittify" id="codeholder" class="text-left w-10/12 border-gray-700 border-solid border-2 rounded-xl bg-gray-900"></textarea>
<center><button  type="button" on:click={dogshittify}  class="text-center buttonshit border-gray-900 border-2 rounded-xl">Doghittify 🚮</button></center>
</div>