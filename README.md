create database chat_app;
use chat_app;

create table login(
	id int AUTO_INCREMENT PRIMARY KEY,
    username nvarchar(255),
    email nvarchar(255),
    password nvarchar(255),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
CREATE TABLE messages (
    id INT AUTO_INCREMENT PRIMARY KEY,
    sender_id INT NOT NULL,
    receiver_id INT NOT NULL,
    message TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (sender_id) REFERENCES login(id) ON DELETE CASCADE,
    FOREIGN KEY (receiver_id) REFERENCES login(id) ON DELETE CASCADE
);
select * from login;
select * from mesages;

insert into login(id,username,email,password,created_at)
    value(1,"admin","vudz2310@gmail.com","123","2025-02-26 20:30:45"),
         (2,"test","vudz2310@gmail.com","123","2025-02-26 20:30:45");
