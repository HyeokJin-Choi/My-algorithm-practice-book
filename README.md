# My-algorithm-practice-book
This is my computer algorithm practice book for when i faced the difficult coding problem.

백준 문제를 c++언어를 통해 내가 해결한 방식 

백준 알람 문제 사이트--> https://www.acmicpc.net/problem/2884

#include <iostream>

using namespace std;

int main()
{
    int H, M;
    cin >> H >> M;
    if(M>=45)
    {
        M-=45;
    }
    else if(M<45)
    {
        M+=15;
        H--;
        if(H<0)
        {
            H+=24;
        }
    }
    cout << H << " " << M;
    return 0;
}

백준 A+B - 4 문제 사이트 --> https://www.acmicpc.net/problem/10951

#include <iostream>

using namespace std;

int main()
{
    int A, B, sum;
    for (int i=0; i<5; i++)
    {
    cin >> A >> B;
    sum = A + B;
    cout << sum << endl;
    }
    return 0;
}
