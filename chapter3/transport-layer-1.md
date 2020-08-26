## 목차
- [목차](#목차)
- [Transport services and protocols](#transport-services-and-protocols)
- [Multiplexing/Demultiplexing](#multiplexingdemultiplexing)
  - [Demultiplexing](#demultiplexing)

## Transport services and protocols
network: host to host communication
transport: process to process communication 그 밖의 추가적인 기능(tcp의 reliability)

추가적인 기능
* tcp: reliable-in-order delivery
* congestion control은 네트워크 overwhelming을 막고 flow control은 리시버 버퍼의 overwhelming을 막는다
* udp: 네트웨크 계층의 서비스에 더 얹어주는 게 하나도 없다 호스트 딜리버리가 네트워크 계층에서 이루어지면 프로세스 딜리버리만 추가적으로 한다.

## Multiplexing/Demultiplexing

udp
여러 개의 프로세스에서 각자의 소켓을 통해 트랜스포트 계층으로 정보가 내려오면 메세지마다 목적지를 헤더에 더해 네트워크로 일렬로 내보내는데 이걸 muliplexing이라고 함

sender가 헤더에 더한 것으로 리시버에서는 demuliplexing을 한다.

### Demultiplexing

transport에서 만드는 data segment라고 부른다. 헤더와 payload 부분으로 이루어짐 
헤더에는 클라이언트 포트 넘버와 목적지 포트 넘버가 써있다. 네트워크에서 호트의 ip를 붙여주기 때문에 포트 넘버만

udp segment를 받으면 포트 번호 확인 후 해당 프로세스로 연결
포트 번호 만으로는 클라이언트 구분까지 할 수 없음 서버에서 클라이언트 주소를 extract 할 때 ip주소도 extract를 해야함
