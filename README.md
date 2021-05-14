# simpleprimefactorization
#include<bits/stdc++.h>
#include<math.h>
#include<sstream>
#define str string
#define ll long long int
#define con continue
 
#define rt return 0
#define fr first
#define sec second
#define pf push_front
#define pb push_back
#define vb vct.begin()
#define ve vct.end()
#define ib it.begin()
#define ie it.end()
#define lb lst.begin()
#define le lst.end()
#define mb mp.begin()
#define me mp.end()
#define ms mp.size()
#define sb st.begin()
#define se st.end()
#define strb s.begin()
#define stre s.end() 
using namespace std;
int mxn=1000001;
bool ara[1000001];
vector<int>vct; 
void seive()
{
   int i,j;
   memset(ara,false,sizeof(ara));
   for(i=4;i<=mxn;i+=2)ara[i]=true;
   for(i=3;i*i<=mxn;i+=2)
    {
      if(ara[i]==false)
       {
        for(j=i*i;j<=mxn;j+=i)
          ara[j]=true;
       }
    }
    vct.pb(2);
   for(i=3;i<=mxn;i+=2) 
    {
    if(ara[i]==false)
    vct.pb(i);
    }    
   
    
}
   
int main()
{
   seive();
  ll sum=0;   
  int tc; scanf("%d",&tc); while(tc--){
  int n,i,chck,c=0;
  
  scanf("%d",&n);
     if(ara[n]==false) 
    {
        printf("2^0\n");  
        con;
    }      
           
  map<ll,ll>mp;
  map<ll,ll>::iterator it,it2;    
  for(i=0;vct[i]<=n;i++)
   {
     ll value=vct[i];   
     if( n%value == false)
        {
         while(n%value == false)       
          {
           ++mp[value];
            n/=value;  
          }
        }
   } 
  if(mb->fr!=2)printf("2^0*");       
   for(it=mb;it!=me;it++)     
   {
     c++;
     int frst=it->fr;
     int scnd=it->sec;        
     
    if(c==ms) //cout<<frst<<"^"<<scnd;
     printf("%d^%d",frst,scnd);
    else   printf("%d^%d*",frst,scnd);
   }
    printf("\n");
   /* for(it=mb;it!=me;it++)     
   {
     
     ll frst=it->fr;
     ll scnd=it->sec;        
      sum+=(frst*scnd);
    
   }*/
    
    }
   //cout<<sum<<endl;    
   
      rt;
  
}
      
