---
layout: post
title:  "Exploring the Gym and its
Features"
date:   2020-07-05 09:00:13
categories: OpenAI_Gym
permalink: /openaigym/ch4
---
이번 chapter에서는 Gym toolkit에서 제공되는 다양한 option들과 feature들에 대해 알아봅니다.
* Gym 환경 타입들
* Reinforcement learning의 loop 구조
* observation과 action space의 종류들
<!--more-->
---

# Exploring the list of environments and nomenclature
본격적으로 먼저 Open AI Gym에 어떤 environments들이 있는지 확인해봅시다.

```python
import gym
from gym import envs
env_names = [spec.id for spec in envs.registry.all()]
for name in sorted(env_names):
  print(name)
```

그러면 다음과 같이 알파벳 순으로 env 목록이 출력됩니다.
```
Acrobot-v1
Adventure-ram-v0
Adventure-ram-v4
Adventure-ramDeterministic-v0
Adventure-ramDeterministic-v4
Adventure-ramNoFrameskip-v0
Adventure-ramNoFrameskip-v4
Adventure-v0
...
ZaxxonDeterministic-v0
ZaxxonDeterministic-v4
ZaxxonNoFrameskip-v0
ZaxxonNoFrameskip-v4
```

env 목록을 보면 비슷한 이름들이 있는 것들을 볼 수 있습니다. 예를 들어 `Alien`이라는 단어가 들어간 environment는 8개가 있습니다. 여기서 8개는 다음에 소개할 명명법에서도 알 수 있듯이 조금씩만 다른 환경들입니다.

# Nomenclature
환경 명명법에 대해서 알아보자.

다음은 환경 이름에 붙는 옵션들이다.

* `ram`: Random Access Memory(RAM)의 내용으로 구성된 env
* `deterministic`:


|Version Name|Description|
|-|-|
|Alien-ram-v0|RAM data로 환경이 이루어져 있으며, |
|Alien-ram-v0|RAM data로 환경이 이루어져 있으며, |
|Alien-ram-v0|RAM data로 환경이 이루어져 있으며, |
|Alien-ram-v0|RAM data로 환경이 이루어져 있으며, |


# Exploring the Gym environments


```python
import gym
import sys
def run_gym_env(argv):
  env = gym.make(argv[1]) # Name of the environment supplied as 1st argument
  env.reset()
  for _ in range(int(argv[2])):
    env.render()
    env.step(env.action_space.sample())
  env.close()
if __name__ == "__main__":
  run_gym_env(sys.argv)
```

다음을 실행한 ipynb 파일은 [here]()을 참고하자.



# Understanding the Gym interface

강화학습에서 나오는 핵심용어들이 agent 와 environment 사이에는 어떻게 상호작용 하는지 살펴봅니다.

![image]("/assets/gym_ch4/image.png")


먼저 gym 라이브러리를 불러온 후, `import gym`

make를 이용해서 원하는 환경을 설정합니다.
`env = gym.make("ENVIRONMENT_NAME")`

Environment로부터 받은 값을 Observation(obs)라 정의하고, 초기상태의 obs는 다음과 같이 정의한다.

![image]("/assets/gym_ch4/image2.png")

...

|Returned value|Type|Description|
|-|-|-|
|next_state (or observation)|Object|설명설명~|
|next_state (or observation)|Object|설명설명~|
|next_state (or observation)|Object|설명설명~|

# Spaces in the Gym

|Space type|Description|Usage Example|
|-|-|-|
|Box|Object|`gym.spaces.Box(low=-100, high=100, shape=(2,))`|
|-|-|-|
|-|-|-|
|-|-|-|
|-|-|-|

전체 코드는 다음과 같다.
```python


```
|Index|Name/description|Min|Max|
|-|-|-|-|
|0|hull_angle|0|2*pi|
|-|-|-|-|
|-|-|-|-|



# Summary
