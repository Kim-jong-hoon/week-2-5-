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
🎯 조건:
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
