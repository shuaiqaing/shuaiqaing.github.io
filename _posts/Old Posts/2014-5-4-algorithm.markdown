---
layout: post
title:  "算法整理"
date:   2014-3-26 11:15:53 +0800
categories: jekyll update
---
<br>
1、冒泡排序   
2、归并排序   
3、二分查找-递归   
4、二分查找-非递归   
5、快速排序   
6、选择排序   
7、插入排序   
下面一一示例介绍      
<? 

//1、冒泡排序    
function bubble_sort($arr) {   
    $n=count($arr);   
    for($i=0;$i<$n-1;$i++){   
        for($j=$i+1;$j<$n;$j++) {   
            if($arr[$j]<$arr[$i]) {   
                $temp=$arr[$i];   
                $arr[$i]=$arr[$j];   
                $arr[$j]=$temp;   
            }   
        }   
    }   
    return $arr;   
}      
   
//2、归并排序    
function Merge(&$arr, $left, $mid, $right) {   
  $i = $left;   
  $j = $mid + 1;   
  $k = 0;   
  $temp = array();   
  while ($i <= $mid && $j <= $right)   
  {   
    if ($arr[$i] <= $arr[$j])   
      $temp[$k++] = $arr[$i++];   
    else   
      $temp[$k++] = $arr[$j++];   
  }   
  while ($i <= $mid)   
    $temp[$k++] = $arr[$i++];   
  while ($j <= $right)   
    $temp[$k++] = $arr[$j++];   
  for ($i = $left, $j = 0; $i <= $right; $i++, $j++)   
    $arr[$i] = $temp[$j];   
}   
    
function MergeSort(&$arr, $left, $right)   
{   
  if ($left < $right)   
  {   
    $mid = floor(($left + $right) / 2);   
    MergeSort($arr, $left, $mid);   
    MergeSort($arr, $mid + 1, $right);   
    Merge($arr, $left, $mid, $right);   
  }   
}   
   
//3、二分查找-递归 
function bin_search($arr,$low,$high,$value) {
    if($low>$high)
        return false;
    else {
        $mid=floor(($low+$high)/2);
        if($value==$arr[$mid])
            return $mid;
        elseif($value<$arr[$mid])
            return bin_search($arr,$low,$mid-1,$value);
        else
            return bin_search($arr,$mid+1,$high,$value);
    }
}



//4、二分查找-非递归 
function bin_search($arr,$low,$high,$value) {
    while($low<=$high) {
        $mid=floor(($low+$high)/2);
        if($value==$arr[$mid])
            return $mid;
        elseif($value<$arr[$mid])
            $high=$mid-1;
        else
            $low=$mid+1;
    }
    return false;
}

//5、快速排序 
function quick_sort($arr) {
    $n=count($arr);
    if($n<=1)
        return $arr;
    $key=$arr[0];
    $left_arr=array();
    $right_arr=array();
    for($i=1;$i<$n;$i++) {
        if($arr[$i]<=$key)
            $left_arr[]=$arr[$i];
        else
            $right_arr[]=$arr[$i];
    }
    $left_arr=quick_sort($left_arr);
    $right_arr=quick_sort($right_arr);
    return array_merge($left_arr,array($key),$right_arr);
}

//6、选择排序 
function select_sort($arr) {
    $n=count($arr);
    for($i=0;$i<$n;$i++) {
        $k=$i;
        for($j=$i+1;$j<$n;$j++) {
           if($arr[$j]<$arr[$k])
               $k=$j;
        }
        if($k!=$i) {
            $temp=$arr[$i];
            $arr[$i]=$arr[$k];
            $arr[$k]=$temp;
        }
    }
    return $arr;
}

//7、插入排序 
function insertSort($arr) {
    $n=count($arr);
    for($i=1;$i<$n;$i++) {
        $tmp=$arr[$i];
        $j=$i-1;
        while($arr[$j]>$tmp) {
            $arr[$j+1]=$arr[$j];
            $arr[$j]=$tmp;
            $j--;
            if($j<0)
                break;
        }
    }
    return $arr;
}

//-------------------- 
// 基本数据结构算法
//-------------------- 
//顺序查找（数组里查找某个元素） 
function  seq_sch($array, $n,  $k){  
    $array[$n] =  $k;  
    for($i=0;  $i<$n; $i++){  
        if( $array[$i]==$k){  
            break;  
        }  
    }  
    if ($i<$n){  
        return  $i;  
    }else{  
        return -1;  
    }  
}  
//线性表的删除（数组中实现） 
function delete_array_element($array , $i) 
{ 
        $len =  count($array);  
        for ($j= $i; $j<$len; $j ++){ 
                $array[$j] = $array [$j+1]; 
        } 
        array_pop ($array); 
        return $array ; 
}  
//------------------------ 
// PHP内置字符串函数实现 
//------------------------ 
//字符串长度 
function strlen ($str) 
{ 
        if ($str == '' ) return 0; 
        $count =  0; 
        while (1){ 
                if ( $str[$count] != NULL){ 
                         $count++; 
                        continue; 
                }else{ 
                        break; 
                } 
        } 
        return $count; 
} 
//截取子串 
function substr($str, $start,  $length=NULL) 
{ 
        if ($str== '' || $start>strlen($str )) return; 
        if (($length!=NULL) && ( $start>0) && ($length> strlen($str)-$start)) return; 
        if (( $length!=NULL) && ($start< 0) && ($length>strlen($str )+$start)) return; 
        if ($length ==  NULL) $length = (strlen($str ) - $start); 

        if ($start <  0){ 
                for ($i=(strlen( $str)+$start); $i<(strlen ($str)+$start+$length ); $i++) { 
                        $substr .=  $str[$i]; 
                } 
        } 
        if ($length  > 0){ 
                for ($i= $start; $i<($start+$length ); $i++) { 
                        $substr  .= $str[$i]; 
                } 
        } 
        if ( $length < 0){ 
                for ($i =$start; $i<(strlen( $str)+$length); $i++) { 
                        $substr .= $str[$i ]; 
                } 
        } 
        return $substr; 
} 
//字符串翻转 
function strrev($str) 
{ 
        if ($str == '') return 0 ; 
        for ($i=(strlen($str)- 1); $i>=0; $i --){ 
                $rev_str .= $str[$i ]; 
        } 
        return $rev_str; 
} 

//字符串比较 
function strcmp($s1,  $s2) 
{ 
        if (strlen($s1) <  strlen($s2)) return -1 ; 
        if (strlen($s1) > strlen( $s2)) return 1; 
        for ($i =0; $i<strlen($s1 ); $i++){ 
                if ($s1[ $i] == $s2[$i]){ 
                        continue; 
                }else{ 
                        return false; 
                } 
        } 
        return  0; 
} 

//查找字符串 
function  strstr($str, $substr) 
{ 
         $m = strlen($str); 
        $n = strlen($substr ); 
        if ($m < $n) return false ; 
        for ($i=0; $i <=($m-$n+1); $i ++){ 
                $sub = substr( $str, $i, $n); 
                if ( strcmp($sub, $substr) ==  0)  return $i; 
        } 
        return false ; 
} 
//字符串替换 
function str_replace($substr , $newsubstr, $str) 
{ 
         $m = strlen($str); 
        $n = strlen($substr ); 
        $x = strlen($newsubstr ); 
        if (strchr($str, $substr ) == false) return false; 
        for ( $i=0; $i<=($m- $n+1); $i++){ 
                 $i = strchr($str,  $substr); 
                $str = str_delete ($str, $i, $n); 
                $str = str_insert($str,  $i, $newstr); 
        } 
        return $str ; 
} 

//-------------------- 
// 自实现字符串处理函数
//-------------------- 
//插入一段字符串 
function str_insert($str, $i , $substr) 
{ 
        for($j=0 ; $j<$i; $j ++){ 
                $startstr .= $str[$j ]; 
        } 
        for ($j=$i; $j <strlen($str); $j ++){ 
                $laststr .= $str[$j ]; 
        } 
        $str = ($startstr . $substr  . $laststr); 
        return $str ; 
} 
//删除一段字符串 
function str_delete($str , $i, $j) 
{ 
        for ( $c=0; $c<$i;  $c++){ 
                $startstr .= $str [$c]; 
        } 
        for ($c=( $i+$j); $c<strlen ($str); $c++){ 
                $laststr  .= $str[$c]; 
        } 
         $str = ($startstr . $laststr ); 
        return $str; 
} 
//复制字符串 
function strcpy($s1, $s2 ) 
{ 
        if (strlen($s1)==NULL || !isset( $s2)) return; 
        for ($i=0 ; $i<strlen($s1);  $i++){ 
                $s2[] = $s1 [$i]; 
        } 
        return $s2; 
} 
//连接字符串 
function strcat($s1 , $s2) 
{ 
        if (!isset($s1) || !isset( $s2)) return; 
        $newstr = $s1 ; 
        for($i=0; $i <count($s); $i ++){ 
                $newstr .= $st[$i ]; 
        } 
        return $newsstr; 
} 
//简单编码函数（与php_decode函数对应） 
function php_encode($str) 
{ 
        if ( $str=='' && strlen( $str)>128) return false; 
        for( $i=0; $i<strlen ($str); $i++){ 
                 $c = ord($str[$i ]); 
                if ($c>31 && $c <107) $c += 20 ; 
                if ($c>106 && $c <127) $c -= 75 ; 
                $word = chr($c ); 
                $s .= $word; 
        }  
        return $s;  
} 
//简单解码函数（与php_encode函数对应） 
function php_decode($str) 
{ 
        if ( $str=='' && strlen($str )>128) return false; 
        for( $i=0; $i<strlen ($str); $i++){ 
                $c  = ord($word); 
                if ( $c>106 && $c<127 ) $c = $c-20; 
                if ($c>31 && $c< 107) $c = $c+75 ; 
                $word = chr( $c); 
                $s .= $word ; 
        }  
        return $s;  
} 
//简单加密函数（与php_decrypt函数对应） 
function php_encrypt($str) 
{ 
         $encrypt_key = 'abcdefghijklmnopqrstuvwxyz1234567890'; 
         $decrypt_key = 'ngzqtcobmuhelkpdawxfyivrsj2468021359'; 
        if ( strlen($str) == 0) return  false; 
        for ($i=0;  $i<strlen($str); $i ++){ 
                for ($j=0; $j <strlen($encrypt_key); $j ++){ 
                        if ($str[$i] == $encrypt_key [$j]){ 
                                $enstr .=  $decrypt_key[$j]; 
                                break; 
                        } 
                } 
        } 
        return $enstr; 
} 
//简单解密函数（与php_encrypt函数对应） 
function php_decrypt($str) 
{ 
         $encrypt_key = 'abcdefghijklmnopqrstuvwxyz1234567890'; 
         $decrypt_key = 'ngzqtcobmuhelkpdawxfyivrsj2468021359'; 
        if ( strlen($str) == 0) return  false; 
        for ($i=0;  $i<strlen($str); $i ++){ 
                for ($j=0; $j <strlen($decrypt_key); $j ++){ 
                        if ($str[$i] == $decrypt_key [$j]){ 
                                $enstr .=  $encrypt_key[$j]; 
                                break; 
                        } 
                } 
        } 
        return $enstr; 
} 
?> 
