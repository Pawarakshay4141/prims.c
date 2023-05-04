# prims.c








#include<stdio.h>

          int cost[10][10]={
                            {0,13,0,0,6,0,0},
                            {13,0,10,6,6,11,0},
                            {0,10,0,0,0,7,0},
                            {0,6,0,0,5,9,0},
                            {6,6,0,5,0,13,8},
                            {0,11,7,9,13,0,10},
                            {0,0,0,0,8,10,0}
                            };
                            int main()
                                    {
                                      int visited[10]={0},min,mincost=0;
                                      int a,b,u,v,n,i,j,ne=1;
                                      printf("\nEnter the number of Vertices :");
                                      scanf("%d",&n);
                                      for(i=0;i< n;i++)
                                      {
                                        for(j=0;j<n;j++)
                                          {
                                            if(cost[i][j]==0)
                                              {
                                                  cost[i][j]=999;
                                               }
                                            }
                                        }
                                          visited[0]=1;
                                          printf("\n");
                                          while(ne < n)
                                          {
                                              min = 999;
                                              for(i=0;i<n;i++)
                                              {
                                                  for(j=0;j<n;j++)
                                                  {
                                                    if(cost[i][j]< min && visited[i]!=0 )
                                                      {
                                                          min=cost[i][j];
                                                          a=u=i;
                                                          b=v=j;
                                                        }
                                                    }
                                                }
                                                        if(visited[u]==0 || visited[v]==0)
                                                          {
                                                            printf("\n Edge %d:(%d %d) cost:%d",ne,a,b,min);
                                                            ne++;
                                                            mincost = mincost + min;
                                                            visited[b]=1;
                                                            }
                                                                cost[a][b]=cost[b][a]=999;
                                                            }
                                                                printf("\n Minimun cost=%d",mincost);
                                                                return 0;
                                      }
/* OUTPUT
Enter the number of nodes:7
Enter the adjacency matrix:
0 13 0 0 6 0 0
13 0 10 6 6 11 0
0 10 0 0 0 7 0
0 6 0 0 5 9 0
6 6 0 5 0 13 8
0 11 7 9 13 0 10
0 0 0 0 8 10 0
Edge 1:(1 5) cost:6
Edge 2:(5 4) cost:5
Edge 3:(4 2) cost:6
Edge 4:(5 7) cost:8
Edge 5:(4 6) cost:9
Edge 6:(6 3) cost:7
Minimun cost=41
