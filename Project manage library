#include <iostream>
#include <stack>
#include <queue>
#include <sstream>
using namespace std;

template<typename T>
class BookStack {
    stack<T> books;
public:
    void read() {
        int n, item;
        cout << "Enter the number of books to add to the library: " << endl;
        cin >> n;
        for(int i = 0; i < n; ++i) {
            cout << "Enter book ID: ";
            cin >> item;
            books.push(item);
        }
    }

    void print() const {
        stack<T> temp = books;
        vector<T> items;
        while(!temp.empty()) {
            items.push_back(temp.top());
            temp.pop();
        }
        for(auto item : items) {
            cout << item << " ";
        }
        cout << endl;
    }

    bool isEmpty() const {
        return books.empty();
    }

    T top() const {
        if(!books.empty())
            return books.top();
        throw runtime_error("Stack is empty");
    }
};

template<typename T>
ostream& operator<<(ostream& os, const BookStack<T>& stack) {
    stack.print();
    return os;
}

template<typename T>
class BookQueue {
    queue<T> booksQueue;
public:
    void add_book(const T& book) {
        booksQueue.push(book);
    }

    void pop_book() {
        if(!booksQueue.empty())
            booksQueue.pop();
        else
            cout << "Queue is empty, cannot pop book." << endl;
    }

    string print_front() const {
        if(!booksQueue.empty()) {
            stringstream ss;
            ss << booksQueue.front();
            return ss.str();
        } else {
            return "Queue is empty.";
        }
    }

    void print_all() const {
        if(booksQueue.empty()) {
            cout << "Queue is empty." << endl;
            return;
        }

        queue<T> tempQueue = booksQueue;
        while(!tempQueue.empty()) {
            cout << tempQueue.front() << endl;
            tempQueue.pop();
        }
    }
};

int main() {
    BookQueue<BookStack<int>> smart_library;
    int ch;
    do {
        cout << "\t\t\t\tLibrary Books" << endl;
        cout << "::::::::::::::: PROGRAM MENU :::::::::::::::" << endl;
        cout << "0. Exit\n";
        cout << "1. Add a New Book" << endl;
        cout << "2. Display the Front Book" << endl;
        cout << "3. Delete the Front Book" << endl;
        cout << "4. Display All IDs of Saved Books" << endl;
        cout << "Enter Your Choice: " << endl;
        cin >> ch;
        cout << "---------------------------------------" << endl << endl << endl;
        switch(ch) {
        case 1: {
            BookStack<int> book;
            book.read();
            smart_library.add_book(book);
            break;
        }
        case 2: {
            cout << smart_library.print_front() << '\n';
            break;
        }
        case 3: {
            smart_library.pop_book();
            break;
        }
        case 4: {
            smart_library.print_all();
            break;
        }
        }
    } while(ch != 0);
    return 0;
}
