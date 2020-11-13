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
***************
#include<stdio.h>
int main(){
	int m,n;
	scanf("%d %d",&m,&n);
	int a[m][n],b[m][n];
	int i,j;
	for(i=0;i<m;i++){
		for(j=0;j<n;j++){
			scanf("%d",&a[i][j]); 
			b[i][j]=0;
		}
	}
	int p=0,q=0;
	for(i=0;i<m;i++){//ÀûÓÃ0,1À´ÅÐ¶ÏÊÇ·Ç¡¢ÕýÎó£¬¿ÉÊ¹³ÌÐòÇåÎúÃ÷ÁË£»¶ø²»ÊÇÖ±½Ó½øÐÐ±È½Ï¡£ 
		int min=a[i][0];
		for(j=0;j<n;j++){
		if(a[i][j]<min){
			min=a[i][j];
			p=i;//ÐÐ×îÐ¡++£¬ÁÐ×î´ó++£¬ÊýÖµÎª¶þµÄ×ø±ê¼´ÎªÂí°°µã¡£ 
			q=j;
			}
		}
		if(a[p][q]==min) b[p][q]++;//×¢ÒâÔÚµÚÒ»ÂÖÑ­»·ÖÐÒòÎÞÂí°°µã£¬¹Ê00Ò²±»¸³Öµ£¬ËùÒÔÓ¦ÉèÖÃÏÞÖÆ±ÜÃâ´íÎó¡£ 
	}
	for(i=0;i<n;i++){
		p=0;
		q=0;
		int max=a[0][i];
		for(j=0;j<m;j++){
		if(a[j][i]>max){
			max=a[j][i];
			p=j;
			q=i;
			}
		}
		if(a[p][q]==max) b[p][q]++;
	}int jug=0;
	for(i=0;i<m;i++){
		for(j=0;j<n;j++
			if(b[i][j]==2){
				printf("%d %d %d\n",i,j,a[i][j]);
				jug=1;
			}
		}
	}
	if(jug==0){
		printf("no\n");
	}
	return 0;
}


