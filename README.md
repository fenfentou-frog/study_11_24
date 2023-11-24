#define _CRT_SECURE_NO_WARNINGS 1
//=============================函数
//#include <stdio.h>
//#include <string.h>
//int ADD(int x,int y)
//{
//	int z = 0;
//	z = x + y;
//	return z;
//}
//int main()
//{
//	int a = 10;
//	int b = 20;
//	int sum = ADD(a,b);
//	printf("%d\n",sum);
//	return 0;
//}
//#include <stdio.h>
//#include <string.h>
//int main()
//{
//	//strlen - string length- 跟字符串长度有关的函数
//	//strcpy - string copy - 字符串拷贝
//	char arr1[] = "bit";
//	char arr2[20] = "#############";
//	//arr1 = bit\0
//	strcpy(arr2,arr1);//因为bit的\0也被拷贝过去了(\0为字符串的结束标志)，因此\0之后的#不显示
//	printf("%s\n",arr2);
//	return 0;
//}
//memset
//memory：内存，set:设置
//#include <stdio.h>
//#include <string.h>
//int main()
//{
//	char arr[] = "hello xixixi";
//	memset(arr,23,4);
//	printf("%s\n",arr);
//	return 0;
//}
//==========水仙花数(过于繁琐)
//int main()
//{
//	int a = 0;//个位
//	int b = 0;//十位
//	int c = 0;//百位
//	int d = 0;
//	int e = 0;
//	int i = 1;
//	for(a=0;a<=9;a++)
//	{
//		for(b=0;b<=9;b++)
//		{
//			for(c=0;c<=9;c++)
//			{
//				d = a*1+b*10+c*100;
//				e = a*a*a+b*b*b+c*c*c;
//				if(e==d)
//				{
//					printf("%d==========\n", e);
//				}
//				//else
//				//{
//				//	i++;
//				//	printf("%d%d%d|==%d\n",a,b,c,e);
//				//}
//			}
//		}
//	}
//	return 0;
//}
//int get_max(int x,int y)
//{
//	if(x>y)
//	{
//		return x;
//	}
//	else
//	{
//		return y;
//	}
//}
//int main()
//{
//	int a = 0;
//	int b = 0;
//	int z = 0;
//	printf("请输入a:");
//	scanf("%d",&a);
//	printf("请输入b:");
//	scanf("%d",&b);
//	z = get_max(a,b);
//	printf("最大值为：%d\n",z);
//	return 0;
//}
//写一个函数可以交换两个整形变量的内容
//void change1(int x,int y)//int是有返回值的函数，void是没有返回值的函数
//{
//	int tmp = 0;
//	tmp = x;
//	x = y;
//	y = tmp;
//}
//int main()
//{
//	int a = 10;
//	int b = 20;
//	printf("a=%d,b=%d\n",a,b);
//	change1(a,b);//change1有问题
//	printf("a=%d,b=%d\n",x,y);
//	return 0;
//}
//int main()
//{
//	int a = 10;
//	int* pa = &a;//pa为指针变量
//	*pa = 20;//解引用操作
//	printf("%d\n",a);
//	return 0;
//}
//#include <stdio.h>
//#include <string.h>
//void change2(int* pa,int* pb)//int是有返回值的函数，void是没有返回值的函数
//{
//	int tmp = 0;
//	tmp = *pa;
//	*pa = *pb;
//	*pb = tmp;
//}
////change2就是直接交换地址，
//int main()
//{
//	int a = 10;
//	int b = 20;
//	printf("a=%d,b=%d\n",a,b);
//  //调用change2函数
//	change2(&a,&b);//change1有问题
//	printf("a=%d,b=%d\n",a,b);
//	return 0;
//}
//函数的参数
//实际参数（实参）
//形式参数（形参）:形式参数只在函数内部使用，出了函数就自动销毁
//当实参传给形参时，形参其实是实参的临时拷贝，实参和形参都具有独立空间
//对形参的修改是不会改变实参的；
//#include <stdio.h>
//#include <string.h>
//#include <math.h>
//int sushu(int x)//是素数返回1，不是素数返回0
//{
//	//产生2到x-1的数
//	int y = 0;
//	for(y=2;y<=sqrt(x);y++)
//	{
//		if(x%2==0)
//		{
//			return 0;
//		}
//		if(x%y==0)
//		{
//			return 0;
//		}
//	}
//	return 1;
//}
//int main()
//{
//	int a = 0;
//	int i = 0;
//	for(i=100;i<=200;i++)
//	{
//		if(sushu(i) == 1)
//		{
//			printf("%d是素数\n",i);
//		}	
//	}
//}
//#include <stdio.h>
//#include <string.h>
//#include <math.h>
//int run_nian(int x)//
//{
//	if(x%4==0 && x%100!=0)
//	{
//		return 0;
//	}
//	else if(x%400==0)
//	{
//		return 0;
//	}
//	else
//	{
//		return 1;
//	}
//}
//int main()
//{
//	int i = 0;
//	int y = 0;
//	for(i=1000;i<=2000;i++)
//	{
//		if(run_nian(i)==0)
//		{
//			printf("%d是闰年\n",i);
//			y++;
//		}
//	}
//	printf("y=%d\n",y);
//	return 0;
//}
//==========================================函数实现二分查找
//#include <stdio.h>
//#include <string.h>
//#include <math.h>
//        //本质上这里的int arr是一个指针，传了首元素的地址
//int half_find(int arr[],int k,int sz)
//{
//	int left = 0;
//	int right = sz-1;
//	while(left<=right)//左右交错了，左右之间没有元素了，就跳出循环
//	{
//		int mid = (left+right)/2;//中间元素的下标
//		if(arr[mid]<k)
//		{
//			left=mid+1;
//		}
//		else if(arr[mid]>k)
//		{
//			right=mid-1;
//		}
//		else
//		{
//			return mid;
//		}
//	}
//	return -1;
//}
//int main()
//{
//	//二分查找
//	//在一个有序数组中查找具体的某个数
//	//如果找到了返回下标，找不到返回-1；
//	int arr[] = {1,2,3,4,5,6,7,8,9,10};
//	int k = 1;
//	int sz = sizeof(arr)/sizeof(arr[0]);
//	                     //本质上这里的int arr是一个指针，传了首元素的地址
//	int ret = half_find(arr,k,sz);
//	if(ret == -1)
//	{
//		printf("找不到\n");
//	}
//	else
//	{
//		printf("找到了，下标是：%d",ret);
//	}
//	return 0;
//}
//#include <stdio.h>
//#include <string.h>
//#include <math.h>
//void Add(int* p)
//{
//	//*p++;====++的优先级在*前面
//	(*p)++;
//}
//int main()
//{
//	int a = 0;
//	int b = 0;
//	int num = 0;
//	Add(&num);
//	printf("%d\n",num);
//	Add(&num);
//	printf("%d\n",num);
//	Add(&num);
//	printf("%d\n",num);
//	return 0;
//}
//#include <stdio.h>
//#include <string.h>
//#include <math.h>
//int main()
//{
//	int len = 0;
//	//1
//	len = strlen("abc");
//	printf("%d\n",len);
//	//2
//	printf("%d\n",strlen("abc"));
//	return 0;
//}
//int main()
//{
//	printf("%d\n",printf("%d\n",printf("%d\n",43)));
//	//printf返回值为字符个数
//	return 0;
//}
//函数的声明和定义
//#include <stdio.h>
//#include <string.h>
//#include <math.h>
//函数声明
//int Add(int x,int y);//当不存在同一个文件中时
//函数的定义
//#include "add.h"//函数的调用
////引用自带函数用<>
////引用自定义函数用""
//int main()
//{
//	int a = 10;
//	int b = 20;
//	int sum = 0;
//	sum = Add(a,b);
//	printf("%d\n",sum);
//	return 0;
//}
//====================================数列
//#include <stdio.h>
//#include <string.h>
//#include <math.h>
//int main()
//{
//	int x = 1;
//	int y = 1;
//	int i = 0;
//	printf("%d，\n%d,\n",x,y);
//	for(i=1;i<=10;i++)
//	{
//		x = y + x;
//		y = y + x;
//		printf("%d，\n%d,\n",x,y);
//	}
//	return 0;
//}
//======================================
//#include <stdio.h>
//#include <string.h>
//#include <math.h>
////函数声明
//int Add(int x,int y);//当不存在同一个文件中时
////函数的定义
//#include "add.h"//函数的调用
////引用自带函数用<>
////引用自定义函数用""
//int main()
//{
//	int a = 10;
//	int b = 20;
//	int sum = 0;
//	sum = Add(a,b);
//	printf("%d\n",sum);
//	return 0;
//}
//=========================================递归
//程序调用自身的编程技巧
//#include <stdio.h>
//#include <string.h>
//#include <math.h>
//int main()
//{
//	printf("hehe\n");
//	main();
//	return 0;
//}
//===================================递归
//#include <stdio.h>
//#include <string.h>
//#include <math.h>
//void print(int n)
//{
//	if(n>9)
//	{
//		print(n/10);
//	}
//	//一定要有递归出口，要不然会死循环（zai溢出）
//	//每次递归之后会越来越接近条件
//	printf("%d\n",n%10);
//}
//int main()
//{
//	unsigned int num = 0;
//	int x = 3596;
//	int y = 0;
//	scanf("%d",&num);//1234
//	//递归
//	print(num);
//	//print（1234）
//	//print（123）4
//	//print（12）3 4
//	//print（1）2 3 4
//	//
//	y= x/10;
//	printf("%d\n",y);
//	return 0;
//}
//============编写函数不允许创建临时变量，求字符串的长度
//#include <stdio.h>
//#include <string.h>
//int length(char* str)
//{
//	//计算字符串的长度
//	int count = 0;
//	while( *str != '\0')
//	{
//		count++;
//		str++;
//	}
//	return count;
//}
//int main()
//{
//	char arr[] = "xixixi";
//	用自带函数
//	int len = strlen(arr);//strlen不包含\0
//	printf("%d\n",len);
//	自己写函数
//	int len = length(arr);//数组传参，传过去的不是整个数组，而是首元素的地址，
//	printf("%d\n",len);
//	return 0;
//}
//用递归解决
//#include <stdio.h>
//#include <string.h>
//int length(char* str)
//{
//	if( *str != '\0')
//	{
//		return 1+length(str+1);
//	}
//	else
//		return 0;
//}
//int main()
//{
//	char arr[] = "xixixi";
//	int len = length(arr);//数组传参，传过去的不是整个数组，而是首元素的地址，
//	printf("%d\n",len);
//	return 0;
//}
//递归和迭代
//#include <stdio.h>
//#include <string.h>
//int Fac1(int x)
//{
//	int i = 0;
//	int y = 1;
//	for(i=1;i<=x;i++)
//	{
//		y = y*i;
//	}
//	return y;
//}
//int Fac2(int x)
//{
//	if(x<=1)
//	{
//		return 1;
//	}
//	else
//	{
//		return x*Fac2(x-1);
//	}
//}
//int main()
//{
//	int n = 0;
//	int ret1 = 0;
//	int ret2 = 0;
//	scanf("%d",&n);
//	ret1 = Fac1(n);
//	ret2 = Fac2(n);
//	printf("%d\n",ret1);
//	printf("%d\n",ret2);
//	return 0;
//}
//================================斐波那契数列
//#include <stdio.h>
//#include <string.h>
//int count = 0;
//int Fib(int n)
//{
//	if(n==3)
//	{
//		count++;
//	}
//	if(n<=2)
//	{
//		return 1;
//	}
//	else
//	{
//		return Fib(n-1)+Fib(n-2);
//	}
//}
//int main()
//{
//	int n = 0;
//	int ret = 0;
//	scanf("%d",&n);
//	ret = Fib(n);
//    printf("%d\n", ret);
//	printf("%d\n", count);
//    return 0;
//}
//用循环
//#include <stdio.h>
//#include <string.h>
//int FFF(int n)
//{
//	int x = 1;
//	int y = 1;
//	int z = 0;
//	int i = 0;
//	if (n==1||n==2)
//	{
//		return 1;
//	}
//	else
//	{
//		for(i=3;i<=n+1;i++)
//		{
//			z = x + y;
//			x = y;
//			y = z;
//		}
//		return z;
//	}
//}
//int main()
//{
//	int n = 0;
//	int ret = 0;
//	scanf("%d",&n);
//	ret = FFF(n);
//	printf("%d\n", ret);
//	return 0;
//}
//===========================================数组
//#include <stdio.h>
//#include <string.h>
//int main()
//{
//	int arr1[10] = {1,2,3};//剩下的元素默认初始化为0
//	char arr2[5] = {'a','b'};
//	char arr3[5] = "ab";//这个时候第三个为\0，后面为0
//	char arr4[] = "abcdef";
//	printf("%d\n",sizeof(arr4));
//	//sizeof是计算arr4所占空间的大小，arr4里面有七个元素， char 7*1 = 7
//	printf("%d\n",strlen(arr4));
//	//strlen是求字符串的长度[a b c d e f \0]，不包括\0
//	//1.strlen和sizeof没有什么关联
//	//2.strlen是求字符串长度的，只能求字符串的长度---strlen是库函数，需要引用头文件
//	//3.sizeof是计算变量、数组、类型的大小，单位为字节---sizeof是操作符
//	//
//	return 0;
//}
//==============
//#include <stdio.h>
//#include <string.h>
//int main()
//{
//	char arr1[] = "abc";
//	char arr2[] = {'a','b','c'};
//	printf("%d\n",sizeof(arr1));
//	printf("%d\n",sizeof(arr2));
//	printf("%d\n",strlen(arr1));
//	printf("%d\n",strlen(arr2));
//	return 0;
//}
//==================一维数组
//#include <stdio.h>
//#include <string.h>
//int main()
//{
//	//int i = 0;
//	//char arr[] = "abcdef";//[a]0  [b]1  [c]2  [d]3  [e]4  [f]5  [\0]6  
//	//printf("%c\n",arr[3]);
//	//for(i=0;i<=6;i++)
//	//{
//	//	printf("%c\n",arr[i]);
//	//}
//	int arr[] = {1,2,3,4,5,6,7,8,9,0};
//	int sz = sizeof(arr)/sizeof(arr[0]);
//	int i = 0;
//	for(i=0;i<sz;i++)
//	{
//		printf("%d ",arr[i]);
//	}
//	return 0;
//}
//#include <stdio.h>
//#include <string.h>
//int main()
//{
//	int arr[] = {1,2,3,4,5,6,7,8,9,10};
//	int sz = sizeof(arr)/sizeof(arr[0]);
//	int i = 0;
//	for(i=0;i<sz;i++)
//	{
//		printf("&arr[%d] = %p\n", i , &arr[i]);
//	}
//	//数组在内存中是连续存放的；16进制 1-9-a-b-c-d-e-f
//	return 0;
//}
//=====================二维数组
//#include <stdio.h>
//#include <string.h>
//int main()
//{
//	int arr[3][4] = {{1,2,3,4},{1,2}};//列不能省略
//	int i = 0;
//	for(i=0;i<3;i++)
//	{
//		int j = 0;
//		for(j=0;j<4;j++)
//		{
//			printf("&arr[%d][%d]=%p\n",i,j,&arr[i][j]);
//		}
//		printf("\n");
//	}
//	return 0;
//}
//================
//#include <stdio.h>
//#include <string.h>
//void bubble_sort(int arr[],int sz)
//{
//	int i = 0;
//	for(i = 0;i<sz-1;i++)
//	{	
//		int flag = 1;//假设本次排序已经有序了
//		//每一趟冒泡排序
//		int j = 0;
//		for(j=0;j<sz-1-i;j++)
//		{
//			if(arr[j]>arr[j+1])
//			{
//				int tmp = arr[j];
//				arr[j] = arr[j+1];
//				arr[j+1] = tmp;
//				flag = 0;//本趟排序的数据其实不完全有序
//			}
//		}
//		if(flag == 1)
//		{
//			break;
//		}
//	}
//}
//
//int main()
//{
//	int arr[] = {91,822,7323,126,225,445,423,2313,3211,1110};
//	int x = 0;
//	int sz = sizeof(arr)/sizeof(arr[0]);
//	bubble_sort(arr,sz);
//	for(x=0;x<sz;x++)
//	{
//		printf("%d ",arr[x]);
//	}
//	return 0;
//}
//#include <stdio.h>
//#include <string.h>
//int main()
//{
//	int arr[] = {1,2,3,4,5,6,7};
//	int sz = sizeof(arr)/sizeof(arr[0]);
//	//1.sizeof（数组名）---数组名表示整个数组，sizeof(数组名)计算的是整个数组的大小，单位为字节
//	//2.&数组名，数组名代表整个数组，取出的是整个数组的地址
//	//&arr--取出的为数组的地址
//	printf("%p\n",arr);
//	printf("%p\n",arr+1);
//
//	printf("%p\n",&arr[0]);
//	printf("%p\n",&arr[0]+1);
//
//	printf("%p\n",&arr);
//	printf("%p\n",&arr+1);
//
//	printf("%d\n",*arr);//*为解引用
//	return 0;
//}
//int main()
//{
//	double  a = 5/2.0;//商2余1
//	printf("%lf\n",a);
//	return 0;
//}
//==================================移位操作符
//int main()
//{
//	int a = -16;
//	int b = a >> 2;//右移操作符--移动的是二进制位
//	//16----0000...00010000
//	//10000
//	printf("%d\n",a);
//	printf("%d\n",b);
//	return 0;
//}
//1.算术右移
//右边丢弃，左边补原符号位（1为负，0为正）（00000000000000000000000000000000）32位

//2.逻辑右移
//右边丢弃，左边补0
//#include <stdio.h>
//#include <string.h>
//int main()
//{
//	int a = -1;
//	//
//	//整数的二进制表示有原码、反码、补码
//	//存储到内存的是补码
//	//10000000000000000000000000000001 - 原码（-1的）
//	//11111111111111111111111111111110 - 反码 符号位不变，其他位按位取反
//	//11111111111111111111111111111111 - 补码 反码+1 
//	//
//
//	return 0;
//}
//左移
//左边抛弃，右边补0
//#include <stdio.h>
//#include <string.h>
//int main()
//{
//	int a = 5;
//	int b = a << 1;
//	//00000000000000000000000000000101
//	//00000000000000000000000000001010
//	printf("%d\n",b);
//	return 0;
//}
//PS:负数为补码存储，各种操作要先将负数转为补码在进行运算
//=============
//位操作符
//& 按位与 对应的二进制位有0则0，两个都为1才是1
//| 按位或 对应的二进制位有1则1，两个都为0才是0
//^ 按位异或 对应的二进制位如果相同则为0，相异为1
//只能操作整数

//int main()
//{
//	//& -按2进制位与
//	int a = 3;//00000000000000000000000000000011
//	int b = 5;//00000000000000000000000000000101
//	//对应的二进制位有0则0，两个都为1才是1
//	int c = a&b;//00000000000000000000000000000001
//	printf("%d\n",c);
//	return 0;
//}
//int main()
//{
//	//| -按2进制位与
//	//对应的二进制位有1则1，两个都为0才是0
//	int a = 3;//00000000000000000000000000000011
//	int b = 5;//00000000000000000000000000000101
//	int c = a|b;//00000000000000000000000000000111
//	printf("%d\n",c);
//	return 0;
//}
//int main()
//{
//	//^ -按2进制位异或
//	//对应的二进制位如果相同则为0，相异为1
//	int a = 3;//00000000000000000000000000000011
//	int b = 5;//00000000000000000000000000000101
//	int c = a^b;//00000000000000000000000000000110
//	printf("%d\n",c);
//	return 0;
//}
//
//==============================================
//
//int main()
//{
//	int a = 3;//00000000000000000000000000000011
//	int b = 5;//00000000000000000000000000000101
//
//	//// 加减法(有缺陷)当两个数过大时，加上去后可能会溢出
//	//a = a + b;
//	//b = a - b;
//	//a = a - b;
//
//	//操作符
//	a = a^b;//110 = 011^101
//	b = a^b;//011 = 110^101
//	a = a^b;//101 = 110^011
//
//	printf("%d\n",a);
//	printf("%d\n",b);
//	return 0;
//}
//===============
//#include <stdio.h>
//#include <string.h>
////123
//int main()
//{
//	int i = 0;
//	int count = 0;
//	int num = 0;
//	scanf("%d",&num);
//	//统计num中补码中1的个数
//	//while(num !=  0)
//	//{
//	//	if( num%2 == 1)
//	//	{
//	//		count++;
//	//	}
//	//	num = num/2;
//	//}
//	for(i=0;i<32;i++)
//	{
//		if( 1 == ((num>>i)&1))
//		{
//			count++;
//		}
//	}
//	printf("%d\n",count);
//	return 0;
//}
//#include <stdio.h>
//int main()
//{
//	//int a = 10;
//	//a >>= 2;
//	int a = 10;//非0为真，0为假
//	if(a)
//	{
//		printf("xxxxx");
//	}
//	printf("%d\n",!a);
//	return 0;
//}
//#include <stdio.h>
//int main()
//{
//	int a = 10;
//	int* p = &a;//取地址操作符
//	*p = 20;//解引用操作符
//	printf("%d\n",a);
//	return 0;
//}
//#include <stdio.h>
//int main()
//{
//	//int a = 10;
//	//char c = 'r';
//	//char* p =&c;
//	//int arr[10] = {0};
//	////sizeof 计算变量所占内存空间的大小，单位为字节
//	//printf("%d\n",sizeof(a));
//	//printf("%d\n",sizeof(int));
//	//printf("\n");
//
//	//printf("%d\n",sizeof(c));
//	//printf("%d\n",sizeof(char));
//	//printf("\n");
//
//	//printf("%d\n",sizeof(p));
//	//printf("%d\n",sizeof(char*));
//	//printf("\n");
//
//	//printf("%d\n",sizeof(arr));
//	//printf("%d\n",sizeof(int [10]));
//	//printf("\n");
//	short s = 0;//短整形
//	int a = 10;
//	printf("%d\n",sizeof(s = a + 5));//这里这个表达式不会真实进行运算
//	printf("%d\n",s);
//	return 0;
//}
//#include <stdio.h>
//int main()
//{
//	//int a = 0;
//	////00000000000000000000000000000000
//	////~a-----按位取反
//	////11111111111111111111111111111111 - 补码
//	////打印出来原码
//	////11111111111111111111111111111110 - 反码
//	////10000000000000000000000000000001 - 原码
//	////
//	//printf("%d\n",a);
//	//printf("%d\n",~a);
//	int a = 11;
//	int b = 15;
//	//00000000000000000000000000001011
//	a = a | (1<<2);
//	//00000000000000000000000000001111
//	//00000000000000000000000000000100
//	printf("%d\n",a);
//	
//	b = b & (~(1 << 2));
//	printf("%d\n",b);
//	return 0;
//}
//#include <stdio.h>
//int main()
//{
//	int a = 10;
//	int b = 10;
//	printf("%d\n",a++);//后置++，先使用再++
//	printf("%d\n",++b);//前置++，先++再使用
//	return 0;
//}
//#include <stdio.h>
//int main()
//{
//	int n = 10000;
//	int dt = 0.001;
//	int v = 10;
//	int z = 0;
//	int a1 = 0;
//	int v1 = 0;
//	int z1 = 0;
//	int z2 = 0;
//	int v2 = 0;
//	int i = 0;
//	int k = 300;
//	int m = 30;
//	int t = 0;
//	int q = 0;
//	printf("%d\n",z);
//	for(i=0;i<=n;i++)
//	{
//		t = i * dt;
//		a1 = -(k/m) * z;
//		v1 = v;
//		z1 = z;
//		v2 = v1 + dt * a1;
//		z2 = z1 + dt * v1;
//		v = v2;
//		z = z2;
//		printf("%d\n",z);
//	}
//	return 0;
//}
//#include <stdio.h>
//int main()
//{
//	int a = 0;
//	int b = 5;
//	int c = a && b;
//	//&& -- 逻辑与 -- 有假则假，都真为真 0为假，非0为真
//	int d = a || b;
//	//|| -- 逻辑或 -- 有真则真，都假为假
//	printf("%d\n",c);
//	printf("%d\n",d);
//	return 0;
//}
//#include <stdio.h>
//int main()
//{
//	int i = 0 ,a = 1 , b = 2 , c = 3 , d = 4;
//	//i = a++&&++b&&d++;//遇到假，则不执行后面的了
//	////后置++ --- 先使用在++
//	i = a++||++b||d++;//前面为真，后面则不执行了
//	printf("a=%d\nb=%d\nc=%d\nd=%d\n",a,b,c,d);
//	return 0;
//}
//exp1 ? exp2:exp3 --- exp1为真，执行exp2;exp1为假，执行exp3
//#include <stdio.h>
//int main()
//{
//	int a = 10;
//	int b = 20;
//	int c = 0;
//	int max = 0;
//	if(a>b)
//	{
//		max = a;
//	}
//	else
//	{
//		max = b;
//	}
//	c = (a>b ? 3 : -3);
//	return 0;
//}
//=====================================
//exp1,exp2,exp3,...,expn
//由左向右依次执行，整个表达式的结果就是最后一个表达式的结果
//1byte=8bit
//指针是用来存放地址的，地址是唯一表示一块地址空间的
//32位的机器，地址为32位的，一个地址就用32个bit来存储，就是4个byte
//64位的机器，地址为64位的，一个地址就用64个bit来存储，就是8个byte
//#include <stdio.h>
//int main()
//{
//	int a = 10;
//	int* p = &a;//指针变量，存放a的地址
//	return 0;
//}
//#include <stdio.h>
//int main()
//{
//	//printf("%d\n",sizeof(char*));
//	//printf("%d\n",sizeof(short*));
//	//printf("%d\n",sizeof(int*));
//	//printf("%d\n",sizeof(double*));
//	int a = 0x11223344;
//	int* pa = &a;
//	*pa = 0;
//	printf("%d\n",a);
//	return 0;
//}
//指针类型决定了指针进行解引用操作的时候，能够访问空间的大小
//int* p -- *p 能够访问4个字节
//char* p -- *p 能够访问1个字节
//double* p -- *p 能够访问8个字节

//==========
//#include <stdio.h>
//int main()
//{
//	int a = 0x11223344;
//	int* pa = &a;
//	char* pc = &a;
//
//	printf("%p\n",pa);//%p打印16进制
//	printf("%p\n",pa+1);
//
//	printf("%p\n",pc);
//	printf("%p\n",pc+1);
//	return 0;
//}
//指针类型决定了指针走一步走多远（指针的步长）
//int* p -- p+1 向后4个字节
//char* p -- p+1 向后1个字节
//double* p -- p+1 向后8个字节
//#include <stdio.h>
//int main()
//{
//	int arr[10] = {0};
//	char* p = arr;//数组名-首元素的地址
//	int i = 0;
//	for(i=0;i<10;i++)
//	{
//		*(p+i) = 1;
//	}
//	printf("%p\n",p);
//	return 0;
//}
//==============
//野指针 -- 指针指向的位置不可知
//int main()
//{
//	int a;//局部变量不初始化默认随机值
//	int* p;//局部的指针变量，就被随机初始值
//	*p = 20;
//	return 0;
//}
//规避野指针
//

//=================================================================
//#include <stdio.h>
//int main()
//{
//	int a[10] =  {0};
//	int i = 0;
//	int* p = a;
//	for(i=0;i<10;i++)
//	{
//		//*p = i;
//		//p++;
//		*p++ = i;
//	}
//	printf("%d\n",a);
//	return 0;
//}
//=======================
//int main()
//{
//	//int a  = 10;
//	//int* pa = &a;//初始化
//	//int* p = NULL;//NUL -- 用来初始化指针的，给指针赋值
//	int a = 10;
//	int* pa = &a;
//	return 0;
//}
//=====================================
//#include <stdio.h>
////指针的运算
//int main()
//{
//	int arr[10] = {1,2,3,4,5,6,7,8,9,10};
//	int i = 0;
//	int* p = &arr[9];
//	for(i=0;i<10;i++)
//	{
//		printf("%d  ", *p);
//		p = p - 1;
//	}
//	return 0;
//}
//#include <stdio.h>
//int main()
//{
//	int arr[10] = {1,2,3,4,5,6,7,8,9,10};
//	printf("%d\n", &arr[9] - &arr[0]);//指针减去指针可到中间元素个数
//	return 0;
//}
//int my_strlen(char* str)
//{
//	char* start = str;
//	char* end = str;
//	while(*end != '\0')
//	{
//		end++;
//	}
//	return end - start;
//}
//#include <stdio.h>
//int main()
//{
//	//strlen -- 求字符串的长度
//	//递归 - 模拟实现strlen
//	//
//	char arr[] = "bit";
//	int len = my_strlen(arr);
//	printf("%d\n", len);
//	return 0;
//}
//==================================
//#include <stdio.h>
//int main()
//{
//	int arr[10] ={0};
//	printf("%p\n",arr);
//	printf("%p\n",&arr[0]);
//	printf("%p\n",&arr);//这里是整个数组的地址
//	printf("%p\n",&arr+1);//+1之后，跳过整个数组
//
//	//1.&arr -- &数组名-数组名不是首元素地址，数组名表示整个数组-&数组名 取出的是整个数组的地址
//	//2.sizeof(arr)-sizeof(数组名)-数组名表示的整个数组-sizeof（arr）计算的是整个数组的大小
//
//	return 0;
//}
//#include <stdio.h>
//int main()
//{
//	int arr[10] = {0};
//	int* p = arr;
//	int i = 0 ;
//	for(i=0;i<10;i++)
//	{
//
//		printf("%p ===========  %p\n",p+i,&arr[i]);
//	}
//	return 0;
//}
//#include <stdio.h>
//int main()
//{
//	int a = 10;
//	int * pa = &a;//一级指针
//	int* * ppa = &pa;//二级指针 存储一级指针的地址
//	**ppa = 20;
//	printf("%d\n",**ppa);
//	printf("%d\n",a);
//	return 0;
//}
//指针数组 - 本质是一个数组 - 存放指针的数组
//
//数组指针 - 本质是一个指针

//#include <stdio.h>
//int main()
//{
//	int a = 10;
//	int b = 20;
//	int c = 30;
//	//int* pa = &a;
//	//int* pb = &b;
//	//int* pc = &c;
//	////整形数组 - 存放整形
//	////字符数组 - 存放字符
//	////指针数组 - 存放指针
//	int* arr2[3] = {&a,&b,&c};//指针数组
//	int i = 0;
//	for(i=0;i<3;i++)
//	{
//		printf("%d ",*(arr2[i]));
//	}
//	return 0;
//}
#include <stdio.h>

//struct Stu
//{
//	//成员变量
//	char name[20];
//	short age;
//	char tele[12];
//	char sex[5];
//}s1,s2,s3;//全局变量//分号不可少

//typedef struct Stu
//{
//	//成员变量
//	char name[20];
//	short age;
//	char tele[12];
//	char sex[5];
//}Stu;// Stu为类型 //分号不可少
//
//int main()
//{
//	Stu s1 = {"张三",20,"12345678912","男"};
//	struct Stu s2 = {"小张",20,"123437489","女"};
//	return 0;
//}
//
//struct S
//{
//	int a;
//	char c;
//	char arr[20];
//	double d;
//};
//
//struct T
//{
//	char ch[10];
//	struct S s;
//	char *pc;
//};
//int main()
//{
//	char a[] = "hello";
//	struct T t = {"hehe",{100,'w',"hello",3.14},a};
//	printf("%s\n",t.ch);
//	printf("%s\n",t.s.arr);
//	printf("%lf\n",t.s.d);
//	printf("%s\n",t.pc);
//	return 0;
//}

//typedef struct Stu
//{
//	char name[20];
//	short age;
//	char tele[12];
//	char sex[5];
//}Stu;
//
//void Print1(Stu tmp)
//{
//	printf("name:%s\n",tmp.name);
//	printf("age:%d\n",tmp.age);
//	printf("telephone:%s\n",tmp.tele);
//	printf("sex:%s\n",tmp.sex);
//}
//
//void Print2(Stu* ps)
//{
//	printf("  name   :%s\n",ps->name);//格式注意到
//	printf("   age   :%d\n",ps->age);
//	printf("telephone:%s\n",ps->tele);
//	printf("   sex   :%s\n",ps->sex);
//}
//
//int main()
//{
//	Stu s = {"张三",20,"1881881818","男"};
//	//打印结构体数据
//	Print1(s);
//	printf("\n");
//	Print2(&s);//尽量用第二种，结构体传参传地址，直接传地址，占用空间小；
//	return 0;
//}
//===================================================
//压栈
int Add1(int x,int y)
{
	int z = 0;
	z = x + y;
	return z;
}

int main()
{
	int a = 10;
	int b = 20;
	int ret = 0;
	ret = Add1(a,b);
	return 0;
}
