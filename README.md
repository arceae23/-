#include <stdio.h>
#include <stdlib.h>

/* run this program using the console pauser or add your own getch, system("pause") or input loop */

int main(int argc, char *argv[]) {
	int choose = -1;
	int i;
	for(i=0;i<=i;){
	
    printf("======学生成绩管理系统======\n");
	printf("1、学生成绩录入\n");
	printf("2、学生成绩修改\n");
	printf("3、学生成绩删除\n");
	printf("4、学生成绩查询\n");
	printf("5、学生成绩打印\n");
	printf("0、退        出\n");
	
	printf("请输入您的选择（0-5）\n");
	
	printf("============================\n");
	scanf("%d",&choose);
	
	printf("您选择的是:%d\n",choose);
	

	
	switch(choose){//可以用if函数：if(条件){}
		int grades;
	
		case 1:
		  printf("正在使用：学生成绩录入\n");
		  printf("请输入成绩\n");
		  scanf("%d",&grades);
		  printf("学生的成绩是:%d\n",grades);
		    printf("\n");
		  
		  
		  break;
		case 2:
		  printf("正在使用：学生成绩修改\n");
		   printf("请输入成绩\n");
		  scanf("%d",&grades);
		  printf("修改后学生的成绩是:%d\n",grades);
		    printf("\n");
		  break;
		case 3:
		  printf("正在使用：学生成绩删除\n");
		  grades = 0;
		    printf("\n");
		  break;	
		case 4:
		   printf("正在使用：学生成绩查询\n");
		   printf("查询学生的成绩是:%d\n",grades);
		   printf("\n");
		  break;
		case 5:
		  printf("正在使用：学生成绩打印\n");
		  break;
		case 0:
		  printf("谢谢使用，再见\n");
		  break;
		default:
		  printf("对不起，没有这个菜单\n");
		  break;
	}
}
	return 0;
}
