```c++
class A
{
private:
    const int a; // 常对象成员，可以使用列表初始化或者类的内部初始化
public:
    A():a(0){};
    A(int x):a(x){};//初始化列表
    
    int getValue();       //普通成员函数
    int getValue() const;  //常成员函数，不能修改类中任何数据成员的值
    
    
};

void function()
{
    //对象
	A b;					//普通对象，可以调用全部的成员函数
    const A a;				//常对象，智能调用常成员函数
    const A *p = &a;		//指针变量，指向常对象
    const A &q = a;			//指向常对象的引用
    
    //指针
    char greeting[] = "Hello";	
    char * p1 = greeting;		//指针变量，指向字符数组的变量
    const char* p2 = greeting;	//指针变量，指向字符串数组常量
    char* const p3 = greeting;	//常量指针，指向字符串变量
    const char* const p4 =greeting; //常量指针，指向字符数组常量
}

//函数
void function1(const int var );		//传递过来的参数在函数内不可变
void function2(const char* var);	//参数指针指向的内容的常量
void function3(char* const var);	//参数指针是常量
void function4(const int& var);		//引用参数在函数内为常量

//函数的返回值
const int function5();		//返回一个常数
const int* function6();		//返回一个指向常量的指针变量
int* const function7();		//返回一个指向变量的常量指针

```

2022年3月31日 15:39:12

参考：

https://github.com/huihut/interview#cc
