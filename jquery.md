[04 jquery.txt](https://github.com/user-attachments/files/17654454/04.jquery.txt)

![image](https://github.com/user-attachments/assets/cc3ef36d-3edf-4483-bad3-5fa9a17e6c65)

![image](https://github.com/user-attachments/assets/d69db4b0-ebfe-4bcb-8890-df240f6244a5)

태그 선택자
- document.querySelector("p"); // p 태그 선택
- document.qeurySelectorAll("p") // 모든 p 태그 엘리먼트를 선택해서 배열로 반환한다.
- $("p")
  
클래스 선택자
- document.querySelector(".row") // class에 row가 포함되어 있는 태그 중에서 첫 번째 엘리먼트를 반환한다.
- document.querySelectorAll(".row") // class에 row가 포함된 모든 엘리먼트를 선택해서 배열로 반환한다.
- $(".row")
  
아이디 선택자
- document.querySelector("#form-search") // id가 form-search인 엘리먼트를 반환한다.
- $("#form-search")

자손 선택자
- document.querySelector("#form-search input") // id가 form-search인 엘리먼트의 자식 엘리먼트 중에서 input 태그를 선택한다.
- $("#form-search input")
- $("div p")
- ${".row .col-12 h1")

자식 선택자
- document.querySelectorAll("div > p")

형제 선택자
- document.querySelectorAll("div + p") : 바로 밑 동생이 p여야 선택할 수 있다.
- document.querySelectorAll("div ~ p") : 동생들 중에서 p들을 선택할 수 있다.
