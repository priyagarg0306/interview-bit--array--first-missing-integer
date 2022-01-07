# interview-bit--array--first-missing-integer

---> Question:

Given an unsorted integer array, find the first missing positive integer.

Example:

Given [1,2,0] return 3,

[3,4,-1,1] return 2,

[-8, -7, -6] returns 1

Your algorithm should run in O(n) time and use constant space.

------> Code:

int Solution::firstMissingPositive(vector<int> &v) {

    int n=v.size();

    for(int i=0;i<n;i++){
            if(v[i]>0 && v[i]<=n){
                if(v[v[i]-1]!=v[i]){
                    swap(v[v[i]-1],v[i]);
                    i--;
                }
                
            }
    }

    for(int i=0;i<n;i++){
        if(v[i]!=i+1){
            return i+1;
        }
    }

    return n+1;
}
