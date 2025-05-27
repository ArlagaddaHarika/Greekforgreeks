# Linear search
class Solution {

    static int search(int arr[], int x) {
        for(int i=0;i<arr.length;i++){
            if(x==arr[i]){
                return i;
            }
        }
        return -1;
    }
}

# Binary search
class Solution {
    public int binarysearch(int[] arr, int k) {
        int l = 0, r = arr.length - 1;
        int result = -1;

        while (l <= r) {
            int mid = l + (r - l) / 2;

            if (arr[mid] == k) {
                result = mid;      
                r = mid - 1;       
            } else if (k < arr[mid]) {
                r = mid - 1;
            } else {
                l = mid + 1;
            }
        }

        return result;
    }
}

# Bubble sort
class Solution {
    public static void bubbleSort(int arr[]) {
        for(int i=0;i<arr.length;i++){
            for(int j=i+1;j<arr.length;j++){
                if(arr[j]<arr[i]){
                    int temp=arr[i];
                    arr[i]=arr[j];
                    arr[j]=temp;
                }
            }
        }
    }
}

# Selection sort
class Solution {
    void selectionSort(int[] arr) {
        for(int i=0;i<arr.length;i++){
            int a=i;
            for(int j=i+1;j<arr.length;j++){
                if(arr[j]<arr[a]){
                    a=j;
                }
            }
            int temp=arr[i];
            arr[i]=arr[a];
            arr[a]=temp;
        }
    }
}
# Insertion sort
class Solution {
    public void insertionSort(int arr[]) {
        // code here
        for(int i=1;i<arr.length;i++){
            int temp=arr[i];
            int j=i-1;
            while(j>=0 && temp<arr[j]){
                arr[j+1]=arr[j];
                j--;
            }
            arr[j+1]=temp;
        }
    }
}

# Merge sort
class Solution {
    void merge(int[] arr, int l,int mid, int r) {
        int n1=mid-l+1;
        int n2=r-mid;
        int k=l;
        int[] L=new int[n1];
        int[] R=new int[n2];
        for(int i=0;i<n1;i++){
            L[i]=arr[k++];
        }
        for(int i=0;i<n2;i++){
            R[i]=arr[k++];
        }
        int i=0,j=0;
        k=l;
        while(i<n1 && j<n2){
            if(L[i]<R[j]){
                arr[k++]=L[i++];
            }
            else{
                arr[k++]=R[j++];
            }
        }
        while(i<n1){
            arr[k++]=L[i++];
        }
        while(j<n2){
            arr[k++]=R[j++];
        }
        
    }
    void mergeSort(int arr[], int l,int r){
        if(l<r){
            int mid=(l+r)/2;
            mergeSort(arr,l,mid);
            mergeSort(arr,mid+1,r);
            merge(arr,l,mid,r);
            
            
        }
    }
}
