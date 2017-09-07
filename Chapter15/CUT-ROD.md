```
#include<stdio.h>

int max(int a, int b){
	if(a < b)
		return b;
	else
		return a;
}
int cutRod(int* p, int n){
	if(n == 0){
		return 0;
	}
	int q = -100;
	int i = 0;
	for(i = 1; i <= n; i++){
		q = max(q, p[i] + cutRod(p,n - i));
	}
	return q;
}


int main(){
	int p[11] = {0,1,5,8,9,10,17,17,20,24,30};
	int n = 5;
	int q = cutRod(p, n);
	printf("%d\n", q);
	return 0;
}
```
