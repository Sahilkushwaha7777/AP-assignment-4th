# AP-assignment-4th
Write a program that implements interpolation search for a sorted array of integers.


public class InterpolationSearchExample {

    public static int interpolationSearch(int[] arr, int key) {
        int low = 0;
        int high = arr.length - 1;

        while (low <= high && key >= arr[low] && key <= arr[high]) {
            if (low == high) {
                if (arr[low] == key) return low;
                return -1;
            }
            int pos = low + ((key - arr[low]) * (high - low)) / (arr[high] - arr[low]);

            
            if (arr[pos] == key)
                return pos;

            
            if (arr[pos] < key)
                low = pos + 1;
           
            else
                high = pos - 1;
        }
        return -1; 
    }

   
    public static void main(String[] args) {
        int[] sortedArray = {10, 20, 30, 40, 50, 60, 70, 80, 90, 100};
        int key = 70;

        int index = interpolationSearch(sortedArray, key);

        if (index != -1)
            System.out.println("Element found at index: " + index);
        else
            System.out.println("Element not found in the array.");
    }
}
