# BubbleSort-in-Array

#include <iostream>

using namespace std;


int main() {
    int n; std::cin >> n;
    int arr[n];
    
    for(int i = 0; i<n; i++){
        cin>>arr[i];
    }
int counter = 0;
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

                                        
                                
                                        
