# Documentation

## Step 1 - Codeblocks

Codeblocks in a nutshell makes it *very easy* for **people** to ***copy, paste and share code.*** We use this whenever possible.

### As an example:

class Library:
    def __init__(self):
        self.books = {}

    def add_book(self, title, author, ISBN):
        if ISBN not in self.books:
            self.books[ISBN] = {'Title': title, 'Author': author}
            print(f"Added book: {title} by {author}")
        else:
            print("Book with the same ISBN already exists.")

    def search_book(self, title):
        found_books = []
        for ISBN, book_info in self.books.items():
            if title.lower() in book_info['Title'].lower():
                found_books.append((ISBN, book_info))
        if found_books:
            print(f"Search results for '{title}':")
            for ISBN, book_info in found_books:
                print(f"ISBN: {ISBN}, Title: {book_info['Title']}, Author: {book_info['Author']}")
        else:
            print(f"No books found with the title '{title}'.")

    def display_books(self):
        if not self.books:
            print("The library is empty.")
        else:
            print("Available books in the library:")
            for ISBN, book_info in self.books.items():
                print(f"ISBN: {ISBN}, Title: {book_info['Title']}, Author: {book_info['Author']}")

def main():
    library = Library()
    
    while True:
        print("\nLibrary Menu:")
        print("1. Add a book")
        print("2. Search for a book")
        print("3. Display all books")
        print("4. Quit")
        
        choice = input("Enter your choice (1/2/3/4): ")
        
        if choice == '1':
            title = input("Enter the title of the book: ")
            author = input("Enter the author of the book: ")
            ISBN = input("Enter the ISBN of the book: ")
            library.add_book(title, author, ISBN)
        elif choice == '2':
            search_title = input("Enter the title to search for: ")
            library.search_book(search_title)
        elif choice == '3':
            library.display_books()
        elif choice == '4':
            print("Goodbye!")
            break
        else:
            print("Invalid choice. Please choose a valid option.")

if __name__ == "__main__":
    main()
