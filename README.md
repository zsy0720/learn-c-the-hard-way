# learn-c-the-hard-way
the process of learning c
将结构体作为函数的参数进行传输
Github中是将结构体的名称进行传递
printf("Joe is at memory location %p:\n", (void*)&joe); (void*)&joe void 是无返回值的类型，用于指针是将一级指针的地址进行操作
实际上就是将地址传递出来用于后续使用（修改地址存放的值等），实际上(void*)&data是一个通用类型，data是什么类型，void*就与该类型的指针一样。用的是同一块内存。

要作为参数，则可以在函数定义时就把位置预留出来

struct student{
char*name;
int age;
};

int main()
{
struct student stu1 = {"joe',32}, *pst;
pst=&stu1;

void print(struct student);//第一个函数的参数是两个结构体，可以直接把定义的结构体进行输入
void print1(char *name,int age);第二个函数的参数是两种类型的变量。
void ptinf2(struct student *);第三个是指针，指向结构体的地址
//三种参数不同的函数，最后打印出的果是一样的







void print(struct student)
{
  pintf(" %s %d",stu1.name,stu.age);
  }

print(stu1);
  
  void print1(char*name,int age)
  {
  printf(" %s %d",stu1.name,stu1.age);
  }

print1(stu1.name,stu1.age);
  
void print2(struct student *)
{
  pintf(" %s %d",pst->name,pst->age);
  }

print2(pst);


return 0;
}
