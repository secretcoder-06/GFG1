# GFG1
Geeks for geeks (Problem of the day)

class Solution{
public:	
	bool sameFreq(string s)
	{
	map<char,int>mp;
    int maxi=INT_MIN;
    int mini=INT_MAX;
    int mxcnt=0;
    int mncnt=0;
    int n=s.length();
     
   for(int i=0;i<n;i++){ 
        mp[s[i]]++;  
    } 
    for(auto it:mp){  
        maxi=max(maxi,it.second); 
        mini=min(mini,it.second); 
    } 
    for(auto it:mp){ 
    if(maxi==it.second) 
    mxcnt++;
    if(mini==it.second) 
    mncnt++;
    }
  
  if((mxcnt==1 && mncnt==mp.size()-1 && (maxi-mini==1)) ||
(mxcnt==mp.size()-1 && mncnt==1 && mini==1) ||
                  mxcnt==mp.size())
  
  return 1;
  
  return 0;
	}
};
