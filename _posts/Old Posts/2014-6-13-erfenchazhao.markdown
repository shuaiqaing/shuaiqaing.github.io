---
layout: post
title:  "二分查找简单理解"
date:   2014-6-13 10:13:03 +0800
categories: jekyll update
---
<?php  

#二分查找  
function binarySearch(Array $arr, $target) {  

$low = 0;  
$high = count($arr) - 1;  

while($low <= $high) {  

$mid = floor(($low + $high) / 2);  
 #找到元素  
if($arr[$mid] == $target) return $mid;  
#中元素比目标大,查找左部  
if($arr[$mid] > $target) $high = $mid - 1;  
#重元素比目标小,查找右部  
if($arr[$mid] < $target) $low = $mid + 1;  

}  
  
#查找失败  
return false;  

}
 
$arr = array(1, 3, 5, 7, 9, 11);  
$inx = binarySearch($arr, 1);   
 var_dump($inx);   
?>

二分查找的基本思想是将n个元素分成大致相等的两部分，去a[n/2]与x做比较，如果x=a[n/2],则找到x,算法中止；如果x<a[n/2],则只要在数组a的左半部分继续搜索x,如果x>a[n/2],则只要在数组a的右半部搜索x.

时间复杂度无非就是while循环的次数！

总共有n个元素，

渐渐跟下去就是n,n/2,n/4,....n/2^k，其中k就是循环的次数

由于你n/2^k取整后>=1

即令n/2^k=1

可得k=log2n,（是以2为底，n的对数）

所以时间复杂度可以表示O()=O(logn)
