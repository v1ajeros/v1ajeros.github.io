---
title:  "Bypassing GFW by Trojan"

categories:
  - GFW
tags:
  - Blog
last_modified_at: 2020-08-24T13:31:00+09:00
---

트로이라는 말을 들으면 먼저 "트로이 목마"라는 녀석이 연상된다. 아마 처음 이 녀석을 고안해낸 개발자도 그런 마음이었나보다. GFW가 점점 진화되어 가고, 수동적인 차단이 아닌 능동적인 차단까지 수행해내는 현재로서 보다 효율적으로 만리장성을 뛰어넘기 위해 이 기법(?)을 도입했는지도 모르겠다.

원리는 간단하다. GFW가 보기에 일반적인 HTTPS로 보이도록 하는 것이다. 그동안의 GFW의 우회가 강력한 암호화 기술이나 새로운 프로토콜을 개발했다면, 이건 그냥 딱 봐도 일반적인 HTTPS다.

trojan 클라이언트가 서버에 연결될 때, 마치 HTTPS와 같이 TLS handshake를 하고 성공하면 그 다음부터는 TLS를 통해 서로 통신하는 것이다. 자세한 프로토콜은 다음의 링크를 참고할 수 있다. ( [https://trojan-gfw.github.io/trojan/protocol](https://trojan-gfw.github.io/trojan/protocol) )

# Trojan installation

[https://github.com/trojan-gfw/trojan](https://github.com/trojan-gfw/trojan)

[https://github.com/p4gefau1t/trojan-go](https://github.com/p4gefau1t/trojan-go)

오리지널은 C++코드로 작성된 건데 최근엔 GO언어로 포팅된 녀석을 많이 사용한다. 특히 trojan-go의 경우 다른 잡다한 기능들도 있어 널리 애용된다.

설치는 간단하다. git clone한 뒤, 직접 컴파일해서 쓰거나 해당 github repository에 release page에 가서 자신의 machine에 맞는 바이너리를 다운로드하면 된다. 

# Trojan configuration