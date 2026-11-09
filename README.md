#include <stdio.h>
int grade[5][4];

void menu(){
	printf("====学生成绩管理系统====\n");
	printf("1、学生成绩录入\n");
	printf("2、学生成绩修改\n");
	printf("3、学生成绩删除\n");
	printf("4、学生成绩查询\n");
	printf("5、学生成绩保存\n");
	printf("6、学生成绩读取\n");
	printf("0、退        出\n");
	printf("=========================\n");
	printf("\n");
}

void input_score(){
            printf("执行录入学生成绩\n");		    
		    printf("请输入要录入全部或者单个学生，全部（1），单个（0）\n");
		    int x;
		    scanf("%d",&x);
		    printf("\n");
			printf("选择的是%d\n",x);
		    if(x==1){	
			for(int i = 0;i<5;i++){
			printf("请输入学号\n");
		    int num;
		    scanf("%d", &num);
		    grade[i][0]=num;  
		    printf("请输入英语成绩\n");
		    int eng;
		     scanf("%d", &eng);
		    grade[i][1]=eng;
		    printf("请输入数学成绩\n");
		    int math;
		     scanf("%d", &math);
		    grade[i][2]=math;
		    printf("请输入语文成绩\n");
		    int chin;
		     scanf("%d", &chin);
		    grade[i][3]=chin;
			printf("当前为第%d名学生\n",i+1);
			printf("\n");
			}
			}
		    if(x==0){
		 	int y;
		 	printf("请输入要选择的学生\n");
		 	scanf("%d",&y);
			printf("选择的是第%d名学生\n",y);
		 	printf("请输入学号\n");
		    int num;
		    scanf("%d", &num);
		    grade[y-1][0]=num; 
			 printf("请输入英语成绩\n");
		    int eng;
		     scanf("%d", &eng);
		    grade[y-1][1]=eng;
		    printf("请输入数学成绩\n");
		    int math;
		     scanf("%d", &math);
		    grade[y-1][2]=math;
		    printf("请输入语文成绩\n");
		    int chin;
		     scanf("%d", &chin);
		    grade[y-1][3]=chin; 
		    printf("当前为第%d名学生\n",y);
		    printf("\n");
		 }
	
}
void printf_score(){
            printf("请输入要查询全部或录入单个学生，全部（1），单个（0）\n");
			int y;
			scanf("%d,",&y);
			printf("\n");
			printf("选择的是%d\n",y);
			if(y==1){	
			printf("学号  英语  数学  语文\n");
			for(int i=0;i<5;i++){
			printf("  %-3d  %-3d  %-3d  %-3d\n",grade[i][0],grade[i][1],grade[i][2],grade[i][3]);
			 }
			}
			if(y==0){
			printf("请输入要查询第几位学生\n");
			int x;
			scanf("%d",&x);
		    printf("学号  英语  数学  语文\n");
		    printf("  %-3d  %-3d  %-3d  %3d\n",grade[x-1][0],grade[x-1][1],grade[x-1][2],grade[x-1][3]);
				
			}
		
}
void update_score(){
	printf("请输入要修改第几个学生\n");
	int x;
	scanf("%d",&x);
	printf("选择的学生成绩为：\n");
    printf("学号  英语  数学  语文\n");
    printf("  %-3d  %-3d  %-3d  %-3d\n",grade[x-1][0],grade[x-1][1],grade[x-1][2],grade[x-1][3]);
	printf("请选择修改单科（0）或全部（1）\n");
	int y;
	scanf("%d",&y);
	if(y==1){
	 printf("请输入英语成绩\n");
	  int eng;
      scanf("%d", &eng);
   	  grade[x-1][1]=eng;
	  printf("请输入数学成绩\n");
 	  int math;
	  scanf("%d", &math);
	  grade[x-1][2]=math;
   	  printf("请输入语文成绩\n");
	  int chin;
	  scanf("%d", &chin);
	  grade[x-1][3]=chin;
	}
	if(y==0){
		printf("请选择更改的科目：英语（1），数学（2），语文（3）\n");
		int choose;
		scanf("%d",&choose);
		switch(choose){
			case 1:
				printf("请输入英语成绩\n");
				int eng;
                scanf("%d", &eng);
	            grade[x-1][1]=eng;
	            break;
	        case 2:
	           	printf("请输入数学成绩\n");
			    int math;
	            scanf("%d", &math);
	            grade[x-1][2]=math;	
	            break;
	        case 3:
	            printf("请输入语文成绩\n");
				int chin;
	            scanf("%d", &chin);
	            grade[x-1][3]=chin;
	            break;
		}
	}
}
void del_score(){
	printf("请输入要删除第几位学生(1-5)\n");
	int x;
	scanf("%d",&x);
    grade[x-1][1]=0;
    grade[x-1][2]=0;
    grade[x-1][3]=0;
	printf("已执行删除第%d名学生成绩\n",x);
}
	
void save_score(){
FILE *fp=fopen("data09.txt","w");
if(!fp){
	printf("文件未打开");
}
for(int i=0;i<5;i++){

  fprintf(fp,"%-3d %-3d %-3d %-3d\n",grade[i][0],grade[i][1],grade[i][2],grade[i][3]);
}

fclose(fp);
printf("成绩成功保存到data09.TXT\n");
}

void read_score(){
FILE *fp=fopen("data09.txt","r");
if(!fp){
	printf("文件未打开");
}
for(int i=0;i<5;i++){
fscanf(fp, "%d %d %d %d", &grade[i][0], &grade[i][1], &grade[i][2], &grade[i][3]);	
}
fclose(fp);
printf("成绩成功从data09.txt中读取\n");
}
		

int main(){
    menu();	
	for(;;){
		
	int choice;
	printf("请输入你的选择（0-6）：\n");

	scanf("%d",&choice);
//	printf("%d",choice);
	
	
	switch(choice){
		case 1:
		    input_score();
		    	menu();
		    break;
		case 2:
		    printf("执行修改学生成绩\n");
		    update_score();
			break;
	    case 3:
	        printf("执行删除学生成绩\n");
	        del_score();
			break;
	    case 4:
	        printf("执行查询学生成绩\n");
	        printf_score();
	        break;
	    case 5:
	        printf("执行保存学生成绩\n");
	        save_score();
	        break;
	    case 6:
	    	printf("执行读取学生成绩\n");
	        read_score();
	        break;
		    
	    default:
		printf("请输入1-5\n");
		case 0:
	        printf("正在执行：退出\n");
	        printf("谢谢使用，再见\n");
	        printf("\n");
	   return 0;   
		menu();}
	}
	   return 0;
}
