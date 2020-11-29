# 001
oj test
#include <stdio.h>
int main(int argc, const char * argv[])
{
    int a[1000],b[1000];
    int n;
    scanf("%d",&n);
    for (int i =0; i<n; i++) {
        scanf("%d ",&a[i]);
    }
    for (int q=0; q<n; q++) {
        b[q]=0;
        int t;
        int j=a[q];
        for (; j>0; j/=10) {
            t=j%10;
            b[q]+=t;
            }
    }
    for (int z=0; z<n-1; z++) {
        for (int x=0; x<n-z-1; x++) {
            if (b[x]<b[x+1]) {
                int m,l;
                m=a[x];a[x]=a[x+1];a[x+1]=m;
                l=b[x];b[x]=b[x+1];b[x+1]=l;
            }
            if (b[x]==b[x+1]&&a[x]>a[x+1]) {
                int k;
                k=a[x];a[x]=a[x+1];a[x+1]=k;
            }
        }
    }
    for (int c=0; c<n; c++) {
       printf("%d %d\n",a[c],b[c]);
    }
    return 0;
}
