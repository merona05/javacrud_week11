# Week 11 — Attachment Board (Student Sample)

Spring Boot + Thymeleaf + JPA + MariaDB: 게시글 CRUD / 다중 첨부파일 업로드 / 다운로드

1. PostController, PostService, PostRepository는 각각 어떤 역할을 하며, 서로 어떻게 연결되는가?
   - Controller는 사용자의 입력과 출력을 담당하고, Service에서는 핵심 기능을 수행하며, Repository는 데이터베이스와의 연결을 담당한다.
2. 게시글 작성 시 HTML Form의 입력값과 첨부파일은 Controller에 어떻게 전달되는가?
   - Controller에서 @ModelAttribute("postForm")와  @RequestParam, List<MultipartFile>을 통해 각각 전달받는다. HTML Form은 method="post"와 enctype="multipart/form-data"를 사용하여 서버로 전송한다.
3. Post와 Attachment Entity는 어떤 관계이며, @ManyToOne과 @OneToMany는 각각 어떤 역할을 하는가?
   - 하나의 post가 여러개의 Attachment Entity를 가질 수 있기 떄문에 일대 다 관계이다. OneToMany는 하나의 게시글을 중심으로 연결된 첨부파일들을 관리하고 ManyToOne은 첨부파일을 중심으로 여러개의 첨부파일이 하나의 게시글에 속하도록 설정한다.
4. cascade = CascadeType.ALL과 orphanRemoval = true는 어떤 역할을 하며, 실제 디스크에 저장된 파일에도 영향을 주는가?
   -
5. MultipartFile은 무엇이며, 업로드된 파일은 어떤 과정을 거쳐 서버에 저장되는가?
   - MultipartFile은 HTML Form을 통해 전송된 파일을 Spring에서 처리할 수 있도록 제공하는 인터페이스이다. Controller -> Service -> FileStorageService.store() 순서로 전달받아 검증후 저장한다.
6. 파일을 원본 이름 대신 UUID 기반 파일명으로 저장하는 이유는 무엇인가?
   - 파일이름이 중복되는 것을 방지하기 위해서이다.
7. 파일 다운로드 시 Resource, ResponseEntity, Content-Disposition은 각각 어떤 역할을 하는가?
   - Resource는 파일 읽기, ResponseEntity는 HTTP 구성, Content-Disposition은 브라우저에게 지시하는 역할을 한다.
8. 파일 저장 과정에서 normalize()와 startsWith()를 사용하는 이유는 무엇인가?
   -  경로를 정리하고 점검하여 잘못된 파일경로로 접근하는것을 방지할 수 있다.
