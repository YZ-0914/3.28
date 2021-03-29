# 3.28
#define _CRT_SECURE_NO_WARNINGS 1
//关键字 typedef

//3.28
//int main()
//{
//	//typedef - 类型定义 - 类型重定义
//	typedef unsigned int u_int;
//	unsigned int num = 20;
//	u_int num2 = 20;
//	return 0;
//}
//
////取地址
//int main()
//{
//	int a = 10;
//	printf("%p\n", &a);
//	return 0;
//}
//
//int main()
//{
//	int a = 10;
//	int* p = &a;
//	printf("%p\n", &a);
//	printf("%p\n", p);
//	*p = 20;
//	printf("a=%d\n", a);
//	return 0;
//
//}

//void test(int arr[])
//{
//	int sz = sizeof(arr) / sizeof(arr[0]);
//	printf("%d\n", sz);
//}
//
//int main()
//{
//	int arr[10] = { 0 };
//	test(arr);
//	return 0;
//}

//int main()
//{
//	char ch = 'w';
//	char* pc = &ch;
//	return 0;
//}

//int main()
//{
//	char arr[] = "abcdef";
//	char* pc = arr;
//	printf("%s\n", arr);
//	printf("%s\n", pc);
//
//	return 0;
//}

//int main()
//{
//	char* p = "abcdef";//"abcdef"是一个常量字符串
//	//printf("%c\n",*p);
//	printf("%s\n", p);
//	return 0;
//
//}
//
//int main()
//{
//	char* p = "abcdef";//"abcdef"是一个常量字符串
//	*p = 'W';
//	printf("%s\n", p);//出错
//	//printf("%c\n",*p);
////	printf("%s\n", p);
//	return 0;
//
//}
//如何改正
//加入const
//int main()
//{
//	const char* p = "abcdef";//"abcdef"是一个常量字符串
//	//*p = 'W';
//	printf("%s\n", p);//出错
//	//printf("%c\n",*p);
//	//	printf("%s\n", p);
//	return 0;
//
//}
//stackoverflow.com
//Segmentation fault - 段错误
//segmentfault.com
//内存访问出错

//int main()
//{
//	char arr1[] = "abcdef";
//	char arr2[] = "abcdef";
//	char* p1 = "abcdef";
//	char *p2 = "abcdef";
//	if (arr1 == arr2)
//	{
//		printf("hehe\n");
//	}
//	else
//	{
//		printf("haha\n");
//	}
//	return 0;
//}//打印haha

//int main()
//{
//	char arr1[] = "abcdef";
//	char arr2[] = "abcdef";
//	char* p1 = "abcdef";
//	char *p2 = "abcdef";
//	if (p1 == p2)
//	{
//		printf("hehe\n");
//	}
//	else
//	{
//		printf("haha\n");
//	}
//	return 0;
//}//打印hehe
////更准确的写法
//int main()
//{
//	char arr1[] = "abcdef";
//	char arr2[] = "abcdef";
//	const char* p1 = "abcdef";
//	const char *p2 = "abcdef";
//	if (p1 == p2)
//	{
//		printf("hehe\n");
//	}
//	else
//	{
//		printf("haha\n");
//	}
//	return 0;
//}//打印hehe
//
//int main()
//{
//	int arr1[] = { 1, 2, 3, 4, 5 };
//	int arr2[] = { 2, 3, 4, 5, 6 };
//	int arr3[] = { 3, 4, 5, 6, 7 };
//
//	int * parr[] = { arr1, arr2, arr3 };
//	int i = 0;
//	for (i = 0; i < 3; i++)
//	{
//		int j = 0;
//		for (j = 0; j < 5; j++)
//		{
//			printf("%d ", *(parr[i] + j));
//		}
//		printf("\n");
//	}
//	return 0;
//
//}

//数组指针 - 指针

//int main()
//{
//	int *p = NULL;//p是整形指针 - 指向整形的指针
//	char* pc = NULL;//pc是字符指针 - 指向字符的指针 - 可以存放字符的地址
//	int arr[10] = { 0 };//数组指针 - 指向数组的指针 - 存放数组的地址
//	//arr - 首元素地址
//	//&arr[0] - 首元素的地址
//	//&arr - 数组的地址
//
//	int arr[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
//	int(*p)[10]=&arr;//数组的地址要存起来
//	//上面的P就是数组指针
//	return 0;
//}
//
//int main()
//{
//	char* arr[5];
//	char* (*pa)[5] = &arr;
//	int arr2[10] = { 0 };
//	int(*pa2)[10] = &arr2;
//	return 0;
//
//}

//
////参数是数组的形式
//void print1(int arr[3][5], int x, int y)
//{
//	int i = 0;
//	int j = 0;
//	for (i = 0; i < x; i++)
//	{
//		for (j = 0; j < y; j++)
//		{
//			printf("%d ", arr[i][j]);
//		}
//		printf("\n");
//	}
//}
//
////参数是指针的形式
//void print2(int(*p)[5], int x, int y)
//{
//	int i = 0;
//	for (i = 0; i < x; i++)
//	{
//		int j = 0;
//		for (j = 0; j < y; j++)
//		{
//			//printf("%d ", *(*(p + i) + j));
//			printf("%d", *(p + i)[j]);
//		}
//		printf("\n");
//	}
//}
//
//int main()
//{
//	int arr[3][5] = { { 1, 2, 3, 4, 5 }, { 2, 3, 4, 5, 6 }, { 3, 4, 5, 6, 7 } };
//
//	print1(arr, 3, 5);//arr - 数组名 - 数组名就是首元素地址
//	print2(arr, 3, 5);
//	return 0;
//}

//void test(int arr[3][5])
//{}
//void test1(int arr[][5])
//{}
//void test2(int arr[3][])//err
//{}
//void test3(int* arr)//err
//{}
//void test4(int **arr)//err
//{}

//void test5(int (*arr)[5])
//{
//
//}
//int main()
//{
//	int arr[3][5] = { 0 };
//
//	//test(arr);//二维数组传参
//	//test1(arr);
//	//test2(arr);
//	//test3(arr);
//	//test4(arr);
//	test5(arr);
//}
//
//void Print(char*str)
//{
//	printf("%s\n", str);
//
//}
//int main()
//{
//	void(*p)(char*) = Print;
//	(*p)("hello bit");
//	return 0;
////}
//
//int Add(int x, int y)
//{
//	return x + y;
//}
//int Sub(int x, int y)
//{
//	return x - y;
//}
//int Mul(int x, int y)
//{
//	return x * y;
//}
//int Div(int x, int y)
//{
//	return x / y;
//}
//
//int main()
//{
//	//指针数组
//	int* arr[5];
//	//需要一个数组，这个数组可以存放4个函数的地址 —函数指针的数组
//	int(*pa)(int, int) = Add;//Sub Mul Div
//	int(*parr[4])(int, int) = { Add, Sub, Mul, Div };//函数指针的数组
//	int i = 0;
//	for (i = 0; i < 4; i++)
//	{
//		printf("%d\n",parr[i](2, 3));//5 -1 6 0
//	}
//	return 0;
//}
//
//char* my_strcpy(char* dest, const char* src);
////写一个函数指针pf，能够指向my_strcpy
////写一个函数指针数组，能够存放4个my_strcpy函数的地址
//char(*pf(char* my_strcpy(char* dest, const char* src)()//我写的
//	char* (*pf)(char*,const char*)//正确答案
//char(*pfArr[4](char*, const char*)) = { my_strcpy, my_strcpy, my_strcpy, my_strcpy };//我写的
//char* (*pfArr[4])(char*, const char*);//正确答案
//

//计算器
//void menu()
//{
//	printf("*****************************\n");
//	printf("**   1.add            2.sub**\n");
//	printf("**   3.mul            4.div**\n");
//	printf("**           0. exit       **\n");
//	printf("*****************************\n");
//}
//
//int Add(int x, int y)
//{
//	return x + y;
//}
//int Sub(int x, int y)
//{
//	return x - y;
//}
//int Mul(int x, int y)
//{
//	return x * y;
//}
//int Div(int x, int y)
//{
//	return x / y;
//}
//
//int main()
//{
//	int input = 0;
//	int x = 0;
//	int y = 0;
//	int(*pfArr[5])(int, int){ 0, Add, Sub, Mul, Div };
//	do
//	{
//		menu();
//		printf("请选择：>");
//		scanf("%d", &input);
//		if (input >= 1 && input <= 4)
//		{
//			printf("请输入两个操作数：>");
//			scanf("%d%d", &x, &y);
//			int ret = pfArr[input](x,y);
//			printf("%d\n", ret);
//		}
//		else if (input == 0)
//		{
//			printf("退出\n");
//
//		}
//		else
//		{
//			printf("选择错误\n");
//		}
//	} while (input);
//	return 0;
//
//}

//void menu()
//{
//	printf("*****************************\n");
//	printf("**   1.add            2.sub**\n");
//	printf("**   3.mul            4.div**\n");
//	printf("**           0. exit       **\n");
//	printf("*****************************\n");
//}
//
//int Add(int x, int y)
//{
//	return x + y;
//}
//int Sub(int x, int y)
//{
//	return x - y;
//}
//int Mul(int x, int y)
//{
//	return x * y;
//}
//int Div(int x, int y)
//{
//	return x / y;
//}
//int Xor(int x, int y)
//{
//	return x ^ y;
//}
//
//void Calc(int(*pf)(int, int))
//{
//	int x = 0;
//	int y = 0;
//	printf("请输入两个操作数：>");
//	scanf("%d%d", &x, &y);
//	printf("%d\n",Add(x, y));
//}
//int main()
//{
//	int input = 0;
//	do
//	{
//		menu();
//		printf("请选择：>");
//		scanf("%d", &input);
//		switch (input)
//		{
//		case 1:
//			Calc(Add);
//			break;
//		case 2:
//			Calc(Sub);
//			break;
//		case 3:
//			Calc(Mul);
//			break;
//		case 4:
//			Calc(Div);
//			break;
//		case 5:
//			Calc(Xor);
//			break;
//		case 0:
//			printf("退出\n");
//			break;
//		default:
//			printf("选择错误\n");
//			break;
//		}
//	} while (input);
//	return 0;
//
//}
//
//int Add(int x, int y)
//{
//	return x + y;
//}
//
//int main()
//{
//	int arr[10] = { 0 };
//	int(*p)[10] = &arr;//取出数组的地址
//	int (*pfArr[4])(int, int);//pfArr是一个数组 - 函数指针的数组
//	int(*(*ppfArr)[4])(int,int) = &pfArr;
//	//ppfArr是一个数组指针，指针指向的数组有4个元素
//	//指向的数组的每个元素的类型是一个函数指针 int(*)(int,int)
//	return 0;
//}

//void print(char *str)
//{
//	printf("hehe:%s", str);
//}
//
//void test( void(*p)(char*))
//{
//	printf("test\n");
//	p("bit");
//}
//
//int main()
//{
//	test(print);
//	return 0;
//}

//
//}
//void test1()
//{
//	int arr[10] = { 9, 8, 7, 6, 5, 4, 3, 2, 1, 0 };
//	int sz = sizeof(arr) / sizeof(arr[0]);
//	qsort(arr, sz, sizeof(arr[0]), cmp_int);
//	int i = 0;
//	for (i = 0; i < sz; i++)
//	{
//		printf("%d ", arr[i]);
//	}
//}
//
//int cmp_float(const void* e1, const void* e2)
//{
//	if (*(float*)e1 == *(float*)e2)
//	return 0;
//	else if (*(float*)e1 > *(float*)e2)
//		return 1;
//	else
//		return -1;
//	//return((int)(*(float*)e1 - *(float*)e2));强制转换
//}
//void test2()
//{
//	float f[] = { 9.0, 8.0, 7.0, 6.0, 5.0, 4.0 };
//	int sz = sizeof(f) / sizeof(f[0]);
//	qsort(f, sz, sizeof(f[0]), cmp_float);
//	int j = 0;
//	for (j = 0; j < sz; j++)
//	{
//		printf("%f ", f[j]);
//	}
//}
//
//int main()
//{
//	test1();
//	test2();
//	return 0;
//}


//int cmp_int(const void* e1, const void* e2)
//{
//	//比较两个整型值的
//	return *(int*)e1 - *(int*)e2;
//}
//void test1()
//{
//	int arr[10] = { 9, 8, 7, 6, 5, 4, 3, 2, 1, 0 };
//	int sz = sizeof(arr) / sizeof(arr[0]);
//	qsort(arr, sz, sizeof(arr[0]), cmp_int);
//	int i = 0;
//	for (i = 0; i < sz; i++)
//	{
//		printf("%d ", arr[i]);
//	}
//}
//int cmp_float(const void* e1, const void* e2)
//{
//	if (*(float*)e1 == *(float*)e2)
//	return 0;
//	else if (*(float*)e1 > *(float*)e2)
//		return 1;
//	else
//		return -1;
//	//return((int)(*(float*)e1 - *(float*)e2));强制转换
//}
//void test2()
//{
//	float f[] = { 9.0, 8.0, 7.0, 6.0, 5.0, 4.0 };
//	int sz = sizeof(f) / sizeof(f[0]);
//	qsort(f, sz, sizeof(f[0]), cmp_float);
//	int j = 0;
//	for (j = 0; j < sz; j++)
//	{
//		printf("%f ", f[j]);
//	}
//}
//
//int cmp_stu_by_age(const void* e1, const void* e2)
//{
//	return((struct Stu*)e1)->age - ((struct Stu*)e2)->age;
//}
//int cmp_stu_by_name(const void* e1, const void* e2)
//{
//	//比较名字就是比较字符串
//	//字符串比较不能直接用><=来比较，应该用strcmp函数
//	return strcmp((struct Stu*)e1)->name - ((struct Stu*)e2)->name;
//}
//
////实现bubble_sort函数的程序员，他是否知道未来排序的数据类型 - 不知道
////那程序员也不知道，待比较的两个元素的类型
//
//void Swap(char* buf1, char*buf2, int width)
//{
//	int i = 0;
//	for (i = 0; i < width; i++)
//	{
//		char tmp = *buf1;
//		*buf1 = *buf2;
//		*buf2 = tmp;
//		buf1++;
//		buf2++;
//	}
//}
//
//void bubble_sort(void*base, int sz, int width, int(*cmp)(void*e1, void*e2))
//{
//	int i = 0;
//	//趟数
//	for (i = 0; i < sz - 1; i++)
//	{
//		//每一趟比较的对数
//		int j = 0;
//		for (j = 0; j < sz - 1; j++)
//		{
//			//两个元素的比较
//			if (cmp((char*)base + j*width), (char*)base + (j + 1)*width > 0)
//			{
//				//交换
//				Swap((char*)base + j*width, (char*)base + (j + 1)*width, width);
//			}
//		}
//	}
//}
//void test4()
//{
//	int arr[10] = { 9, 8, 7, 6, 5, 4, 3, 2, 1, 0 };
//	int sz = sizeof(arr) / sizeof(arr[0]);
//	//使用bubble_sort的程序员一定知道自己排序的是什么数据
//	//就应该知道如何比较待排序数组中的元素
//	bubble_sort(arr, sz, sizeof(arr[0]), cmp_int);
//}
//void test5()
//{
//	struct Stu s[3] = { { "zhangsan", 20 }, { "lisi", 30 }, { "wangwu", 40 } };
//	int sz = sizeof(s) / sizeof(s[0]);
//	bubble_sort(s, sz, sizeof(s[0]),cmp_stu_by_age );
//	bubble_sort(s, sz, sizeof(s[0]), cmp_stu_by_name);
//}
//
//int main()
//{
//	test4();
//	test5();
//	return 0;
//}


//3.29
#include<stdio.h>
#include<stdlib.h>

#include<string.h>

//int Add(int x, int y)
//{
//	return x + y;
//}
//
//int main()
//{
//	//指针数组
//	int* arr[10];
//	//数组指针
//	int* (*pa)[10] = &arr;
//	//函数指针
//	int(*pAdd)(int, int) = Add;//&Add
//	int sum = (*pAdd)(1, 2);
//	int sum = pAdd(1, 2);
//	           //Add(1,2)
//	printf("sum=%d\n", sum);
//	//函数指针的数组
//	int(*pArr[5])(int, int);
//	//指向函数指针数组的指针
//	int(*(*ppArr)[5])(int, int)=&pArr;
//	return 0;
//}
//================================================
void bubble_sort()
{
	int i = 0;
	//趟数
	for (i = 0; i < sz - 1; i++)
	{
		//一趟冒泡排序
		int j = 0;
		for (j = 0; j < sz - 1 - i; j++)
		{
			if (arr[j]>arr[j + 1])
			{
				int tmp = arr[j];
				arr[j] = arr[j + 1];
				arr[j + 1] = tmp;
			}
		}
	}
}
int main()
{
	int arr[10] = { 9, 8, 7, 6, 5, 4, 3, 2, 1, 0 };
	int sz = sizeof(arr) / sizeof(arr[0]);

	bubble_sort(arr, sz);
	int i= 0;
	for (i = 0; i < sz; i++)
	{
		printf("%d ", arr[i]);
	}
	return 0;
}
#3.29
#define _CRT_SECURE_NO_WARNINGS 1
//3.29
#include<stdio.h>
#include<stdlib.h>

#include<string.h>

//int Add(int x, int y)
//{
//	return x + y;
//}
//
//int main()
//{
//	//指针数组
//	int* arr[10];
//	//数组指针
//	int* (*pa)[10] = &arr;
//	//函数指针
//	int(*pAdd)(int, int) = Add;//&Add
//	int sum = (*pAdd)(1, 2);
//	int sum = pAdd(1, 2);
//	           //Add(1,2)
//	printf("sum=%d\n", sum);
//	//函数指针的数组
//	int(*pArr[5])(int, int);
//	//指向函数指针数组的指针
//	int(*(*ppArr)[5])(int, int)=&pArr;
//	return 0;
//}
//================================================
//void bubble_sort(int arr[],int sz)
//{
//	int i = 0;
//	//趟数
//	for (i = 0; i < sz - 1; i++)
//	{
//		//一趟冒泡排序
//		int j = 0;
//		for (j = 0; j < sz - 1 - i; j++)
//		{
//			if (arr[j]>arr[j + 1])
//			{
//				int tmp = arr[j];
//				arr[j] = arr[j + 1];
//				arr[j + 1] = tmp;
//			}
//		}
//	}
//}
//struct Stu
//{
//	char name[20];
//	int age;
//};
//int main()
//{
//	int arr[10] = { 9, 8, 7, 6, 5, 4, 3, 2, 1, 0 };
//	int sz = sizeof(arr) / sizeof(arr[0]);
//	struct Stu s[3] = { { "zhangsan", 20 }, { "lisi", 30 }, { "wangwu", 50 } };
//	float f[] = { 9.0, 8.0, 7.0, 6.0, 5.0, 4.0 };
//	bubble_sort(arr, sz);
//
//	int i = 0;
//	for (i = 0; i < sz; i++)
//	{
//		printf("%d ", arr[i]);
//	}
//	return 0;
//}
//目前的冒泡排序只能用来排序整型
//==========================================================================

//qsort - 库函数 - 排序
//quick sort - 
//void qsort(void *base,
//             size_t num,
//             size_t width,
//             int(*cmp)(const void *e1, const void e2)
//             );
//base  --  start of target array  --  目标数组的起始位置
//num   --  array size in elements --  几个元素
//width --  element size in bytes  --  几个字节
//compare  --  comparison function --  比较函数
//elem1 --  pointer to the key for the search --  要比较的两个元素的地址
//elem2 --  pointer to the array element to be compared with the key --

//
//
//
//
//void bubble_sort(int arr[],int sz)
//{
//	int i = 0;
//	//趟数
//	for (i = 0; i < sz - 1; i++)
//	{
//		//一趟冒泡排序
//		int j = 0;
//		for (j = 0; j < sz - 1 - i; j++)
//		{
//			if (arr[j]>arr[j + 1])
//			{
//				int tmp = arr[j];
//				arr[j] = arr[j + 1];
//				arr[j + 1] = tmp;
//			}
//		}
//	}
//}
//
//struct Stu
//{
//	char name[20];
//	int age;
//}; 
//
//int cmp_int(const void* e1, const void* e2)
//{
//	//比较两个整型值的
//	return *(int*)e1 - *(int*)e2;
//}
//void test1()
//{
//	int arr[10] = { 9, 8, 7, 6, 5, 4, 3, 2, 1, 0 };
//	int sz = sizeof(arr) / sizeof(arr[0]);
//	qsort(arr, sz, sizeof(arr[0]), cmp_int);
//	int i = 0;
//	for (i = 0; i < sz; i++)
//	{
//		printf("%d ", arr[i]);
//	}
//}
//
//int cmp_float(const void*e1, const void*e2)
//{
//	if (*(float*)e1 == *(float*)e2)
//		return 0;
//	else if (*(float*)e1 > *(float*)e2)
//		return 1;
//	else
//		return -1;
//	//return *(float*)e1 - *(float*)e2;
//	//return ((int)(*(float*)e1 - *(float*)e2));
//}
//void test2()
//{
//	float f[] = { 9.0, 8.0, 7.0, 6.0, 5.0, 4.0 };
//	int sz = sizeof(f) / sizeof(f[0]);
//	qsort(f, sz, sizeof(f[0]), cmp_float);
//	int j = 0;
//	for (j = 0; j< sz; j++)
//	{
//		printf("%f ", f[j]);
//	}
//}
//
//int cmp_stu_by_age(const void*e1, const void*e2)
//{
//	return ((struct Stu*)e1)->age - ((struct Stu*)e2)->age;
//}
//
//int cmp_stu_by_name(const void*e1, const void*e2)
//{
//	//比较名字就是比较字符串
//	//字符串比较不能直接用》《+来比较，应该用strcmp函数
//	return strcmp(((struct Stu*)e1)->name , ((struct Stu*)e2)->name);
//}
//
//void test3()
//{
//	struct Stu s[3] = { { "zhangsan", 20 }, { "lisi", 30 }, { "wangwu", 50 } };
//	int sz = sizeof(s) / sizeof(s[0]);
//	qsort(s, sz, sizeof(s[0]), cmp_stu_by_age);
//	qsort(s, sz, sizeof(s[0]), cmp_stu_by_name);
//	//第一个参数：待排序数组的首元素地址
//	//第二个参数：待排序数组的元素个数
//	//第三个参数：待排序数组的每个元素的大小 - 单位是字节
//	//第四个参数：是函数指针，比较两个元素的所用函数的地址 - 这个函数使用者自己实现
//	//            函数指针的两个参数是：待比较的两个元素的地址
//	int j = 0;
//	for (j = 0; j< sz; j++)
//	{
//		printf("%f ", s[j]);
//	}
//}
//
////实现bubble_sort函数的程序员，他是否知道未来排序的数据类型 - 不知道
////那程序员也不知道，待比较的两个元素的类型
//
//void Swap(char* buf1, char* buf2,int width)
//{
//	int i = 0;
//	for (i = 0; i < width; i++)
//	{
//		char tmp = *buf1;
//		*buf1 = *buf2;
//		*buf2 = tmp;
//		buf1++;
//		buf2++;
//	}
//}
//void bubble_sort(void*base, int sz, int width,int (*cmp)(void*e1,void*e2))
//{
//	int i = 0;
//	//趟数
//	for (i = 0; i < sz - 1; i++)
//	{
//		//每一趟比较的对数
//		int j = 0;
//		for (j = 0; j < sz - 1 - i; j++)
//		{
//			//两个元素的比较
//			if (cmp((char*)base+j*width,(char*)base+(j+1)*width)>0)
//			{
//				//交换
//				Swap((char*)base + j*width, (char*)base + (j + 1)*width,width);
//			}
//		}
//	}
//}
//void test4()
//{
//	int arr[10] = { 9, 8, 7, 6, 5, 4, 3, 2, 1, 0 };
//	int sz = sizeof(arr) / sizeof(arr[0]);
//	//使用bubble_sort的程序员一定知道自己排序的是什么数据
//	//就应该知道如何比较待排序数组中的元素
//	bobble_sort(arr, sz, sizeof(arr[0]), cmp_int);
//
//void test5()
//{
//	struct Stu s[3] = { { "zhangsan", 20 }, { "lisi", 30 }, { "wangwu", 50 } };
//	int sz = sizeof(s) / sizeof(s[0]);
//	bobble_sort(s,sz,sizeof(s[0]),cmp_stu_by_age);
//
//	bobble_sort(s, sz, sizeof(s[0]), cmp_stu_by_name);
//}
//
//
//int main()
//{
//
//	//test1();
//	//test2();
//	//test3();
//	//test4();
//	test5();
//
//	//bubble_sort(arr, sz);
//	//bubble_sort(f, sz);
//	
//	return 0;
//}
//
//
//int main()
//{
//	int a = 10;
//	//int* pa = &a;
//	//char* pc = &a;
//
//	//char ch = 'w';
//	void* p = &a;//无类型指针
//	//*p = 0;//err
//	//p++;//err
//	//p = &ch;
//	//void* 类型的指针 可以接受任意类型的地址
//	//void* 类型的指针 不能进行解引用操作
//	//void* 类型的指针 不能进行加减整数的操作
//	return 0;
//}

//============================================
#include<stdio.h>
//指针和数组笔试题解析
//一维数组
int main()
{
	//数组名是首元素的地址
	//1.sizeof(数组名） - 数组名表示整个数组
	//2.&数组名 - 数组名表示整个数组
	//
	//一维数组
	int a[] = { 1, 2, 3, 4 };//4*4=16
	printf("%d\n", sizeof(a));//sizeof(数组名）-计算的是数组总大小 - 单位是字节 - 16
	printf("%d\n", sizeof(a + 0));//4/8 - 数组名这里表示首元素地址，a+0还是首元素地址，地址的大小就是4/8个字节 
	printf("%d\n", sizeof(*a));//4 - 数组名表示首元素地址，*a就是首元素，sizeof（*a）就是4
	printf("%d\n", sizeof(a + 1));//4/8 - 数组名这里表示首元素地址，a+1是第二个元素地址，地址的大小就是4/8个字节 
	printf("%d\n", sizeof(a[1]));//4 - 第2个元素的大小
	printf("%d\n", sizeof(&a));//4/8 &a取出的是数组的地址，但是数组的地址那也是地址，地址的大小就是4/8个字节
	printf("%d\n", sizeof(*&a));//16 - &a数组的地址，数组的地址解引用访问的数组，sizeof计算的就是数组的大小单位是字节
	printf("%d\n", sizeof(&a + 1));//4/8 &a是数组的地址，&a+1虽然地址跳过整个数组，但还是地址，所以是4/8个字节
	printf("%d\n", sizeof(&a[0]));//4/8 &a[0]是第一个元素的地址
	printf("%d\n", sizeof(&a[0] + 1));//4/8 &a[0]+1是第二个元素的地址
	return 0;
}

//字符数组
int main()
{
	char arr[] = { 'a', 'b', 'c', 'd', 'e', 'f' };
	printf("%d\n", sizeof(arr));//sizeof计算机的是数组大小，6*1=6字节
	printf("%d\n", sizeof(arr+0));//4/8 arr是首元素的地址，arr+0还是首元素的地址，地址的大小是4/8字节
	printf("%d\n", sizeof(*arr));//1 arr是首元素的地址，*arr就是首元素，首元素是字符大小是一个字节
	printf("%d\n", sizeof(arr[1]));//1
	printf("%d\n", sizeof(&arr));//&arr 虽然是数组的地址，但还是地址，地址大小是4/8个字节
	printf("%d\n", sizeof(&arr+1));//&arr+1 虽然是数组的地址，但还是地址，地址大小是4/8个字节
	printf("%d\n", sizeof(&arr[0]+1));//4/8 第二个元素的地址
	return 0;
}

int main()
{
	char arr[] = { 'a', 'b', 'c', 'd', 'e', 'f' };
	printf("%d\n", strlen(arr));//随机值
	printf("%d\n", strlen(arr+0));//随机值
	printf("%d\n", strlen(*arr));//err
	printf("%d\n", strlen(arr[1]));//err
	printf("%d\n", strlen(&arr));//随机值
	printf("%d\n", strlen(&arr+1));//随机值-6
	printf("%d\n", strlen(&arr[0]+1));//随机值-1
	return 0;
}





