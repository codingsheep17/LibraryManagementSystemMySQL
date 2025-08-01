CREATE DATABASE lms;
USE lms;

CREATE TABLE author (
	author_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    country VARCHAR(100)
);

SELECT * FROM author;

CREATE TABLE books (
	books_id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(100),
    author_id INT,
    genre VARCHAR(100),
    publish_year INT,
    CONSTRAINT fk_author FOREIGN KEY(author_id) REFERENCES author(author_id) ON DELETE CASCADE,
    available_copies INT CHECK (available_copies > 0)
);

ALTER TABLE books MODIFY COLUMN author_id INT FIRST;
SELECT * FROM books;

CREATE TABLE members (
	member_id INT AUTO_INCREMENT PRIMARY KEY,
    full_name VARCHAR(100),
    email VARChar(100) UNIQUE,
    membership_date DATE
);

SELECT * FROM members;

CREATE TABLE borrow_records (
	record_id INT AUTO_INCREMENT PRIMARY KEY,
	member_id INT,
	CONSTRAINT fk_member FOREIGN KEY (member_id) REFERENCES members(member_id) ON DELETE CASCADE,
    book_id INT,
    CONSTRAINT fk_book FOREIGN KEY (book_id) REFERENCES books(books_id) ON DELETE CASCADE,
	borrow_date DATE,
    return_date DATE DEFAULT NULL
);

SELECT * FROM borrow_records;

INSERT INTO author (name, country) VALUES
('J.K. Rowling', 'UK'),
('George R.R. Martin', 'USA'),
('Haruki Murakami', 'Japan'),
('Paulo Coelho', 'Brazil');

SELECT * FROM author;

INSERT INTO books (title, genre, publish_year, author_id, available_copies) VALUES
('Harry Potter and the Sorcerer\'s Stone', 'Fantasy', 1997, 1, 10),
('A Game of Thrones', 'Fantasy', 1996, 2, 5),
('Norwegian Wood', 'Romance', 1987, 3, 7),
('The Alchemist', 'Adventure', 1988, 4, 8),
('Harry Potter and the Chamber of Secrets', 'Fantasy', 1998, 1, 6);

SELECT * FROM books;

INSERT INTO members (full_name, email, membership_date) VALUES
('Ali Raza', 'ali.raza@example.com', '2024-12-01'),
('Fatima Noor', 'fatima.noor@example.com', '2025-01-10'),
('Usman Ghani', 'usman.ghani@example.com', '2025-01-11'),
('Sana Sheikh', 'sana.sheikh@example.com', '2025-01-12');

SELECT * FROM members;

INSERT INTO borrow_records (member_id, book_id, borrow_date, return_date) VALUES
(1, 1, '2025-01-15', '2025-01-25'),
(2, 2, '2025-01-16', NULL),
(3, 3, '2025-01-17', NULL),
(1, 5, '2025-01-20', NULL),
(4, 4, '2025-01-21', '2025-01-28');

SELECT * FROM borrow_records;
