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
    매개변수: obstacles (장애물들의 집합/리스트)
3. 캔버스 설정:
   -크기: figsize=(8, 6)
   -축 범위: X(-18), Y(-112)
   -격자: grid(True, alpha=0.3)
4. 목표선 계산:
  -가장 높은 장애물의 Y좌표 찾기
  -목표선 = 최대 Y좌표 + 3
  -장애물이 없으면 Y=0 기준
5. 목표선 그리기:
  -초록색 수평선 (color='lime')
  -선 두께: linewidth=3
  -투명도: alpha=0.7
6. 텍스트 표시:
  -위치: (7, goal_y + 0.2)
  -내용: f-string으로 "GOAL (y={goal_y})" 표시
  -색상: 초록색
7. 완성 요소:
  -범례 표시 (ax.legend())
  -레이아웃 최적화
  -화면 출력
  -goal_y 값 반환
8. 실행:
  obstacles = {(3, 2), (3, 3), (2, 4), (4, 5)} 사용
  함수 호출해서 결과 확인
💡 힌트:
ax.axhline(): 수평선 그리기
max() 함수와 조건부 표현식 활용
ax.text()의 ha, va 매개변수 사용
