// Lab 9

// #include<stdio.h>

#define LENGTH 10 //constant array length

void printArr(int *p);
int getSwapDistance();
void swapArr(int *p, int dist);

int main(void){

    int arr[] = {1,2,3,4,5,6,7,8,9,10}; //initialzie array

    printf("Original Array:\n"); //print original array
    printArr(arr);

    int swapDistance = getSwapDistance(); //get value for swap distance

    swapArr(arr, swapDistance); //swap array elements

    printf("Swapped Array:\n"); //print swapped array
    printArr(arr);

}

//prints array elements
void printArr(int *p){

    for(int i = 0; i < LENGTH; i++){
        printf("%d ", *(p+i));
    }
}


//takes user input for swap distance
int getSwapDistance(){
    int a = 0;

    printf("\nHow far apart should the swaps be? ");
    scanf("%d", &a);
    return a;
}

//swaps array values based on swap distance
void swapArr(int *p, int dist){
    int temp;
    //int count = 0;

    for(int i = 0; LENGTH-i > dist; i+=dist+1){
        temp = *(p+i);
        *(p+i) = *(p+dist+i);
        *(p+dist+i) = temp;

        //count+=dist+1;
    }
}