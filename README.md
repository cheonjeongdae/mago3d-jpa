# mago3d-jpa
mago3D 3.0. jpa, vue.js, rest api 

jpa 적용시 고려 할점

1. 중복이 되는 테이블
 - attribute, layer, data 같은 테이블은 
   공통 컬럼은 join 테이블에, 나머지는 각자에....
 - 한개로 통합하고, 구분만 두는것도 나쁘지 않음  
 - 대용량의 경우 속도가 문제가 되는데...... 이건 어떤게 좋을지 고민해 봐야 함
2. 테이블에 공통으로 사용되는 컬럼
 - BaseEntity 를 두고 상속 하자.

실무에서는 join 을 LAZY 만.... 즉시 가져와야 하는 경우는 fetch join

모든 연관 관계는 지연 로딩으로
@ManyToOne, @OneToOne 은 기본이 즉시 로딩이므로 지연 로딩으로 변경 
