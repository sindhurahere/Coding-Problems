#include <cstdio>

int max(int a, int b){
	return (a>b) ? a:  b;
}

int min(int a, int b){
	return (a<b) ?a : b;
}

int selectCoin(int a[], int i, int j, int x){
	if(i==j) return x+a[i];
	if(j<i) return x;
	return max(a[i]+min(selectCoin(a, i+2, j, x), selectCoin(a, i+1, j-1, x)), a[j]+min(selectCoin(a, i+1, j-1, x), selectCoin(a, i, j-2, x)));
}

int main() {
	int t, n, i, a[100000];
	scanf("%d",&t);
	while(t--){
		scanf("%d",&n);
		for(i=0;i<n;i++){
			scanf("%d",&a[i]);
		}
		printf("%d\n",selectCoin(a, 0, n-1,0));
	}
	return 0;
}

//Ideone link : http://ideone.com/8MJV6B