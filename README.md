# wildcard-character-matching
#include <bits/stdc++.h>
using namespace std;
 
bool charMatching(char *s1, char * s2)
{
    
    if (*s1 == '\0' && *s2 == '\0')
        return true;
 
    
    if (*s1 == '*' && *(s1+1) != '\0' && *s2 == '\0')
        return false;
 

    if (*s1 == '?' || *s1 == *s2)
        return charMatching(s1+1, s2+1);
 
    
    if (*s1 == '*')
        return charMatching(s1+1, s2) || charMatching(s1, s2+1);
    return false;
}
 
int main()
{
    char s1[20] ;
    char s2[20] ;
    cin>>s1 ;
    cin>>s2 ;
    if(charMatching(s1, s2))
    {
        cout<<"TRUE"<<endl;
    }
    else
    {
        cout<<"FALSE"<<endl;
    }
    return 0;
}
