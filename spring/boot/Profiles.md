# Profiles

1. 테스트 클래스에 Annotation 추가
   @ActiveProfiles("test")

2. 환경 변수로 설정
   \# Linux, Mac 등
   SPRING_PROFILES_ACTIVE=test ./gradlew cleanTest test

   \# (또는)
   export SPRING_PROFILES_ACTIVE=test
   ./gradlew cleanTest test

   \# Windows
   set SPRING_PROFILES_ACTIVE=test
   gradlew.bat cleanTest test

3. Run Configurations 설정
   ![image-20200518185253230](/Users/bluuminn/Library/Application Support/typora-user-images/image-20200518185253230.png)

   > Environment variables에 SPRING_PROFILES_ACTIVE='어떤 설정 사용할 것인지 적어줌'

   ![image-20200518185442346](/Users/bluuminn/Library/Application Support/typora-user-images/image-20200518185442346.png)

   > application.yml 에 spring.profiles로 만들어둔 설정 값을 적어주면 됨.
   >
   > 여기서는 application.yml의 dev 라는  환경 설정을 사용할 거라서 Run Configuration에서 dev로 적어준 것..
   >
   > application.yml에는 여러 상황의 환경 설정을 따로 해줄 수 있다.
   >
   > ​	ex) local, dev, operation, ...

