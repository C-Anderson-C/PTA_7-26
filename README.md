# PTA_7-26
# 单词长度
# 你的程序要读入一行文本，其中以空格分隔为若干个单词，以.结束。你要输出每个单词的长度。这里的单词与语言无关，可以包括各种符号，比如it's算一个单词，长度为4。注意，行中可能出现连续的空格；最后的.不计算在内。

# 输入格式：输入在一行中给出一行文本，以.结束

# 提示：用scanf("%c",...);来读入一个字符，直到读到.为止。

# 输出格式：在一行中输出这行文本对应的单词的长度，每个长度之间以空格隔开，行末没有最后的空格。
```cpp  


#include<iostream>
#include<string>
#include<sstream>

using namespace std;
int main() {
	string sencenten;
	getline(cin, sencenten);

	if (sencenten.length() == 0) {  //判断输入是否为空
		cout << 0;
		return 0;
	}
	if (!sencenten.empty() && sencenten.back() == '.') {  //如果输入不是空并且最后一个是'.' 就把'.'忽略
		sencenten.pop_back();
	}
	stringstream ss(sencenten);
	string word;
	bool first = true;  //用于判断是否需要空格

	while (ss >> word) {
		if (!first) {
			cout << " ";
		}
		cout << word.length() ;
		first = false;
	}
}