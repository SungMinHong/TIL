# MSA(Microsevice Architecture)
- Monolithic과 반대되는 개념
- "시스템을 여러개의 독립된 서비스로 나눠서, 이 서비스를 조합함으로서 기능을 제공하는 아키텍쳐 디자인 패턴" (조대협)
- MSA에서는 코드 중복을 어느 정도 허용하는 편이다.(공통 모듈로 꼭 같이 쓸 필요는 없다는 의미..)

![Monolithic Architecture vs Microsevice Architecture](https://www.zirous.com/wp-content/uploads/2018/08/Microservice-Architecture-01.png)
- Monolithic Architecture
  - 책임소재가 불분명해 오너쉽이 떨어진다.
  - 규모가 커지면 배포조직이 필요하게되고 배포가 민첩하지 못하게 된다. (서비스 단위로 자유롭게 배포가 힘들어짐)
  - 의사소통이 힘들어진다.
  - 결국 개발자 만족도가 낮아진다.

## 실습
- Cloud Native 사용
- repo: https://github.com/SungMinHong/spring-cloud-workshop

### Cloud Native
- 클라우드 네이티브의 핵심은 애플리케이션을 어떻게 만들고 배포하는지에 있으며 위치는 중요하지 않다.
- 클라우드 서비스를 활용한다는 것은 컨테이너와 같이 민첩하고 확장가능한 구성 요소를 사용해서 재사용 가능한 개별적인 기능을 제공하는 것을 의미한다. 이러한 기능은 멀티클라우드와 같은 여러 기술 경계 간에 매끄럽게 통합되므로 제공팀이 반복 가능한 자동화와 오케스트레이션을 사용해서 빠르게 작업과정을 반복할 수 있다. (- 앤디 맨)
  - 신축성: 서비스가 중단이되더라도 인스턴스가 내려가더라도 전체적인 장애로 퍼지지 않고 빠르게 복구될 수 있는 성질 
  - 민첩성: 빠르고 독립적으로 배포할 수 있는 성질 
  - 확장 가능성: 스케일 아웃 가능한 성질
  - 자동화: 운영에 큰 수고 없이 자동으로 할 수 있는 성질
  - 무상태: 각 서비스의 상태는 상태가 없음

![DevOps](https://user-images.githubusercontent.com/18229419/66267356-e94fa880-e86a-11e9-8658-84676f818a5e.png)
- 같은 팀 내에서 개발하고 배포까지 할 수 있게만 해도 데브옵스 성격을 가짐

<br/>

![12가지 요소1](https://user-images.githubusercontent.com/18229419/66267358-f2d91080-e86a-11e9-8bc3-2e27ef403596.png)
![12가지 요소2](https://user-images.githubusercontent.com/18229419/66267442-bce85c00-e86b-11e9-9911-915a913a1469.png)
> 12가지 요소를 잘지키면 MSA를 하기 쉬워진다.

- L4장비 같은 경우 가격이 너무 비싸 개발환경에도 적용하기 쉽지 않고 이런 경우 개발환경과 실환경을 맞추기 쉽지 않다. 그래서 리본과 유레카를 이용해 L7에서 로드밸런싱을 하면 최대한 개발환경과 실환경을 비슷하게 유지할 수 있다.

### Netflix OSS
- TODO:: 이어서 정리

### Feign
![Feign url유무](https://user-images.githubusercontent.com/18229419/66500897-55e1d600-eafd-11e9-941f-4f63af82956f.png)
![Feign hystrix 사용](https://user-images.githubusercontent.com/18229419/66501962-5e3b1080-eaff-11e9-90d7-a200d2c3d042.png)


### spring-cloud-zuul
- defualt isolation은 semaphore이다
- semaphore로는 타임아웃 처리를 할 수 없다
- 쓰레드 생성 비용이 더 높지만 isolation을 타임아웃 처리가 가능한 Thread pool을 사용하는 것을 추천함

![isolation을 Thread pool로 사용](https://user-images.githubusercontent.com/18229419/66713738-99805c80-ede9-11e9-9e0b-9afff22dd375.png)

> 출처: [SKplanet Tacademy](https://www.youtube.com/watch?v=mJMzV6GCmPw)
