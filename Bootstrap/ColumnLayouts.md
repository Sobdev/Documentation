### Simple example of three in to one
```javascript
      <Container>
        <Row>
          <Col xs={12} sm={12} md={4}>
            <h1>Columna 1</h1>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, doloremque. Quisquam, doloremque.</p>
          </Col>
          <Col xs={12} sm={12} md={4}>
            <h1>Columna 2</h1>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, doloremque. Quisquam, doloremque.</p>
          </Col>
          <Col xs={12} sm={12} md={4}>
            <h1>Columna 3</h1>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, doloremque. Quisquam, doloremque.</p>
          </Col>
        </Row>
      </Container>
```

### **Two Columns on Large, One Column on Small**
```javascript
<Container>
  <Row>
    <Col xs={12} lg={6}>
      <h1>Column 1</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, doloremque. Quisquam, doloremque.</p>
    </Col>
    <Col xs={12} lg={6}>
      <h1>Column 2</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, doloremque. Quisquam, doloremque.</p>
    </Col>
  </Row>
</Container>
```
**Explanation**: This layout has two columns on large screens (`lg`), but each column takes the full width on smaller screens (`xs`).

### **Three Columns on Medium, Two Columns on Small**
```javascript
<Container>
  <Row>
    <Col xs={6} sm={6} md={4}>
      <h1>Column 1</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, doloremque. Quisquam, doloremque.</p>
    </Col>
    <Col xs={6} sm={6} md={4}>
      <h1>Column 2</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, doloremque. Quisquam, doloremque.</p>
    </Col>
    <Col xs={12} sm={12} md={4}>
      <h1>Column 3</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, doloremque. Quisquam, doloremque.</p>
    </Col>
  </Row>
</Container>
```
**Explanation**: Three columns appear on medium screens (`md`), two columns on small screens (`sm`), and one column takes the full width on extra small screens (`xs`).

### **Four Columns on Large, Two Columns on Medium**
```javascript
<Container>
  <Row>
    <Col xs={12} sm={6} lg={3}>
      <h1>Column 1</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, doloremque. Quisquam, doloremque.</p>
    </Col>
    <Col xs={12} sm={6} lg={3}>
      <h1>Column 2</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, doloremque. Quisquam, doloremque.</p>
    </Col>
    <Col xs={12} sm={6} lg={3}>
      <h1>Column 3</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, doloremque. Quisquam, doloremque.</p>
    </Col>
    <Col xs={12} sm={6} lg={3}>
      <h1>Column 4</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, doloremque. Quisquam, doloremque.</p>
    </Col>
  </Row>
</Container>
```
**Explanation**: This layout has four columns on large screens (`lg`), but two columns per row on medium and small screens (`sm`), and one column on extra small screens (`xs`).

### **Two Unequal Columns (Two-Thirds, One-Third)**
```javascript
<Container>
  <Row>
    <Col xs={12} md={8}>
      <h1>Column 1 (2/3)</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, doloremque. Quisquam, doloremque.</p>
    </Col>
    <Col xs={12} md={4}>
      <h1>Column 2 (1/3)</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, doloremque. Quisquam, doloremque.</p>
    </Col>
  </Row>
</Container>
```
**Explanation**: On medium and larger screens, the first column takes up two-thirds of the width (`md=8`), and the second column takes one-third (`md=4`). On smaller screens (`xs`), both columns stack vertically.

### Example 5: **Responsive Grid with Different Content Alignments**
```javascript
<Container>
  <Row>
    <Col xs={12} md={6} className="text-center">
      <h1>Column 1</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, doloremque. Quisquam, doloremque.</p>
    </Col>
    <Col xs={12} md={6} className="text-right">
      <h1>Column 2</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, doloremque. Quisquam, doloremque.</p>
    </Col>
  </Row>
</Container>
```
**Explanation**: This layout displays two columns side by side on medium and larger screens (`md`), with text alignment set to the center for the first column and to the right for the second. On small screens (`xs`), the columns stack vertically and maintain their text alignment.