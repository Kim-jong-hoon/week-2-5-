## 첫번째 미션
🎯 Mission: 기본 플롯 만들기
조건:
1. Import: import matplotlib.pyplot as plt
2. 함수 정의: def setup_basic_plot(step_num=1, action="forward"):
3. 캔버스 크기: figsize=(10, 8)
4. 축 범위:
  X축: -1부터 8까지
  Y축: -1부터 12까지
5. 글자 크기: 라벨과 제목에 fontsize=12 사용
6. 레이아웃 최적화: plt.tight_layout() (show() 직전에)
7. 실행: if __name__ == "__main__": 안에서 setup_basic_plot(5, "turn_left") 호출
8. 추가 힌트:
  <br>함수는 ax 객체를 반환해야 함
  <br>plt.show()로 화면에 표시
  <br>f-string 사용해서 동적 제목 만들기

## 두번째 미션
📝 Mission: 목표선 그리기 함수 만들기
<br>🎯 조건:
1. Import: import matplotlib.pyplot as plt
2. 함수 정의: def draw_goal_line(obstacles):
    <br>매개변수: obstacles (장애물들의 집합/리스트)
3. 캔버스 설정:
   <br>-크기: figsize=(8, 6)
   <br>-축 범위: X(-18), Y(-112)
   <br>-격자: grid(True, alpha=0.3)
4. 목표선 계산:
  <br>-가장 높은 장애물의 Y좌표 찾기
  <br>-목표선 = 최대 Y좌표 + 3
  <br>-장애물이 없으면 Y=0 기준
5. 목표선 그리기:
  <br>-초록색 수평선 (color='lime')
  <br>-선 두께: linewidth=3
  <br>-투명도: alpha=0.7
6. 텍스트 표시:
  <br>-위치: (7, goal_y + 0.2)
  <br>-내용: f-string으로 "GOAL (y={goal_y})" 표시
  <br>-색상: 초록색
7. 완성 요소:
  <br>-범례 표시 (ax.legend())
  <br>-레이아웃 최적화
  <br>-화면 출력
  <br>-goal_y 값 반환
8. 실행:
  <br>obstacles = {(3, 2), (3, 3), (2, 4), (4, 5)} 사용
  <br>함수 호출해서 결과 확인
💡 힌트:
<br>ax.axhline(): 수평선 그리기
<br>max() 함수와 조건부 표현식 활용
<br>ax.text()의 ha, va 매개변수 사용

## 세번째 미션
📝 Mission: 장애물 그리기 함수 만들기
<br>🎯 조건:
1. Import:
  <br>-import matplotlib.pyplot as plt
  <br>-from matplotlib.patches import Rectangle
2. 함수 정의: def draw_obstacles(obstacles):
  <br> -매개변수: obstacles (장애물 위치들의 set 또는 list)
3. 캔버스 설정:
  <br>-크기: figsize=(8, 6)
  <br>-축 범위:
      <br>  1.ax.set_xlim(-1, 8)   # X축 범위: -1 ~ 8
      <br>  2.ax.set_ylim(-1, 12)  # Y축 범위: -1 ~ 12
  <br>-정사각형 비율: set_aspect('equal')
  <br>-격자와 라벨 설정
4. 데이터 처리:
  <br>-set을 list로 변환하여 순서 보장
  <br>-isinstance() 함수로 타입 확인
5. 장애물 그리기:
  <br>-빨간색 사각형 (color='red', alpha=0.7)
  <br>-크기: 0.8 x 0.8
  <br>-중심 좌표에서 0.4씩 빼서 위치 조정
  <br>-Rectangle 패치 사용
6. 텍스트 표시:
  <br>-각 장애물 중앙에 번호 (흰색, 굵은 글씨)
  <br>-enumerate() 함수로 번호 매기기
7. 완성 요소:
  <br>-범례 표시 (첫 번째 장애물에만 라벨)
  <br>-콘솔에 정보 출력
  <br>-레이아웃 최적화
8. 실행:
  <br>-obstacles = {(3, 2), (3, 3), (2, 4), (4, 5)} 사용
💡 핵심 힌트:
  <br>-Rectangle((x-0.4, y-0.4), 0.8, 0.8): 사각형 생성
  <br>-ax.add_patch(rect): 사각형을 그래프에 추가
  <br>-enumerate(): 인덱스와 값을 동시에 가져오기
<br>isinstance(obstacles, set): 타입 확인

## 네번째 미션
센서 빔들 그리기 # 📝 Mission: 센서 그리기 함수 만들기
🎯 조건:
1. 함수 정의:
  <br>-def draw_sensors(x, y, sensors):
2. 캔버스: figsize=(6, 5), 격자, 제목 "Sensors"
3. 차량 위치: 검은색 원점 'ko', markersize=15
4. 센서 선 그리기:
  <br>-전방: 'b-' (x, y) → (x, y + sensors['front'])
  <br>-좌측: 'g-' (x, y) → (x - sensors['left'], y)
  <br>-우측: 'r-' (x, y) → (x + sensors['right'], y)
  <br>-모든 선: linewidth=3

거리 텍스트 표시:
ax.text(x + 0.1, y + front_reach/2, f'{sensors["front"]:.1f}', color='blue', fontweight='bold')
센서 끝점 동그라미:# 센서 끝점에 점 표시
ax.plot(x, y + front_reach, 'bo', markersize=8) # 전방 끝점
최대 센서 길이 제한:
sensor_length = 3 # 최대 센서 길이 front_reach = min(sensors['front'], sensor_length)


## 지도학습과 자율주행의 연관성
 1. 지도 학습(Supervised Learning)과 자율주행의 연관성
  <br>지도 학습이란?

입력 데이터와 그에 대한 **정답(라벨)**이 함께 주어진 상태에서 모델을 학습시키는 방법입니다.

예: 이미지(고양이 사진) → 라벨(고양이)

자율주행에서 지도학습 활용 예시:

차선 인식: "이 이미지에 차선이 있다/없다"라는 라벨로 이미지 학습

객체 탐지: 보행자, 신호등, 차량 등을 정확히 인식하기 위한 학습

도로 표지판 인식: ‘정지’, ‘속도 제한’, ‘좌회전 금지’ 등의 표지판 분류

행동 예측: 다른 차량이나 보행자가 다음에 어떤 행동을 할지를 예측

📌 정리하면:

지도 학습은 자율주행차가 세상을 "이해"할 수 있도록 시각 정보 등을 분류/탐지하는 데 매우 중요한 역할을 합니다.
