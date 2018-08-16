# converting-array-into-zigzag-fashion

#include <iostream>
using namespace std;
class example{
    public:
    int a[10000];
    int i,n;
    
    int accept();
    int process();
    int swap(int x,int y,int i);
    int display();
    
};
    int example :: accept()
    {
            cin>>n;
            for(i=0;i<n;i++)
            {
                cin>>a[i];
            }
    }
    int example :: process()
    {
        
            int b[100],x,y;
            for(i=0;i<n-1;i++)
            {
                if(i%2==0)
                {
                    x=a[i];
                    y=a[i+1];
                    if(x>y)
                    {
                        swap(x,y,i);
                    }
                    else
                    {
                        continue;
                    }
                }
                if(i%2!=0)
                {
                    x=a[i];
                    y=a[i+1];
                    if(x<y)
                    {
                        swap(x,y,i);
                    }
                    else
                    {
                        continue;
                    }
                }
            }
    }
    int example :: swap(int x,int y,int i)
    {
        a[i]=y;
        a[i+1]=x;
    }
    int example :: display()
    {
        for(i=0;i<n;i++)
        {
            cout<<a[i]<<" ";
        }
        cout<<"\n";
    }
int main() {
	//code
	example st[100];
	int i,n;
	cin>>n;
	for(i=0;i<n;i++)
	{
	st[i].accept();
	}
	for(i=0;i<n;i++)
	{
	st[i].process();
	st[i].display();
	}
	return 0;
}
