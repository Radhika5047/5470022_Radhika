**1. PLUS MNUS** 



\#include <bits/stdc++.h>



using namespace std;



string ltrim(const string \&);

string rtrim(const string \&);

vector<string> split(const string \&);



void plusMinus(vector<int> arr) {

&nbsp;   int positive = 0, negative = 0, zero = 0;

&nbsp;   int n = arr.size();



&nbsp;   for (int i = 0; i < n; i++) {

&nbsp;       if (arr\[i] > 0) {

&nbsp;           positive++;

&nbsp;       } else if (arr\[i] < 0) {

&nbsp;           negative++;

&nbsp;       } else {

&nbsp;           zero++;

&nbsp;       }

&nbsp;   }



&nbsp;   cout << fixed << setprecision(6) << (double)positive / n << endl;

&nbsp;   cout << fixed << setprecision(6) << (double)negative / n << endl;

&nbsp;   cout << fixed << setprecision(6) << (double)zero / n << endl;

}



int main()

{

&nbsp;   string n\_temp;

&nbsp;   getline(cin, n\_temp);



&nbsp;   int n = stoi(ltrim(rtrim(n\_temp)));



&nbsp;   string arr\_temp\_temp;

&nbsp;   getline(cin, arr\_temp\_temp);



&nbsp;   vector<string> arr\_temp = split(rtrim(arr\_temp\_temp));



&nbsp;   vector<int> arr(n);



&nbsp;   for (int i = 0; i < n; i++) {

&nbsp;       int arr\_item = stoi(arr\_temp\[i]);



&nbsp;       arr\[i] = arr\_item;

&nbsp;   }



&nbsp;   plusMinus(arr);



&nbsp;   return 0;

}



string ltrim(const string \&str) {

&nbsp;   string s(str);



&nbsp;   s.erase(

&nbsp;       s.begin(),

&nbsp;       find\_if(s.begin(), s.end(), not1(ptr\_fun<int, int>(isspace)))

&nbsp;   );



&nbsp;   return s;

}



string rtrim(const string \&str) {

&nbsp;   string s(str);



&nbsp;   s.erase(

&nbsp;       find\_if(s.rbegin(), s.rend(), not1(ptr\_fun<int, int>(isspace))).base(),

&nbsp;       s.end()

&nbsp;   );



&nbsp;   return s;

}



vector<string> split(const string \&str) {

&nbsp;   vector<string> tokens;



&nbsp;   string::size\_type start = 0;

&nbsp;   string::size\_type end = 0;



&nbsp;   while ((end = str.find(" ", start)) != string::npos) {

&nbsp;       tokens.push\_back(str.substr(start, end - start));



&nbsp;       start = end + 1;

&nbsp;   }



&nbsp;   tokens.push\_back(str.substr(start));



&nbsp;   return tokens;

}











**2. MINI MAX SUM**



\#include <bits/stdc++.h>



using namespace std;



string ltrim(const string \&);

string rtrim(const string \&);

vector<string> split(const string \&);



void miniMaxSum(vector<int> arr) {

&nbsp;   long long totalSum = 0;

&nbsp;   int minVal = INT\_MAX;

&nbsp;   int maxVal = INT\_MIN;



&nbsp;   for (int i = 0; i < 5; i++) {

&nbsp;       totalSum += arr\[i];

&nbsp;       if (arr\[i] < minVal) {

&nbsp;           minVal = arr\[i];

&nbsp;       }

&nbsp;       if (arr\[i] > maxVal) {

&nbsp;           maxVal = arr\[i];

&nbsp;       }

&nbsp;   }



&nbsp;   long long minSum = totalSum - maxVal;

&nbsp;   long long maxSum = totalSum - minVal;



&nbsp;   cout << minSum << " " << maxSum << endl;

}





int main()

{



&nbsp;   string arr\_temp\_temp;

&nbsp;   getline(cin, arr\_temp\_temp);



&nbsp;   vector<string> arr\_temp = split(rtrim(arr\_temp\_temp));



&nbsp;   vector<int> arr(5);



&nbsp;   for (int i = 0; i < 5; i++) {

&nbsp;       int arr\_item = stoi(arr\_temp\[i]);



&nbsp;       arr\[i] = arr\_item;

&nbsp;   }



&nbsp;   miniMaxSum(arr);



&nbsp;   return 0;

}



string ltrim(const string \&str) {

&nbsp;   string s(str);



&nbsp;   s.erase(

&nbsp;       s.begin(),

&nbsp;       find\_if(s.begin(), s.end(), not1(ptr\_fun<int, int>(isspace)))

&nbsp;   );



&nbsp;   return s;

}



string rtrim(const string \&str) {

&nbsp;   string s(str);



&nbsp;   s.erase(

&nbsp;       find\_if(s.rbegin(), s.rend(), not1(ptr\_fun<int, int>(isspace))).base(),

&nbsp;       s.end()

&nbsp;   );



&nbsp;   return s;

}



vector<string> split(const string \&str) {

&nbsp;   vector<string> tokens;



&nbsp;   string::size\_type start = 0;

&nbsp;   string::size\_type end = 0;



&nbsp;   while ((end = str.find(" ", start)) != string::npos) {

&nbsp;       tokens.push\_back(str.substr(start, end - start));



&nbsp;       start = end + 1;

&nbsp;   }



&nbsp;   tokens.push\_back(str.substr(start));



&nbsp;   return tokens;

}







**3. Time Conversion**



\#include <bits/stdc++.h>



using namespace std;



string timeConversion(string s) {

&nbsp;   string period = s.substr(8, 2);     

&nbsp;   int hour = stoi(s.substr(0, 2));     

&nbsp;   

&nbsp;   if (period == "AM") {

&nbsp;       if (hour == 12) hour = 0;       

&nbsp;   } else { 

&nbsp;       if (hour != 12) hour += 12;      

&nbsp;   }

&nbsp;   

&nbsp;   stringstream ss;

&nbsp;   ss << setfill('0') << setw(2) << hour << s.substr(2, 6);

&nbsp;   return ss.str();

}



int main()

{

&nbsp;   ofstream fout(getenv("OUTPUT\_PATH"));



&nbsp;   string s;

&nbsp;   getline(cin, s);



&nbsp;   string result = timeConversion(s);



&nbsp;   fout << result << "\\n";



&nbsp;   fout.close();



&nbsp;   return 0;

}





**4. SPARSE ARRAY**





\#include <bits/stdc++.h>



using namespace std;



string ltrim(const string \&);

string rtrim(const string \&);



vector<int> matchingStrings(vector<string> strings, vector<string> queries) {

&nbsp;   unordered\_map<string, int> freqMap;

&nbsp;   vector<int> result;



&nbsp;   for (const string\& s : strings) {

&nbsp;       freqMap\[s]++;

&nbsp;   }



&nbsp;   for (const string\& q : queries) {

&nbsp;       result.push\_back(freqMap\[q]); 

&nbsp;   }



&nbsp;   return result;

}





int main()

{

&nbsp;   ofstream fout(getenv("OUTPUT\_PATH"));



&nbsp;   string strings\_count\_temp;

&nbsp;   getline(cin, strings\_count\_temp);



&nbsp;   int strings\_count = stoi(ltrim(rtrim(strings\_count\_temp)));



&nbsp;   vector<string> strings(strings\_count);



&nbsp;   for (int i = 0; i < strings\_count; i++) {

&nbsp;       string strings\_item;

&nbsp;       getline(cin, strings\_item);



&nbsp;       strings\[i] = strings\_item;

&nbsp;   }



&nbsp;   string queries\_count\_temp;

&nbsp;   getline(cin, queries\_count\_temp);



&nbsp;   int queries\_count = stoi(ltrim(rtrim(queries\_count\_temp)));



&nbsp;   vector<string> queries(queries\_count);



&nbsp;   for (int i = 0; i < queries\_count; i++) {

&nbsp;       string queries\_item;

&nbsp;       getline(cin, queries\_item);



&nbsp;       queries\[i] = queries\_item;

&nbsp;   }



&nbsp;   vector<int> res = matchingStrings(strings, queries);



&nbsp;   for (size\_t i = 0; i < res.size(); i++) {

&nbsp;       fout << res\[i];



&nbsp;       if (i != res.size() - 1) {

&nbsp;           fout << "\\n";

&nbsp;       }

&nbsp;   }



&nbsp;   fout << "\\n";



&nbsp;   fout.close();



&nbsp;   return 0;

}



string ltrim(const string \&str) {

&nbsp;   string s(str);



&nbsp;   s.erase(

&nbsp;       s.begin(),

&nbsp;       find\_if(s.begin(), s.end(), not1(ptr\_fun<int, int>(isspace)))

&nbsp;   );



&nbsp;   return s;

}



string rtrim(const string \&str) {

&nbsp;   string s(str);



&nbsp;   s.erase(

&nbsp;       find\_if(s.rbegin(), s.rend(), not1(ptr\_fun<int, int>(isspace))).base(),

&nbsp;       s.end()

&nbsp;   );



&nbsp;   return s;

}









**5. LONELY INTEGER**



\#include <bits/stdc++.h>



using namespace std;



string ltrim(const string \&);

string rtrim(const string \&);

vector<string> split(const string \&);





int lonelyinteger(vector<int> a) {

&nbsp;   int result = 0;

&nbsp;   for (int num : a) {

&nbsp;       result ^= num;

&nbsp;   }

&nbsp;   return result;

}





int main()

{

&nbsp;   ofstream fout(getenv("OUTPUT\_PATH"));



&nbsp;   string n\_temp;

&nbsp;   getline(cin, n\_temp);



&nbsp;   int n = stoi(ltrim(rtrim(n\_temp)));



&nbsp;   string a\_temp\_temp;

&nbsp;   getline(cin, a\_temp\_temp);



&nbsp;   vector<string> a\_temp = split(rtrim(a\_temp\_temp));



&nbsp;   vector<int> a(n);



&nbsp;   for (int i = 0; i < n; i++) {

&nbsp;       int a\_item = stoi(a\_temp\[i]);



&nbsp;       a\[i] = a\_item;

&nbsp;   }



&nbsp;   int result = lonelyinteger(a);



&nbsp;   fout << result << "\\n";



&nbsp;   fout.close();



&nbsp;   return 0;

}



string ltrim(const string \&str) {

&nbsp;   string s(str);



&nbsp;   s.erase(

&nbsp;       s.begin(),

&nbsp;       find\_if(s.begin(), s.end(), not1(ptr\_fun<int, int>(isspace)))

&nbsp;   );



&nbsp;   return s;

}



string rtrim(const string \&str) {

&nbsp;   string s(str);



&nbsp;   s.erase(

&nbsp;       find\_if(s.rbegin(), s.rend(), not1(ptr\_fun<int, int>(isspace))).base(),

&nbsp;       s.end()

&nbsp;   );



&nbsp;   return s;

}



vector<string> split(const string \&str) {

&nbsp;   vector<string> tokens;



&nbsp;   string::size\_type start = 0;

&nbsp;   string::size\_type end = 0;



&nbsp;   while ((end = str.find(" ", start)) != string::npos) {

&nbsp;       tokens.push\_back(str.substr(start, end - start));



&nbsp;       start = end + 1;

&nbsp;   }

&nbsp;   

&nbsp;   tokens.push\_back(str.substr(start));



&nbsp;   return tokens;

}



