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
