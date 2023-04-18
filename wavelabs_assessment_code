#include<bits/stdc++.h>
using namespace std;

void lexo(vector<int> &ans, vector<int> point)
{
    if(point[0] != ans[0])
    {
        if(point[0] < ans[0])
        {
            ans[0] = point[0];
            ans[1] = point[1]; 
        }
    }
    else{

        if(point[1] < ans[1])
        {
            ans[0] = point[0];
            ans[1] = point[1];
        }
    }    
}

vector<int> Find_highest_quality(vector<vector<int>> towers, int radius)
{
    vector<int> ans;

    int max_quality = 0;
    for(int i=0;i<towers.size();i++)
    {
        int curr_qaulity = 0;
        for(int j=0;j<towers.size();j++)
        {
            int d = pow( towers[i][0]-towers[j][0], 2 ) + pow( towers[i][1]-towers[j][1], 2 );
            d = sqrt(d);

            if( d <= radius )
            {
                curr_qaulity += towers[j][2] / (1+d);
            }
        }

        if(ans.size()==0)
        {
            ans.push_back(towers[i][0]);
            ans.push_back(towers[i][1]);
            max_quality = curr_qaulity;
        }
        else if( curr_qaulity > max_quality )
        {
            ans[0] = towers[i][0];
            ans[1] = towers[i][1];

            max_quality = curr_qaulity;
        }
        else if(curr_qaulity == max_quality)
        {
            lexo(ans, towers[i]);
        }
    }
    
    return ans;
}

int main()
{
    int n;
    cout<<"Total Number of Tower Points: ";
    cin>>n;

    int radius;

    vector<vector<int>> v;

    for(int i=0;i<n;i++)
    {
        int x,y,q;
        cout<<"Enter X-Y Cordinates and Quality of "<<(i+1)<<"th Tower: ";
        cin>>x>>y>>q;
        vector<int> p;
        p.push_back(x);
        p.push_back(y);
        p.push_back(q);

        v.push_back(p);
    }

    cout<<"Enter Radius: ";
    cin>>radius;

    vector<int> HQP = Find_highest_quality(v , radius);

    cout<<"Highest Quality Point: ["<<HQP[0]<<" , "<<HQP[1]<<"]";

    return 0;
}
