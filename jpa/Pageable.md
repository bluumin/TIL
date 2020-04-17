# Pageable

Pagable은 인터페이스다.

따라서 실제 사용할 때는 해당 인터페이스를 구현한 org.springframework.data.domain.PageRequest 객체를 사용한다.

PageRequest 생성자의 첫 번째 파라미터에는 현재 페이지를, 두 번째 파라미터에는 조회할 데이터 수를 입력한다.

여기에 추가로 정렬 정보도 파라미터로 사용할 수 있다.

참고로 페이지는 0부터 시작한다.

 



### Page 인터페이스

```java
public interface Page<T> extends Iterable<T> {
  int getNumber(); //현재 페이지
  int getSize(); //페이지 크기
  int getTotalPages(); //전체 페이지 수
  int getNumberOfElements(); //현재 페이지에 나올 데이터 수
  long getTotalElements(); //전체 데이터 수
  boolean hasPreviousPage(); //이전 페이지 여부
  boolean isFirstPage(); //현재 페이지가 첫 페이지 인지 여부
  boolean hasNextPage(); //다음 페이지 여부
  boolean isLastPage(); //현재 페이지가 마지막 페이지 인지 여부
  Pageable nextPageable(); //다음 페이지 객체, 다음 페이지가 없으면 null
  Pageable previousPageable();//다음 페이지 객체, 이전 페이지가 없으면 null
  List<T> getContent(); //조회된 데이터
  boolean hasContent(); //조회된 데이터 존재 여부
  Sort getSort(); //정렬 정보
}
```

