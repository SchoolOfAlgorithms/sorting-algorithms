# sorting-algorithms
![Screenshot (437)](https://user-images.githubusercontent.com/47795037/121123977-c6e11000-c841-11eb-95d4-0d6566b3e3d4.png)

## 1. Merge Sort
```cpp
void merge(int *arr, int l, int r){
    int mid=(l+r)/2;
	int temp[100000];
	int i=l;
	int j=mid+1;
    int k=l;
    while(i<=mid && j<=r){
		if(arr[i]<arr[j])temp[k++]=arr[i++];
		else temp[k++]=arr[j++];
	}
	while(i<=mid)temp[k++]=arr[i++];
	  
	while(j<=r)temp[k++]=arr[j++];
	
	for(int i=l;i<=r;i++)arr[i]=temp[i];
	
}
void mergeSort(int *arr, int l, int r){
	if(l>=r)return ;
	int mid=(l+r)/2;
	mergeSort(arr,l,mid);
	mergeSort(arr,mid+1,r);
	merge(arr,l,r);

}
```
## 2. Quick Sort
```cpp
int partition(int *a, int s, int e){
	int i=s-1;
	int j=s;
	int pivot=a[e];
	for(;j<e;j++){
        if(a[j]<=pivot){
        	i++;
		    swap(a[i],a[j]);
		    
	    }
	}
	swap(a[i+1],a[e]);
	return i+1;
}
void quickSort(int *dp, int s, int e){
	if(s>=e)return;
	int pivotposition=partition(dp,s,e);
	quickSort(dp,s,pivotposition-1);//calling left part of the pivot
	quickSort(dp,pivotposition+1,e);//calling right part of the pivot
}
```
## 3. Bubble Sort
```cpp
void bubbleSort(int *arr, int n){
    for(int i=0;i<n-1;i++){
        for(int j=0;j<n-i-1;j++){
            if(arr[j]>arr[j+1])swap(arr[j], arr[j+1]);
        }
    }    
}
```
## 4. Insertion Sort
```cpp
void insert(int *arr, int i){   
    int key=arr[i];
    int j=i-1;
    while(j>=0 && arr[j]>key){
        arr[j+1]=arr[j];j--;
    }
        arr[j+1]=key;
}
 

void insertionSort(int *arr, int n){
    for(int i=1;i<n;i++){
        insert(arr, i);
    }
}
````
## 5. Selection Sort
```cpp
void selectionSort(int *arr, int n){  
    for(int i=0;i<n-1;i++){
        for(int j=i+1;j<n;j++){
            if(arr[j]<=arr[i]){
                swap(arr[j], arr[i]);
            }
        }
    }
}
```
## 6. Heap Sort
## 7. Radix Sort
## 8. Bucket Sort
