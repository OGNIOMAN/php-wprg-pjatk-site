<template>
    <div>
        <pre><code class="language-php">
$a = 5;
$b = 3;
$c = 6;
$temp = 0;
if ($a > $c){
    $temp = $a;
    $a = $c;
    $c = $temp;
}
if ($a > $b){
    $temp = $a;
    $a = $b;
    $b = $temp;
}
if ($b > $c){
    $temp = $b;
    $b = $c;
    $c = $temp;
}

if ($a$a+$b$b==$c*$c){
    echo "Jest to pitagoras";
}else{
    echo "Nie jest to pitagoras";
}
echo "$a $b $c";
        </code></pre>
    </div>
</template>
        <script src="https://gist.github.com/OGNIOMAN/4150a744dc5b71401c9e2bb8668888d3.js"></script>
<script>
import Prism from 'prismjs'

import 'prismjs/components/prism-bash'
import 'prismjs/components/prism-javascript'
import 'prismjs/components/prism-json'
import 'prismjs/components/prism-liquid'
import 'prismjs/components/prism-markdown'
import 'prismjs/components/prism-markup-templating'
import 'prismjs/components/prism-php'
import 'prismjs/components/prism-scss'
import 'prismjs/themes/prism-okaidia.css'

export default {
mounted(){
Prism.highlightAll()
},
data: () => ({

    
    code: `<?php
$a = 5;
$b = 3;
$c = 6;
$temp = 0;
if ($a > $c){
    $temp = $a;
    $a = $c;
    $c = $temp;
}
if ($a > $b){
    $temp = $a;
    $a = $b;
    $b = $temp;
}
if ($b > $c){
    $temp = $b;
    $b = $c;
    $c = $temp;
}

if ($a$a+$b$b==$c*$c){
    echo "Jest to pitagoras";
}else{
    echo "Nie jest to pitagoras";
}
echo "$a $b $c";`
    })
}
</script>
<style scoped>
.token.variable {
	color: #e90;
}
</style>