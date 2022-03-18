# **Chart 관련 비교 보고서**

chart 관련 모듈 별로 기능 및 디자인, 사용법 등을 자료조사 하여 상세히 서술함  
추후 개발될 프로젝트에서 사용할 때 이 보고서를 참고하여 프로젝트 별로 어울리는 모듈을 찾아 적용시키기 위함

## **모듈 조사 기준 및 유의사항**

- vanilla javascript / react / Only opensource
- 어느정도 `공신력이 있는 라이브러리`로 (github star가 높다던가, 공식 홈페이지가 있다던가)
- `relation chart`를 제공하는 라이브러리 위주로 조사
- 라이브러리 별로 relation chart 외에 제공하는 `차트 종류` 조사  
  (line, bar, doughnut ...)
- canvas, svg 중 어떤 `방식`으로 구현 하였는지 조사
- Github 확인해서 어떤 라이브러리(p5.js, d3.js 등..)로 구현하였는지 조사
- 라이브러리들의 `공통 인터페이스 정리` (차트 설정, 데이터 입력, 제공 함수 등)

## **조사한 모듈 종류**

1. Recharts
2. React-chartjs-2
3. Visx
4. Antd-chart
5. Nivo
6. React vis
7. React-stockcharts
8. React time series charts

## **모듈별 호환 및 사용시 참고**

| module                   | documents | relation chart | canvas | svg | Dependency On |
| ------------------------ | --------- | -------------- | ------ | --- | ------------- |
| Recharts                 | O         | X              | X      | O   | O             |
| React-chartjs-2          | O         | X              | X      | O   | O             |
| Visx                     | O         | O              | X      | O   | O             |
| Antd-chart               | O         | O              | O      | X   | O             |
| Nivo                     | O         | O              | X      | O   | O             |
| React vis                | O         | X              | X      | O   | O             |
| React-stockcharts        | X         | X              | X      | O   | O             |
| React time series charts | O         | X              | X      | O   | O             |
