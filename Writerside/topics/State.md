# State

## Giới thiệu

State Pattern cho phép một đối tượng thay đổi hành vi của nó khi trạng thái nội bộ thay đổi. Điều này được thực hiện bằng cách đóng gói trạng thái vào các lớp riêng biệt.

## Định nghĩa

State Pattern định nghĩa trạng thái của một đối tượng như một lớp riêng biệt. Khi trạng thái thay đổi, đối tượng sẽ thay đổi lớp hiện tại của nó bằng một lớp mới để thay đổi hành vi.

## Mục đích

- Cho phép một đối tượng thay đổi hành vi khi trạng thái nội bộ thay đổi.

- Đóng gói các trạng thái và hành vi liên quan vào các lớp riêng biệt.

- Tách biệt máy trạng thái khỏi ngữ cảnh sử dụng nó.

## Đặt vấn đề

Giả sử bạn đang phát triển một trò chơi, có lớp NhânVật có các trạng thái: đi bộ, chạy, nhảy. Mỗi trạng thái sẽ có các hành vi riêng.

Ban đầu, mọi logic xử lý được đặt trong lớp NhânVật dẫn đến lớp này phình to, khó bảo trì.

Làm thế nào để tổ chức code cho dễ quản lý hơn?

## Giải quyết

State Pattern được áp dụng như sau:

- Mỗi trạng thái được đóng gói thành một lớp riêng biệt, triển khai từ một interface chung.

- Lớp NhânVật sẽ lưu trữ trạng thái hiện tại và delegate mọi hành vi cho trạng thái đó.

- Khi trạng thái thay đổi, NhânVật sẽ chuyển sang trạng thái mới.

![](https://refactoring.guru/images/patterns/diagrams/state/structure.png)

## Cấu trúc

Các thành phần chính trong State Pattern:

- Context: lớp chứa tham chiếu đến trạng thái hiện tại.

- State: interface chung cho các trạng thái.

- ConcreteState: các lớp triển khai cụ thể cho mỗi trạng thái.

## Cách triển khai

Để triển khai State Pattern trong Java, chúng ta có thể:

- Định nghĩa một interface chung cho State.

- Tạo các lớp Concrete State triển khai interface đó.

- Lớp Context sẽ lưu trữ instance của State hiện tại.

## Ví dụ

// Ví dụ State Pattern áp dụng cho trạng thái của nhân vật trong game

## So sánh với các Pattern

So với Strategy, State tập trung vào việc thay đổi hành vi dựa trên trạng thái đối tượng. Strategy tập trung vào việc thay đổi thuật toán riêng lẻ.

## Kết luận

State Pattern giúp tổ chức code dựa trên trạng thái của đối tượng, dễ mở rộng và bảo trì hơn. Tuy nhiên cũng cần tránh lạm dụng và làm phức tạp hóa code.