# Part4. 네트워크 장비에 관한 이야기

## 랜카드의 역할
- 유저의 데이터를 케이블에 실어서 허브/스위치, 혹은 라우터에 전달하고 전달받은 데이터를 CPU에 전달.
- IRQ(Interrupt Request)의 값으로 CPU는 랜카드의 요청을 구분한다.

## 허브
- Multi-port Repeater: 한 포트에서 들어온 데이터를 나머지 포트에 뿌져주는 장치
- Repeater: 먼 거리 데이터를 전송할 때, AMP처럼 신호를 증폭해주는 역할을 하는 장치
- 하나의 허브에 연결된 모든 장치들은 Collision Domain을 공유합니다.
- 연결된 허브와 장치 수가 늘어날 수록 Collision Domain의 범위가 커짐에 따라 성능이 저하된다.
- 이를 해결하기 위하여 네트워크를 특정 시간 이상 점유하여 성능을 저하하는 장치의 포트를 ISOLATE하는 인텔리전트 허브가 고안되었다.
- 끝내 Collision Domain을 분리해줄 장치의 필요성이 대두되었다.

## 스위치
- 하나의 Collision Domain을 나누어 동시에 네트워크에 접근이 가능하도록 하는 장치

## 브리지
- 브리지의 경우 Collision Domain을 나누어 성능을 개선하고 나누어진 Collision Domain들을 연결하는 역할을 하는 장치이다.

## 브리지의 기능
- Learning: 데이터를 전송하고자 하는 장치의 MAC Address를 MAC Address Table에 저장하는 기능.
- Flooding: 멀티, 브로드 캐스트 및 전송하고자 하는 장치의 MAC Address를 모를 때 모든 장치에 브로드 캐스트를 하는 기능.
- Filtering: MAC Address Table을 기반으로 전달할 필요가 없는 세그먼트로 데이터를 전송하는 것을 막는 기능.
- Forwarding: 전달하고자 하는 장치가 포함된 세그먼트로 프레임을 뿌려주는 기능.
- Aging: 특정 시간 동안 사용되지 않은 MAC Address를 지우거나 Refreshing하는 기능.

## Looping
- 프레임이 무한정으로 네트워크에서 도는 현상.
- 이더넷의 경우 해당 Collision Domain 내에서의 통신이 불가능하다.

## Spanning Tree Algorithm
- 제가 알고있는 개념은 그래프 내의 모든 정점을 포함하지만 사이클이 없는 트리로 알고있습니다.
- 그래서 정점의 개수가 n개 일 때, 간선의 개수는 n -1개이고 모든 정점이 연결된걸로...
- 어쨌든, 네트워크가 스패닝 트리어야 looping이 발생하지 않습니다.
- 이를 위해서 복수의 스위치를 사용할 때, 평시에는 하나의 스위치만 활성화 되는 것으로 이해했습니다.

## Router
- 라우터는 브로드캐스트 도메인을 나눠주는 장치입니다.
- 또한, 데이터를 여러 경로를 통하여 전달을 할 수 있게 하는 로드 분배 기능도 있습니다.
- Collision Domain은 스위치, 브리지로 나눌 수 있지만, 라우터가 없다면 여전히 하나의 Broadcast Domain입니다.
- Broadcast를 나누지 않게 될 경우 CPU의 성능이 저하될 가능성이 높습니다.
