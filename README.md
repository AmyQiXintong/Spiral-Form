// this program aims to print the spiral form of a matrix with size no larger than 10
 
 
 
#include <iostream>
 
 
 
using namespace std;
 
 
 
 
 
int main()
 
{
 
    //part 1:get user input
 
    cout << "Please input the size of the matrix:" << endl;
 
    int size;
 
    cin >> size; //subpart 1:get the size of the matrix
 
 
 
    cout << "Please input the matrix row by row:" << endl;
 
    int arr[10][10];
 
    for (int i = 0; i < 10; i++)
 
    {
 
        for (int j = 0; j < 10; j++) {
 
            arr[i][j] = 0;
 
        }
 
    }//initialising the array
 
 
 
    for (int i = 0; i < size; i++)
 
    {
 
        for (int j = 0; j < size; j++)
 
        {
 
            int input;
 
            cin >> input;
 
            arr[i][j] = input;
 
        }
 
    }//subpart2:get the matrix itself
 
 
 
     //part 2:rearrange into spiral form and print it
 
    cout << "The spiral form of the matrix is:" << endl;
 
 
 
 
 
    int down = 0;
 
    int right = 0;
 
    int up = 0;
 
    int left = 0; //used to count how many lines in each direction
 
 
 
    for (int i = 1; i < size * 2; i++)
 
    {
 
        //cout << "hi" << endl;
 
        if ((i - 1) % 4 == 0) {
 
            down++;
 
            for (int j = down - 1; j <= size - down; j++)
 
            {
 
                cout << arr[j][down - 1] << " ";
 
            }
 
        }
 
        else if ((i - 2) % 4 == 0) {
 
            right++;
 
            for (int j = right; j <= size - right; j++)
 
            {
 
                cout << arr[size - right][j] << " ";
 
            }
 
        }
 
        else if ((i - 3) % 4 == 0) {
 
            up++;
 
            for (int j = size - 1 - up; j >= up - 1; j--)
 
            {
 
                cout << arr[j][size - up] << " ";
 
            }
 
        }
 
        else if (i % 4 == 0) {
 
            left++;
 
            for (int j = size - 1 - left; j >= left; j--)
 
            {
 
                cout << arr[left - 1][j] << " ";
 
            }
 
        }
 
 
 
    }
 
 
 
    cout << endl;
 
 
 
    return 0;
 
}
