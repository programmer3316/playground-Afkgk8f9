# Filling an array with some initial value

***Filling an static int array
```C++ runnable
#include <bits/stdc++.h> 
using namespace std;

int staticArray[3000];
const int InitValue = 9990;

int main()
{
    std::fill(staticArray,staticArray+(end(staticArray) - begin(staticArray)),InitValue);
    cout << "Array filled with:"<<staticArray[3000-1] << endl;
}
```

***Filling an vector<int> array
```C++ runnable
#include <bits/stdc++.h> 
using namespace std;

vector<int> dynArray;
const int InitValue = 9990;

int main()
{
    dynArray.resize(3000);
    std::fill(dynArray.begin(),dynArray.end(),InitValue);

    cout << "Array filled with:"<<dynArray.back() << endl;
}
```

***Filling an vector<class> array
In that case the object to initialize is a complex one. std::fill works exactly the same.
Avoid memset as much as possible:
```C++ runnable
#include <bits/stdc++.h> 
using namespace std;

class Pod{
public:    
    float x,y;
    float vx,vy;
    Pod(){ } //No initialization
    Pod(float _x,float _y, float _vx, float _vy){
        x=_x;y=_y;vx=_vx;vy=_vy;
    }
};

vector<Pod> dynArray;
const Pod InitValue(0.6f,11.2f,0.45f,0.99f);

int main()
{
    dynArray.resize(3000);
    std::fill(dynArray.begin(),dynArray.end(),InitValue);

    cout << "Array filled with:"<<dynArray.back().x<<","<<dynArray.back().y<< endl;
}
```