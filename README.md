# NOS-Client
Java Client Library for KiSTi NDSL NOS Open API(http://nos.ndsl.kr/)

한국과학기술연구원에서 제공하는 NDSL 검색서비스 OpenAPI를, Java를 이용한 개발에
사용할 때, 하부 HTTP 통신, 결과 XML 파싱 등을 신경쓰지 않고 이 Library의 Java 클래스를
사용하여 할 수 있게 하기 위한 목적.

처음이라 여러가지 생각이 떠 오르긴 하는데 뒤엉켜 있고 정리되지 않는다.

* 일단 기능 구현을 목표로 한다.
  - 성능, 확장성 등은 나중에
* 결국 하부는 HTTP 통신이다
  - 적절한 HTTP 클라이언트 Library가 필요하다
    * Apache HttpComponents Client?
    * 직접 짠다?
    * 아니면 또 다른 Library?
* java.concurrency 패키지를 이용해 보자
  - Excutor, Callable, Future
* Generic을 활용할 거다. 그러니 당연히 Java는 5 버전 이상에서 동작한다.
* LICENSE는 LGPL v.3 로 변경:
  - 쓸 사람이 있을래나? ^^;
  - 아시죠? 문제 있으면 알아서.

## ver. 0.2.1

* 논문 검색 결과 XML에서 record/journalInfo/volume[seqno] 값을 설정할 수 있도록
  NdslJournal 클래스에 volumeSeqNo 및 getter/setter 추가
  - 이에 맞추어 INdslJournal 인터페이스에 getVolumeSeqNo() 추가
* 로그를 위해서 System.out.println으로 출력하던 부분을 java.util.logging 을
  이용하는 것으로 수정

## ver. 0.2

* 저널(Journal), 논문(Article), 저자(Author), 학위논문(Dissertation)을 담는
  클래스로부터 Interface를 추출하였다.
* 아직 Alpha 단계라 할 수 있어 변화가 심하다. 사용하시는 분은 유의 하시길.

