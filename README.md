# Dp
Partition Equal Subset Sum


int sum=0;
        for(int i=0;i<n;i++) sum+=arr[i];
        if(sum%2!=0)return 0;
        int ans=sum/2;
         int dp[n+1][ans+1];
        for(int i=0;i<n+1;i++)
        { for(int j=0;j<ans+1;j++)
            { if(i==0 and j>0) dp[i][j]=0;
                if(j==0)dp[i][j]=1;}}
        for(int i=1;i<n+1;i++)
        {for(int j=1;j<ans+1;j++)
            {if(j>=arr[i-1])
                { dp[i][j]= (dp[i-1][j-arr[i-1]]||dp[i-1][j]); }
                else{dp[i][j]=dp[i-1][j];} }}
        return dp[n][ans];
