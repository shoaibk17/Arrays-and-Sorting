# BubbleSort-in-Array

#include <iostream>
using namespace std;
int main() {
    int n; std::cin >> n;
    int arr[n];
    for(int i = 0; i<n; i++){
        cin>>arr[i];
    } int counter = 0;
	while(counter<n){
   	 for(int i = 0; i<n- counter; i++){
        	if(arr[i]>arr[i+1]){
          	  int temp = arr[i];
          	  arr[i]= arr[i+1];
           	 arr[i+1]= temp;
	}
    }
    counter++;
}
	for(int i = 0; i<n; i++){
        std::cout << arr[i] << std::endl;
    }
}

                                        INSERTION Sorting in ARRAY.
                                        
                                        
 #include <iostream>
using namespace std;
int main() {
    int n; std::cin >> n;
    int arr[n];
    for(int i = 0; i<n; i++){
        cin>>arr[i];
    }
    for(int i = 1; i<n;i++ ){
        int current = arr[i];
        int j = i-1;
        while(arr[j]>current && j>=0){
            arr[j+1] = arr[j];
            j--;
        }
        arr[j+1] = current;
    }
    for(int i = 0; i<n; i++){
        std::cout << arr[i]<<" ";
    }
    cout<<endl;
}

                                        
                                
                                        Longest Arthimetic SubArray 
               
#include <iostream>
using namespace std;
int main() {
    int n; std::cin >> n;
    int arr[n];
    for(int i = 0; i<n; i++){
        cin>>arr[i];
    }
    int j =2;
    int current = 2;
    int ans = 2;
    int pd = arr[1] - arr[0];
    while(j<n){
        if(pd == arr[j] - arr[j - 1]){
            current++;
        }
        else{
            pd = arr[j] - arr[j-1];
            current = 2;
        }
        ans = max(ans, current);
        j++;
    }
    std::cout <<ans<<endl;
	// your code goes here
	return 0;
}

			Smallest Positive Interger in AN ARRAY.
			  
#include <iostream>
using namespace std;
int main() {
    int n; std::cin >> n;
    int arr[n];
    for(int i = 0; i<n; i++){
        cin>>arr[i];
    }
    const int N =1e6+2;
    bool check[N];
    for(int i = 0; i<n; i++){
        check[i] = false;
    }
    for(int i=0;    i<n;    i++){
        if(arr[i]>= 0){
            check[arr[i]] = true;
        }
    }
    int ans = -1;
    for(int i =1; i<N; i++){
        if(check[i] == false){
            ans = i;
            break;
        }
    }
    std::cout << ans << std::endl;
return 0; }
				
				 
				 PAIR SUM of SUB- ARRAY = K
				 
#include <iostream>
#include<climits>
using namespace std;

int PairSum(int arr[], int n, int key){
    int low = 0;
    int high = n-1;
    while(low<high){
        if(arr[low] + arr[high] == key){
            cout<<low<<" "<<high<<endl;
            return true;
        }
        else if(arr[low] + arr[high]> key){
            high--;
        }
        else{
            low++;
        }
    }
    return false;
}

int main() {
   int n; std::cin >>  n;
   int arr[n];
   for(int i = 0; i<n;  i++){
       cin>>arr[i];
   }
   int key; cin>>key;
	cout<<PairSum(arr, n, key)<<endl;
	  
// your code goes here
	return 0;
}

	
				Print Spiral Array
	
	
#include <iostream>
using namespace std;

int main() {
	// your code goes here
	int n,m;
	std::cin >> n>>n;
	int a[n][n];
	
	for(int i = 0; i<n; i++){
	    for(int j = 0; j<n; j++)
	        cin>>a[i][j];
	}
    int rowstart =0, rowend = n-1, columnstart = 0,  columnend = n-1;
    while(rowstart<=rowend && columnstart<=columnend){
        // for rowstart
        for(int col = columnstart; col<= columnend; col++)
            std::cout << a[rowstart][col]<<" ";
        rowstart++;
        
        //for columnend
        for(int row = rowstart; row<= rowend; row++)
            cout<<a[row][columnend]<<" ";
        columnend--;
        
        //for row end;
        for(int col = columnend; col >=columnstart; col--)
            cout<<a[rowend][col]<<" ";
        rowend--;
        
        //for columnstart
        for(int row = rowend; row>= rowstart; row--)
            cout<<a[row][columnstart]<<" ";
        columnstart++;   
    }return 0;
}

					
				MATRIX MULTIPLICATION
	
#include <iostream>
using namespace std;

int main() {
    int n1, n2, n3;
    std::cin >> n1>>n2>>n3;
    int m1[n1][n2];
    int m2[n2][n3];
    
    for(int i = 0; i<n1; i++){
        for(int j =0; j<n2; j++)
            cin>>m1[i][j];
    }
    for(int i = 0; i<n2; i++){
        for(int j =0; j<n3; j++)
            cin>>m2[i][j];
    }
    
    int ans[n1][n3];
    for(int i =0; i<n1; i++){
        for(int j = 0; j<n3; j++)
            ans[i][j] = 0;
    }
    
    for(int i =0; i<n1; i++){
        for(int j =0; j<n3; j++){
            for(int k =0; k<n2; k++){
                ans[i][j] += m1[i][k] * m2[k][j];
            }
        }
    }
    for(int i = 0; i<n1; i++){
        for(int j =0; j<n3; j++)
            std::cout<<ans[i][j]<<" ";
        cout<<"\n";
    }
	// your code goes here
	return 0;
}
	
				MATRIX SEARCH			 
				
#include <iostream>
using namespace std;

int main() {
    int n,m,key;
    std::cin >> n>>m>>key;
    int mat[n][m];
    for(int i = 0; i<n; i++){
        for(int j = 0; j<m; j++){
            cin>>mat[i][j];
        }
    }
    int r= 0, c = m-1;
    bool found = false;
    while(r<n && c >= 0){
        if(mat[r][c] == key){
            found = true;
        }
        if(mat[r][c]>key){
            c--;
        }
        else{
            r++;
        }
    }
        if(found){
            std::cout << " Element found";
        }
        else{
            cout<<" Not there";
        }
	return 0;
}

