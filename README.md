d
--
머티리얼,라이팅 - 재질 
대기환경, 
포스트프로세스 - 카메라 이펙트
나이아가라 - VFX 이펙트
시퀀서, 애니메이션 리타겟팅
랜드스케이프


---02.20 시작 

점 섬 면 으로 이루어진 3D

점-vertex
선-edge
면-polygon , face

합치면 mesh 
ㄴdata O
ㄴ실체 X

material 
ㄴint float 숫자값
ㄴtexture 
2가지로 표현 가능

frame(하나의 필름) - Rendering(필름을 찍어내는 과정)
ㄴ 레벨(map)을 촬영

실시간과 비실시간의 차이

실시간- 게임,메타버스 _ 최적화 위주
비실시간 -영상,영화,전시  _ 퀄리티 위주

TA _ 프로그래머와 아트의 중간지점

원화가 _ 모델링시트 (캐릭터)
          ㄴ 배경
	ㄴ 몬스터

기획 - > 원화 - > 모델링 - >애니메이터 (모션캡쳐 결과 본 수정) -> 이펙터 -> UI
  [유저동선파악] - (레벨 디자이너)_모듈화  - > 팀장급 

원화 - 포토샵
모델러 - 3DSMax, Maya, [Blender]   - SubstacnePainter(서브스탠스페인터) ,Zbrush(하이폴리곤 프로그램)
애니 -  모델러랑 같은거씀 ( 최종 poly)
이펙터 - 엔진(언리얼, 유니티) _ 나이아가라 + 포토샵(이미지)
UI - 포토샵

로우폴리곤을 하이폴리곤처럼? - 노멀맵

PBR 시스템
ㄴPhysically based Redering or S = shader
 ㄴ 리얼한 요소를 간단하게 표현  - > base color, Ruughness, Metallic
					    ㄴ 거칠기

디지털 color
R, G, B + A
RED, GREEN, BLUE + ALPHA(투명도)

가산혼합 어두어줘짐 빛3색 + = 하얀색
감산혼합 밝아짐      색 3색 + = 검은색

0~255 으로 각 색 맞춤(보통)
0 ~ 1 100분율 ( 언리얼 )
0 블랙
1 화이트
 PNG 와 JPEG의 차이  Targa?

X Y Z 
R G B

metallic - 0 이면 비금속 1 이면 금속

확산 - Diffuse _ 색
(거친 표면)

정반사 -speceulse _ 빤짝이
(매끈)        - 

UV좌표 이걸 피면 UV 맵

Emissive Color - 자체발광 _ 다른 오브젝트에 영향을 주지 않음!
 ㄴ 언리얼은 영향을 주기 떄문에(5.2 업데이트) 루멘으로 조명을 줄 수 있음

Nvidia <-> AMD
ㄴDX	    ㄴOpenGl 
    (다이렉트 x) - GTX
	        ㄴRTX  _ RayTracing

RayTracing 을 써야 루멘을 제데로 쓸 수 있음

Noraml (법선)

------------------------------------------------
