# Week 11 — Attachment Board (Student Sample)

Spring Boot + Thymeleaf + JPA + MariaDB: 게시글 CRUD / 다중 첨부파일 업로드 / 다운로드

1. PostController, PostService, PostRepository는 각각 어떤 역할을 하며, 서로 어떻게 연결되는가?
   - Controller는 사용자의 입력과 출력을 담당하고, Service에서는 핵심 기능을 수행하며, Repository는 데이터베이스와의 연결을 담당한다.
2. 게시글 작성 시 HTML Form의 입력값과 첨부파일은 Controller에 어떻게 전달되는가?
   - Controller에서 @ModelAttribute("postForm")와  @RequestParam, List<MultipartFile>을 통해 각각 전달받는다. HTML Form은 method="post"와 enctype="multipart/form-data"를 사용하여 서버로 전송한다.
3. Post와 Attachment Entity는 어떤 관계이며, @ManyToOne과 @OneToMany는 각각 어떤 역할을 하는가?
   - 
