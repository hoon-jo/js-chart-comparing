# **recharts**

## **특징**

- Recharts는 가장 신뢰할 수 있는 차트 라이브러리 중 하나로 알려져 있으므로 전문가와 웹 개발자가 가장 많이 사용하는 차트 라이브러리
- D3에 가볍게 의존하는 라이브러리
- SVG 전체적으로 지원
- 쉽고 간단한 사용법으로 첫 차트 라이브러리로 적당함
- 컴포넌트 방식

> `relation chart` 없음

## **개인적인 장단점**

### **장점**

- 전체적인 문법이 간단하여 사용하기 쉬움.
- 문서에 자세히 나와있어 문서만 보고 코딩 가능
- 커스터마이징이 쉬움
- 차트당 다양한 접근 방식의 예제가 많아 선택의 자유가 높음

### **단점**

- 기본적인 디자인이 구림 (물론 커스터마이징 가능)

## **사용후기 및 의견**

첫 chart 도입 시 이 모듈을 사용했을정도로 인터넷에 제일 추천이 많고 그만큼 사용자가 많음  
그래서 차트를 만들다가 버그나 커스터 마이징 시 검색으로 빠르게 결과를 찾고 도입할 수 있음
하지만 기본적인 디자인이 구리므로(개인적 주관) 커스터마이징이 필요함.  
유연하고 가벼워서 커스터마이징 시 에로사항은 없지만, 하나하나 개별적으로 디자인 해줘야 하므로 기본 디자인 구성이 마음에 안든다면 커스터마이징 각오해야함.  
컴포넌트의 이름이나 프로퍼티의 이름이 직관적이어서 문서를 대충 봐도 어떻게 쓰는지 대충 이해하기 쉬움

## **기본적인 사용방법**

### **1. 대표적인 차트 컴포넌트**

`대부분의 데이터는 아래와 같은 배열 객체 타입으로 들어간다.`

```js
const data = [
  {
    "name": "Page A",
    "uv": 4000,
    "pv": 2400
  },
  {
    "name": "Page B",
    "uv": 3000,
    "pv": 1398
  },

  ...
]
```

### **1. Bar**

```html
<BarChart width="{730}" height="{250}" data="{data}">
  <CartesianGrid strokeDasharray="3 3" />
  <XAxis dataKey="name" />
  <YAxis />
  <Tooltip />
  <legend />
  <Bar dataKey="pv" fill="#8884d8" />
  <Bar dataKey="uv" fill="#82ca9d" />
</BarChart>
```

### **2. Line**

```html
<LineChart width={730} height={250} data={data}
  margin={{ top: 5, right: 30, left: 20, bottom: 5 }}>
  <CartesianGrid strokeDasharray="3 3" />
  <XAxis dataKey="name" />
  <YAxis />
  <Tooltip />
  <Legend />
  <Line type="monotone" dataKey="pv" stroke="#8884d8" />
  <Line type="monotone" dataKey="uv" stroke="#82ca9d" />
</LineChart>
```

### **3. Radar**

```html
<RadarChart outerRadius="{90}" width="{730}" height="{250}" data="{data}">
  <PolarGrid />
  <PolarAngleAxis dataKey="subject" />
  <PolarRadiusAxis angle="{30}" domain="{[0," 150]} />
  <Radar
    name="Mike"
    dataKey="A"
    stroke="#8884d8"
    fill="#8884d8"
    fillOpacity="{0.6}"
  />
  <Radar
    name="Lily"
    dataKey="B"
    stroke="#82ca9d"
    fill="#82ca9d"
    fillOpacity="{0.6}"
  />
  <legend />
</RadarChart>
```

### **4. Composed**

```html
<ComposedChart width="{730}" height="{250}" data="{data}">
  <XAxis dataKey="name" />
  <YAxis />
  <Tooltip />
  <legend />
  <CartesianGrid stroke="#f5f5f5" />
  <area type="monotone" dataKey="amt" fill="#8884d8" stroke="#8884d8" />
  <Bar dataKey="pv" barSize="{20}" fill="#413ea0" />
  <Line type="monotone" dataKey="uv" stroke="#ff7300" />
</ComposedChart>
```

### **1. 기타 지원 컴포넌트**

- ResponsiveContainer

  부모 객체의 크기나 포지션을 결정함

  ```html
  <ResponsiveContainer width="{700}" height="80%"> ... </ResponsiveContainer>
  ```

- Legend

  차트의 범례를 나타내고 기본적으로 dataKey의 이름을 따라감

  ```html
  <LineChart width={730} height={250} data={data}
  margin={{ top: 5, right: 30, left: 20, bottom: 5 }}>
    <XAxis dataKey="name" />
    <YAxis />
    <CartesianGrid strokeDasharray="3 3" />
    <Tooltip />
    <Legend verticalAlign="top" height={36}/>
    <Line name="pv of pages" type="monotone" dataKey="pv" stroke="#8884d8" />
    <Line name="uv of pages" type="monotone" dataKey="uv" stroke="#82ca9d" />
  </LineChart>
  ```

- Tooltip

  차트에 마우스 오버 시 나타나는 툴팁 설정

  ```html
  <Tooltip cursor="{false}" />
  <Tooltip cursor={{ stroke: 'red', strokeWidth: 2 }} />
  <Tooltip cursor="{<CustomizedCursor" />} />
  ```
