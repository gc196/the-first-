# the-first-
Gc's first repository in github
#include<stdio.h>
int main(void){
	int n=0;
	scanf("%d",&n);
	int rec[n][n];
	int i,j;
	for(i=0;i<n;i++){
		for(j=0;j<n;j++){
			scanf("%d",&rec[i][j]);
		}
	} 
	int sum[2*n+2];
	for(i=0;i<2*n+2;i++){
		sum[i]=0;
	}
	for(i=0;i<n;i++){
		for(j=0;j<n;j++){
			sum[i]+=rec[i][j];
		}
	}
	for(i=n;i<2*n;i++){
		for(j=0;j<n;j++){
			sum[i]+=rec[j][i-n];
		}
	}
	for(i=0;i<n;i++){
		sum[2*n]+=rec[i][i];
	} 
	for(i=0;i<n;i++){
		sum[2*n+1]+=rec[n-1-i][i];
	} 
	int t=0;
	for(i=0;i<2*n+1;i++){
		for(j=0;j<2*n+1-i;j++){
			if(sum[j]>sum[j+1]){
				t =  sum[j]	;
				sum[j] =sum[j+1];
				sum[j+1] = t;
			}
		}
	}
	for(i=2*n+1;i>-1;i--){
		printf("%d ",sum[i]);
	}
	return 0;
} 
