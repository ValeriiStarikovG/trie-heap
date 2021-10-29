#include <iostream>
#include <vector>
using namespace std;

class Heap
{
public:
    Heap() { }

    Heap(vector<int>& newHeap) : heap(&newHeap) { }

    // O(log(n))
    void push(int x)
    {
        // Add element to the end
        heap->push_back(x);
        // Get index of last added element
        int i = heap->size() - 1;
        /* While curr elem is lower than parent node and
        we are not in the top */
        while (heap->at(i) < heap->at(i/2) && i != 1)
        {
            // Swap curr elem with it's parent node
            swap(heap->at(i), heap->at(i / 2));
            // Devide i by 2 to make parrent node current
            i /= 2;
        }
    }

    // O(log(n))
    void pop()
    {
        // // Get index of last element
        int i = heap->size() - 1;
        // Swap last and first elements
        swap(heap->at(i), heap->at(1));
        // Delete ex first elem from the end
        heap->pop_back();
        // Set i to first element
        i = 1;

        /* Check if curr node has children and 
        check if curr node elem is higher than one of child */
        while (i * 2 < heap->size() && heap->at(i) > heap->at(i * 2) ||
            i * 2 + 1 < heap->size() && heap->at(i) > heap->at(i * 2 + 1))
        {
            // If left elem is highet than riht
            if (heap->at(i * 2) > heap->at(i * 2 + 1))
            {
                // Swap curr node with right element
                swap(heap->at(i), heap->at(i * 2 + 1));
                // Set i to ex right elem index
                i *= 2 + 1;
            }
            // Else
            else
            {   // Swap curr node with left element
                swap(heap->at(i), heap->at(i * 2));
                // Set i to ex left elem index
                i *= 2;
            }
        }
    }

    void print()
    {
        for (size_t i = 1; i < heap->size(); i++)
        {
            cout << i << ": " << heap->at(i) << endl;
        }
    }

protected:
    vector<int>* heap;
};

void Tetst1()
{
    cout << "*********Test1*********" << endl;
    cout << "create heap:" << endl;
    // First elem is 0 cause of leveles of heap (i, i*2, i*2+1...)
    vector<int> v = { 0, 2, 3, 5, 4, 10 }; 
    Heap heap(v);
    heap.print();
    cout << endl;

    cout << "heap.push(1);" << endl;
    heap.push(1);
    heap.print();
    cout << endl;

    cout << "heap.pop()" << endl;
    heap.pop();
    heap.print();
    cout << endl;
}

void Test2()
{
    cout << "*********Test2*********" << endl;
    cout << "create heap:" << endl;
    vector<int> v = { 0, 3, 6, 5, 11, 7, 10, 6, 13, 41 };
    Heap heap(v);
    heap.print();
    cout << endl;

    cout << "heap.push(4);" << endl;
    heap.push(4);
    heap.print();
    cout << endl;

    cout << "heap.pop()" << endl;
    heap.pop();
    heap.print();
    cout << endl;
}

int main()
{
    Tetst1();
    cout << endl;
    Test2();
}

