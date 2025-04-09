# Library-system
class Library:
    def __init__(self):
        self.books = []

    def display_books(self):
        if not self.books:
            print("No books available in the library.")
        else:
            print("Available books:")
            for book in self.books:
                print(f"- {book}")

    def add_book(self, book):
        self.books.append(book)
        print(f"Book '{book}' added to the library.")

    def borrow_book(self, book):
        if book in self.books:
            self.books.remove(book)
            print(f"You have borrowed '{book}'.")
        else:
            print(f"Sorry, '{book}' is not available.")

    def return_book(self, book):
        self.books.append(book)
        print(f"Thank you for returning '{book}'.")

def main():
    lib = Library()
    lib.add_book("1984 by George Orwell")
    lib.add_book("To Kill a Mockingbird by Harper Lee")
    lib.add_book("The Great Gatsby by F. Scott Fitzgerald")

    while True:
        print("\n===== Library Menu =====")
        print("1. Display available books")
        print("2. Borrow a book")
        print("3. Return a book")
        print("4. Add a book (admin)")
        print("5. Exit")

        choice = input("Enter your choice: ")

        if choice == "1":
            lib.display_books()
        elif choice == "2":
            book = input("Enter the book name you want to borrow: ")
            lib.borrow_book(book)
        elif choice == "3":
            book = input("Enter the book name you want to return: ")
            lib.return_book(book)
        elif choice == "4":
            book = input("Enter the book name to add: ")
            lib.add_book(book)
        elif choice == "5":
            print("Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
