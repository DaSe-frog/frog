<?php
$dir = "../img/random"; 
$img_a = array(); 

if (is_dir($dir)){  
	if($od = opendir($dir)){ 
		while(($file = readdir($od)) !== false){ 
			if(strtolower(strstr($file, "."))===".jpg" || strtolower(strstr($file, "."))===".gif" || strtolower(strstr($file, "."))===".png"){ 
				array_push($img_a, $file);
			}
		}
		closedir($od); 
	}
}

$rd = rand(0, count($img_a)-1); 
print '<img src=' . $dir.$img_a[$rd] . ' weidth="900px" height="650px"> '
?>