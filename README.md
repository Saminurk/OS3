# OS3
 
FCFS
 
#include<stdio.h>
int main()
{
int b[10],t[10],w[10];
int n,i,j;
float avgw,avgt;
printf("Enter the number of processes:\t");
scanf("%d",&n);
for(i=0;i<n;i++)
{
     printf("\n Enter the burst time of process %d:\t",i);
     scanf("%d",&b[i]);
}
             
             w[0]=0;
              for(i=1;i<n;i++)
              {
w[i]=w[i-1]+b[i-1];
              }
              for(i=0;i<n;i++)
              {
t[i]=w[i]+b[i];
              }
              for(i=0;i<n;i++)
              {
avgw += w[i];
avgt += t[i];
              }
              printf(“Total waiting time=%f\n”,avgw);
             avgw /= n;
             printf(“Average waiting time=%f\n”,avgw);
             printf(“\n”);
             printf(“Total turnaround time=%f\n”,avgt);
             avgt /= n;
             printf(“Average turnaround time-%f\n”,avgt);
}


SJF
 
#include<stdio.h>
int main()
{
     int p[10],b[10],w[10],t[10],i,n,j,temp,temp1;
     float awt=0,att=0;
     printf("Enter the number of processes:\t");
     scanf("%d",&n);
     for(i=0i<n;i++)
     {
             printf("Enter the burst time of process %d:\t”,i);
           
             scanf(“%d”,&b[i]);
             p[i]=i;
       }
       for(i=0;i<n;i++)
       {
              for(j=i;j<n;j++)
              {
                        if(b[i] > b[j])
                        {
                                  temp=b[i];
                                  temp1=p[i];
                                  b[i]=b[j];
                                  p[i]=p[j];
                                  b[j]=temp;
                                  p[j]=temp1;
                         }
              }
       }
      w[0]=0;
      for(i=1;i<n;i++)
      {
             w[i]=w[i-1]+b[i-1];
      }
      for(i=0;i<n;i++)
      {
 t[i]=w[i]+b[i];
      }
      for(i=0;i<n;i++)
      {
               awt=awt+w[i];
               att=att+t[i];
      }
     printf("\n\t Processes \t waiting time \t turnaround time\n");
     for(i=0;i<n;i++)
     printf("\t P%d \t\t %d \t\t\t %d\n",p[i],w[i],t[i]);
     printf(“Total waiting time=%f\n”,awt);
     awt /= n;
     printf(“Average waiting time=%f\n”,awt);
     printf(“\n”);
     printf(“Total turnaround time=%f\n”,att);
     att /=n;
     printf(“Average turnaround time-%f\n”,att);
}
