# Linear search
class Solution {

    static int search(int arr[], int x) {

        // Your code here
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
        // code here
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
