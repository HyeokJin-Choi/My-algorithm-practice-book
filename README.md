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

C++ 과제 --> (3장 확인문제 4번)

#include <iostream>
using namespace std;
class ThreeMatrices {
    int a[3][5] = { {5,10,2,7,5},{4,6,2,2,9},{1,9,2,8,4} };
    int b[3][5] = { {5,2,7,4,5},{10,6,9,2,3},{2,6,4,7,1} };
    int c[3][5];
public:
    ThreeMatrices(); //기본 생성자 선언
    void printC(); //멤버함수 선언
    void biggerC(); //""
    void smallerC(); //""
};

ThreeMatrices::ThreeMatrices() {
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 5; j++) {
            c[i][j] = 0;
        }
    }
} //생성자 c배열 0으로 초기화
void ThreeMatrices::printC() {
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 5; j++) {
            cout << c[i][j] << " ";
        } // 0 0 0 0 0 형태로 나타냄
        cout << endl;
    } // 첫 번 째 배열 값을 다 채운 후 한 줄 띄우고 채우기
} // void를 사용한 이유는 리턴을 통해서 반환할 값이 없기 때문
void ThreeMatrices::biggerC() { 
        for (int i = 0; i < 3; i++)
        {
            for (int j = 0; j < 5; j++) {
                if (a[i][j] < b[i][j]) {
                    c[i][j] = b[i][j];
                } 
                else {
                    c[i][j] = a[i][j];
                }

            }
        }
} //배열의 값들을 비교하여 더 큰 값을 c배열에 저장

void ThreeMatrices::smallerC() {
    for (int i = 0; i < 3; i++)
    {
        for (int j = 0; j < 5; j++) {
            if (a[i][j] > b[i][j]) {
                c[i][j] = b[i][j];
            }
            else {
                c[i][j] = a[i][j];
            }

        }
    }
} // 배열의 값들을 비교하여 더 작은 값을 c배열에 저장

int main()
{
    ThreeMatrices m;
    cout << "initail..." << endl;
    m.printC(); // 생성자 함수를 통해 0값으로 초기화 된 값을 멤버함수 printC에 지정된 배열 방식으로 나타냄.
    cout << "bigger..." << endl;
    m.biggerC(); // 멤버함수 biggerC의 계산 방식으로 멤버 변수 int a[3][5]와 int b[3][5]를 비교하여 int c[3][5]에 값을 저장함.
    m.printC(); // 멤버함수 biggerC의 계산 방식으로 멤버 변수 int c[3][5]에 값을 저장된 값들을 printC에 지정된 배열 방식으로 나타냄.
    cout << "smaller..." << endl;
    m.smallerC(); // 멤버함수 smallerC의 계산 방식으로 멤버 변수 int a[3][5]와 int b[3][5]를 비교하여 int c[3][5]에 값을 저장함.
    m.printC(); // 멤버함수 smallerC의 계산 방식으로 멤버 변수  int c[3][5]에 값을 저장된 값들을 printC에 지정된 배열 방식으로 나타냄.

    return 0;
}

C++ 과제 --> (3장 확인문제 9번)

#include <iostream>
#include <cmath>
using namespace std;
class Line {
public:	
	int sx, sy;
	int ex, ey;
	Line();
	void setTwoPoints();
	double getLineLength();
};

Line::Line() {}
void Line::setTwoPoints() {
	cout << "시작점 좌표 정수 두 개를 입력하세요.\n";
	cin >> sx >> sy;
	cout << "끝점 좌표 정수 두 개를 입력하세요.\n";
	cin >> ex >> ey;
}
double Line::getLineLength() {
	return sqrt(pow(sx - sy, 2) + pow(ex - ey, 2));
}

int main()
{
	Line myline;
	myline.setTwoPoints();

	cout << "myline의 길이는 " << myline.getLineLength() << "입니다. \n";
	return 0;
}
