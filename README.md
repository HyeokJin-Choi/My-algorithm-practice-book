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

아직해결하지 못한 백준 문제 --> 1406번 // https://www.acmicpc.net/status?user_id=chlgurwls4585&problem_id=1406&from_mine=1
현재 진행 ↓
#include <iostream>
#include <string>
using namespace std;

int main()
{
	cin.tie(0); ios_base::sync_with_stdio(false); cout.tie(0); //할당돤 시간 줄여주기
	string editor = ""; //입력받을 단어 넣는 공간 초기화 해주기
	string choose = ""; //옵션받을 단어 넣는 공간 초기화 해주기
	string P = ""; //옵션이 P로 받았다면 그에 맞는 추가 될 단어 넣는 공간 초기화 해주기
	int count = 0; //옵션을 몇 번 넣을 지 정해주는 숫자갑 받는 공간 초기화 해주기
	cin >> editor; //단어 입력받기
	int couser = editor.length(); // 커서라는 변수를 선언하여 마치 커서처럼 움직임을 나타내기
	cin >> count; //몇 번 넣을 지 입력받기
	for (int i = 0; i < count; i++) //입력받은 횟수만큼 반복~
	{
		cin >> choose; //옵션으로 받을 단어 입력받기
		if (choose == "L") {
			couser--;
			if (couser <= 0) {
				couser = 0;
			}
		}  // L선택 시 커서는 왼쪽으로 움직여 주기. 그것을 couser--;로 표현. 하지만 맨 앞이라면 커서는 0의 값
		else if (choose == "D") {
			couser++;
			if (couser >= editor.length()) {
				couser = editor.length();
			}  // D선택 시 커서는 오른쪽으로 움직여 주기. 그것을 couser++;로 포현. 하지만 맨 뒤라면 커서는 맨 처음에
			  // 넣은 단어의 길이 이상으로 넘어가지 않음
		}
		else if (choose == "B") {
			if (couser != 0) editor.erase(couser - 1, 1);
			couser--;
			if (couser <= 0) {
				couser = 0;
			} // B선택 시 현재 커서의 위치에 있는 단어를 삭제후 couser--;로 커서를 왼쪽으로 움직여 주기.--> 단어를
			 //삭제하더라도 커서는 움직이지 않기 때문. 삭제후 움진인 커서가 맨 앞이라면 couser에 0의 값
		}
		else if (choose == "P") {
			cin >> P;
			editor.insert(couser, P);
			couser++;
			if (couser >= editor.length()) {
				couser = editor.length();
			} // P선택 시 현재 커서의 위치에 더 입력받은 단어를 추가후 couser++;로 커서를 오른쪽으로 움직여 주기. -->
			 //추가하더라도 커서는 움직이지 않기 때문. 추가후 움직인 커서가 맨 뒤라면 커서는 맨 처음에 넣은 단어의 길
			//이 이상으로 넘어가지 않음
		}
	}
	cout << editor;
	return 0;
}

//int 동아리 과제 
<짝수와 홀수 문제>
https://app.code2flow.com/JnOWRD (1) <-- 사람들이 해결한 방법 + 나의 고안
https://app.code2flow.com/YvwU6Z (2) <--내가 직접 해결

<숫자짝꿍>
https://app.code2flow.com/Oz50KGUfbiYi 
좀 복잡할 듯 하여 코드도 같이 ->

#include <vector>
#include <string>
#include <iostream>
#include <algorithm>

using namespace std;

string solution(string X, string Y) {
    string answer = "";
    vector<int> X_int(X.size()); // X의 정수 배열을 담을 벡터 선언 -> 벡터의 크기는 기존의 string X 배열의 크기 그대로!
    vector<int> Y_int(Y.size()); // Y의 정수 배열을 담을 벡터 선언 -> 벡터의 크기는 기존의 string Y 배열의 크기 그대로!

    for (int i = 0; i < X.size(); i++) { //X배열의 크기(길이)만큼 반복
        X_int[i] = X[i] - '0'; // X의 문자를 정수로 변환하여 X_int에 저장! -> -'0'을 해줌으로써 0의 아스키코드 값인 48을 빼주는 것과 동일! 따라서 X의 문자를 정수로 변환하는 과정! 값은 0-9까지 나온다~ 우리가 입력할 값 자체가 각 자리에 0-9사이의 숫자를 입력하므로~~
    }
    for (int i = 0; i < Y.size(); i++) { //Y배열의 크기(길이)만큼 반복
        Y_int[i] = Y[i] - '0'; // Y의 문자를 정수로 변환하여 Y_int에 저장!
    }

    // 각 정수를 받을 벡터들을 내림차순으로 정렬
    sort(X_int.begin(), X_int.end(), greater<int>());
    sort(Y_int.begin(), Y_int.end(), greater<int>());

    int Xcount = 0, Ycount = 0; //각각 X_int와 Y_int의 index역할을 수행!

    while (Xcount < X.size() && Ycount < Y.size()) { //내림차순으로 정렬이 다 되어있는 X_int와 Y_int의 배열에서 짝꿍을 찾기위한 과정 시작! -> X_int배열과 Y_int의 배열이 각각 X,Y의 배열 길이를 초과할 시 반복문 종료. 각각 Xcount <= X.size()-1의 조건으로는 변경 가능 -> Xcount와 Ycount는 각 배열의 index값이기 때문 
        if (X_int[Xcount] == Y_int[Ycount]) { //X_int와Y_int의 값이 같을 때
            answer += to_string(X_int[Xcount]); // 정수를 문자열로 변환하여 answer에 추가 -> X_int든 Y_int든 두 값이 같기 때문에 Y_int[Ycount]로 수정해도 같다!
            Xcount++; 
            Ycount++; //다음 대상을 찾기위한 과정~
        } else if (X_int[Xcount] < Y_int[Ycount]) { //내림차순으로 정렬이 되어 있기에 X_int의 Xcount번 째의 값이 Y_int의 Ycount번 째의 값보다 작을 시 X_int의 Xcount번 째의 원소값이 Y_int의 배열에 존재하지 않음
            Ycount++; //Ycount를 1 증가시켜, 다시 비교하기 위함
        } else {
            Xcount++; //Y_int의 Ycount번 째의 원소 값이 더 작다면 Xcount를 1 증가 시켜서 다시 비교~
        }
    }

    if (answer.empty()) { //결과를 도출할 string형 변수 answer가 비었을 시 -1 도출
        answer = "-1";
    } else if (answer[0] == '0') { //결과를 도출할 string형 변수 answer의 첫번째 원소가 0일시 0 도출 -> 정렬을 다 하고 계산을 다 했는데, 첫번째 원소가 0이라는 뜻은 뒤에 뭐가 오든지 다 0임
        answer = "0";
    }

    return answer; //짝꿍을 찾아서 나타낼 수 있는 가장 큰 수로 도출!
}

