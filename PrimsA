#include<stdio.h>
#include<limits.h>
int V;
int p[10];

int min(int k[], int mst[])
{
	int i,m=INT_MAX,pos;

	for(i=0;i<V;i++)
	{
		if(mst[i]==0 &&  k[i]<m)
			{
				m=k[i];
				pos=i;
			}
			


	}
	return pos;
}

void primMST(int g[V][V])
{

	int k[V];
	int mst[V];
	int i,v;
	for(i=0;i<V;i++)
	{
		mst[i]=0;
		k[i]=INT_MAX;
		//p[i]=-1;
	}
	
	k[0]=0;
	p[0]=-1;

	for(i=0;i<V;i++)
	{
		int u=min(k,mst);
		mst[u]=1;
		for(v=0;v<V;v++)
		{
			if(g[u][v] && mst[v]==0 && g[u][v]<k[v])
				{
					k[v]=g[u][v];
					p[v]=u;

				}
		}
	}

}

int main()
{
	int i;int mc=0;
	int j;
	printf("ENTER NO OF VERTICES:");
	scanf("%d",&V);
	int g[V][V];
	printf("ENTER THE COST MATRIX: \n");
	for(i=0;i<V;i++)
		for(j=0;j<V;j++)
			scanf("%d",&g[i][j]);

		primMST(g);
	
	printf("THE MST IS :\n");
	printf("E1 - E2   W\n");
	for(i=1;i<V;i++)
             {
		printf("%d - %d   %d \n",p[i],i,g[i][p[i]]);
		mc=mc+g[i][p[i]];
	     }
	printf("\n MINCOST= %d",mc);

	return 0;
}
