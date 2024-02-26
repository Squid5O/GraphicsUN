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

------------------------------------------------ 0221 수업

FBX는 크게 매쉬와 스켈레톤으로 나눠짐
Combine Meshes
mesh 가 합쳐져 있으면 그대로 가져오고 아니면 따로 가져온다.

0 ~ 1 값만 들어가는 
metallic rougheness occluison 은 RGB 하나만 써서 구현 가능
ㄴ merged texture
ㄴ 감마콜렉션(Gama Correction)

실제 수치의 그라데이션과 인간이 느끼는 그라데이션 색 느낌이 다름
ㄴ 이걸 보정하는게 감마콜렉션   - 기준 :sRGB -> HDR

머지드 택스쳐는 sRGB가 들어가기에 설정 꺼야함

인스턴스? 마테리얼을 복사하느 인스턴스가 용량이 적음 _ 최적화
마스터 마테리얼 - > 컨버트 파라미터 - > 인스턴스

노말맵은 2가지
ㄴOpenGL _ 유니티
ㄴDirectX _ 언리얼  
어디에 쓰는걸로 만들었느냐에 따라 노멀맵이 달라짐 _ 뒤집어짐
ㄴ 1-x 와 append 로 해결 가능

라이팅
뷰포트 
ㄴ 릿 : 빛이 보이는대로 보여줘
ㄴ 언릿 : 빛 상관없이 레벨 보여줘

포스트프로세싱 - 자동으로 이쁘게 만들어줌

Cast Shadow - 가려지는 부분 그림자 띄어줌
ㄴ 쓰면 계산 더 많이 들어감

직접광 간접광(반사되는거)   :  Lumen이 자연스럽게 해결
글로벌일루미네이션 - 간접광 

루멘은 개쩐다

삼중조명

quiexl brige  open close ( 다 만들어놈)
                 ㄴ 표면만 만들어놈

---
플레인에  풀 사진 넣어서 풀 넣기 가능. 빌보드( 플레이어 방향 회전으로 가라 가능)
Sky Atmospeher  - 오존 농도 변경 
ㄴGroundRadius _ 전체 크기  _ 유일하게 KM (나머지는 cm)
ㄴ 디폴트값 지구크기

ctrl+L  = 디렉션라이트 화면에서 수정

cubeMap

안개 - 공기원근법 _ ExponentialHeightFog 데이터 많이 잡아먹음 _공간감을 많이 줌
Volumetric FOg _ 이걸 해야 진짜 FOG

최적화 ㄱㄱ

LightMass - 최적화 : 전체가 아닌 그럴싸 하게 보여줌(임의의 도화지, 텕스쳐)
ㄴ 조건  _ 고정
1) actro static
2) ligth static 
3) actor 도화지- > UV map   , 
모든 액터는 UV 값이 있음 그걸 0 으로 하고 UV MAP을 1로 해서 중첩

project setting Rendering glbol illuminatnion - Lumen off 가능 _ reflaction
ㄴ ligth mass 후 light 지워도 유지됨 _ 대신 그림자도 유지
 = Luman 이후로 잘 안씀

포스트프로세스

이펙트 _ 나이아가라
ㄴ 스킬 이펙트 
ㄴ 환경 이펙트
ㄴ 카메라 이펙트 -> post process 

이펙트 = Effect = particle system = VFX

언리얼엔진은 나이아가라! - 이펙트를 만드는 시스템 
언리얼 엔진 4는 캐스케이드, 5는 나이아가라

effetct - 시관 괴물  , 러프 완벽 x

장르 : 폭팔, 전기, 파편
컨셉 : 불 , 물 , 전기, 독
환경 : 먼지, 안개
항상 크고 화려하게!

모닥불 분석 - 운동성, 색, 생성범위, 외형

나이아가라 시스템의 구성
복수 Emitter의 관리
	ㄴ particle

나이아가리 시스템 = 관제탑
Eimitter = 공장
particle = 생산품

spawn 생성 됐을때
update  살아가는 동안
Render 입자 

각각 스테이지라고 부름 

시간은 기본 초

XYZ
RGB

Liner color Curve

파티클은 애초에 작아서 이미지를 작게만듬 (100픽셀 넘기 힘듬)

불은 blend mode additive 
shading 은 빛 안밫게 ( 불 스스로 빛ㄹ으 냄)

랜덤화시키쟈

포스트프로세스

PostProcessVolume
ㄴBloom
ㄴChromatic Aberration


---------------------------------

02.23 

애니메이션, 컷씬

PostProcess  Manger?   = 렌더링 절차 _ Render Pipeline   - 디퍼드 방식 ( 지연 방식)

포스트프로세스는 이미지를 하나하나 때서 조정할 수 있다. Z-Buffer 

Compont Maks _ 특정 값만 삭제

블랜더 쉐이프

움직- > mesh
 
vertex 모션ㅐㅂ

cotrol rig

스켈레톤 내에서도 노드 사용

컨트롤리그 수정 and 애니메이션 모드  -> export

애니메이션 리타겟팅

forward Knemtiac 포워드 키네마틱 < - > 인버스 키네마틱  동작 애니메이션 순서

root bone 이 없을때 ㄴset root boon selected solver

레벨 시퀸스 - 시네마틱 만들기

CineCameraacotr 번개 모양  0 해당 카메라 샷에서만 스이는 스포너블 액터

camera - > rail 자식만들기 _상속

---02.026 마지막수업

위치 시퀸스

VR 렌드스케이프 쓰면 에러 지림

MESH _ 골목 ,동내 , 망르
Landscape _ 창동, 도봉구
open world) 시, 도


-------------------------

Mesh 최적화 _LOD

나나이트셋팅 

나나이트 키면 LOC 꺼지고 클러스터셋

