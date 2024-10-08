#include <iostream>
#include <string>
#include <algorithm>
#include <vector>

using namespace std;
string multiplyStrings(string num1, string num2) 
{
    if (num1 == "0" || num2 == "0")
        return "0";
    
    int len1 = num1.size();
    int len2 = num2.size();
    
    vector<int> result(len1 + len2, 0);

    for (int i = len1 - 1; i >= 0; i--) 
    {
        for (int j = len2 - 1; j >= 0; j--) 
        {
            int mul = (num1[i] - '0') * (num2[j] - '0'); 
            int sum = mul + result[i + j + 1];            
            result[i + j + 1] = sum % 10;                 
            result[i + j] += sum / 10;                    
        }
    }

    string resultStr = "";
    for (int i = 0; i < result.size(); i++) 
    {
        if (!(resultStr.empty() && result[i] == 0)) 
        { 
            resultStr += to_string(result[i]);
        }
    }

    return resultStr;
}

string nextAddition(string str_number_first, string str_number_second)
{
    string score = "";
    reverse(str_number_first.begin(), str_number_first.end());
    reverse(str_number_second.begin(), str_number_second.end());

    unsigned int len1 = str_number_first.length();
    unsigned int len2 = str_number_second.length();
    
    unsigned int carry = 0;  

    for (unsigned int i = 0; i < max(len1, len2); i++) 
    {
        int digit_first = (i < len1) ? (str_number_first[i] - '0') : 0;
        int digit_second = (i < len2) ? (str_number_second[i] - '0') : 0;
        int sum = digit_first + digit_second + carry;

        carry = sum / 10;

        score += to_string(sum % 10);
    }

    if (carry) 
        score += to_string(carry);
    

    reverse(score.begin(), score.end());

    return score;
}

int main()
{
    ios_base::sync_with_stdio(false);
    vector <string> score_vector = {};

    unsigned long a = 0;
    unsigned int n = 0;
    unsigned int z = 0;
    unsigned int p = 0;
    unsigned int input_counter = 0;

    cin >> p;
    for(unsigned int i2 = 0; i2 < p; i2++)
    {
        while (input_counter < 2)
        {
            cin >> n;
            string wynik = "0";

            for(unsigned int i = 0; i < n; i++)
            {
                cin >> z >> a;
                if(z == 0)
                {
                    wynik = nextAddition(wynik, to_string(a));
                }
                else
                    wynik = multiplyStrings(wynik, to_string(a));
            }
            input_counter += 1;
            score_vector.push_back(wynik);
        }
        input_counter = 0;
        
    }
    
    for(unsigned int i = 1; i < p + 1; i++)
    {
        if(score_vector.at(i) != score_vector.at(i + 1))
            cout << "rozne" << "\n";
        else
            cout << "rowne" << "\n";
    }
    return 0;
}
