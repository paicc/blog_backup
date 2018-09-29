---
title: 面試考題-C語言
date: 2018-09-29 16:08:16
tags:
---

最近經歷了殘酷的疲勞面試，從中學習了很多，不管是表達方面還是個人機處方面都有所進步。其中，在面試不乏各式的考題包含C語言、作業系統概念和計組。就幫自己做個紀錄也順便分享一下，等之後有公司了再分享面試心得。

## C語言考題
### 指標

1.  The content of array a?
```
int a[ ]={6,7,8,9,10};
int *p= a;
*(p++) +=123;
*(++p) +=123;
```

2. 請問輸出為何?
```
char i[ ] = “Hello”;
char *p = 1;
int n = 10;
printf(“%d %d %d”, sizeof(i), sizeof(p), 		sizeof(n));
```

3. 請問輸出為何?
```
int main(){
	int a[] ={1,2,3,4,5,6};
	int *ptr = (int*) (&a+1);
	printf("%d", *(ptr-1));
}
```

4. 請問輸出為何?
```
int main(){
	int arr[] = {10,20,30,40,50};
	int *ptr1 = arr;
	int *ptr2 = arr + 5;
	printf("%d", (ptr2-ptr1));
	printf("%d", (char*)ptr2 - (char*)ptr1);
}
```

5. 請問輸出為何?
```
int main(){
	int arr1[] = {10,20};
	int arr2[] = {10,20};
	int arr3[] = {10,20};
	int *p = arr1;
	int *q = arr2;
	int *r = arr3;
	++*p;
	*q++;
	*++r;
	printf("%d %d %d", arr1[0], arr1[1], *p);
	printf("%d %d %d", arr2[0], arr2[1], *q);
	printf("%d %d %d", arr3[0], arr3[1], *r);
}
```

6. 請問輸出為何?
```
void f(int *p, int *q){
	p = q;
	*p = 2;
}

int i=0, j=1;
int main(){
	f(&i, &j);
	printf("%d %d\n", i, j);
}
```

7. 請問輸出為何?
```
int main(){
	char s[ ]="0113256";
	char *p = s;
	
	printf("%c", *p++);
	printf("%c", *(p++));
	printf("%c", (*p)++);
	printf("%c", *++p);
	printf("%c", *(++p));
	printf("%c", ++*p);
	printf("%c", ++(*p));
	printf("\n");
	printf("%s",s);
}
```

8. 請問輸出為何?
```
int main(){
	int ref[]={8,4,0,2};
	int *ptr;
	int index;
	for(index=0, ptr=ref; index<2; index++,ptr++)
		printf("%d %d\n", ref[index], *ptr);
	(*ptr++);
	printf("%d %d\n", ref[index], *ptr);
}
```

### 陣列

1.  請問輸出為何?
```
ine main() {
	char *str[ ][2] =
		{ "professor", "Justin" ,
		  "teacher", "Momor" ,
		  "student", "Caterpillar"};

	char str2[3][10] = {"professor", "Justin", "etc"};
	printf("%s\n", str[1][1]);
	printf("%c\n",str2[1][1]);
}
```

2. what is final value of cnt?
```
int cnt = 10;
const char *pc = "welcome";
while(*pc++)
	cnt++;
```

### 實作題

1.  Write a function that can calculate?  
    `1*2 + 2**3 + …… + (n-1)*n`
    
2.  寫一個string compare的function。相同return 0，不同return 1
    
3.  寫一個sort演算法
    
4.  在一個數值中計算幾個bit為1
    
5.  將一個數值的奇偶bit互換
    
6.  將一個字串reverse
    
7.  給一個連續數列，找出連續最長的1bit
    

### 其他

1.  請問輸出為何？
```
sizeof(byte)? sizeof(float)? sizeof(int)? sizeof(short)? sizeof(short)?
```

2. 請問輸出為何?
```
#include <stdio.h>

union StateMachine {
    char character;
    int number;
    char *str;};

int main(void) {
    union StateMachine machine;
    machine.number = 1;

    printf("sizeof: %lu\n", sizeof(machine));
    printf("number: %d\n", machine.number);
}
```

3.  Write a function which can return the bit content form.  
    給一個整數變數a  
    (1)設置a的bit3  
    (2)清除a的bit3
    
4.  請問v為何?
```
unsign long v1 = 0x00001111;
unsign long v2 = 0x00001202;
unsign long v;
v = v1 & (~v2);
v = v1 | v2;
```
