# 0 = not cute / 1 = cute

``` c++
#include <iostream>
using namespace std;

int main() {
	int n, c, cnt = 0;
	scanf("%d", &n);
	for(int i = 0; i < n; i++) {
		scanf("%d", &c);
		if(c == 1) cnt++;
		else cnt--;
	}
	if(cnt > 0) printf("Junhee is cute!");
	else printf("Junhee is not cute!");
	return 0;
}
```