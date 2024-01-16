<h1><center>C++评测系统</center></h1>

## 版本号 0.1

创作C++评测系统之前，我们现制作一个两个文件的比较系统。做法就是读取文件信息然后逐行比较即可。

**附源代码：**

```c++
#include<bits/stdc++.h>
using namespace std;
bool areFilesIdentical(const string& filePath1,const string& filePath2) {
    ifstream file1(filePath1,ios::binary);
    ifstream file2(filePath2,ios::binary);
    if(!file1||!file2) {
        cerr<<"Error opening files!"<<endl;
        return false;
    }
    string buffer1,buffer2;
    while(getline(file1, buffer1)&&getline(file2, buffer2)) {
        if(buffer1!=buffer2) {
            return false;
        }
    }
    return true;
}

int main() {
    const string filePath1="a.txt";
    const string filePath2="b.txt";
    if(areFilesIdentical(filePath1,filePath2)) {
        cout<<"The files are identical."<<endl;
    } else {
        cout<<"The files are not identical."<<endl;
    }
    return 0;
}
```