## OpenGL

OpenGL introductory commands for initialization.

Defining the *draw* function.

```cpp
void draw() {
	glClear(GL_COLOR_BUFFER_BIT);
	glFlush();
}
```

Defining an *init* function for windows background and coordinates.

```cpp
void init() {
	glClearColor(1,1,1,0);
	gluOrtho2D(-20,20,-20,20); // (xmin, xmax, ymin, ymax)
}
```

Defining main entry function.

```cpp
int main(int argc, char **argv) {
	glutInit(&argc, argv);
	glutInitDisplayMode(GLUT_SINGLE | GLUT_RGB);
	glutInitWindowSize(600, 600);
	glutInitWindowPosition(100, 100);
	glutCreateWindow("OpenGL window title");

	// Pass the address of drawing function to GLUT
	glutDisplayFunc(draw);
	init();
	glutMainLoop() // Start
}
```

---

OpenGL *glVertexDTv*

- D: 2 or 3 dimension
- T: integer (i), short (s), float (f), double (d)
- v: optional for vector points

Colors:
- *glColor3ub*: for setting primitive drawing color. Range (0, 255)
- *glColor3f*: same as above but range (0,.0 1.0)

## Drawing Point

```cpp
glColor3ub(255, 0, 0);
glPointSize(5.0) // Point size
glBegin(GL_POINTS);
	glVertex2i(2, 2);
	glVertex2i(2, 4);
	glVertex2i(2, 6);
glEnd();
```

## Drawing Lines

```cpp
glColor3ub(255, 0, 0);
glLineWidth(3.0);
// GL_LINES Normal line
// GL_LINE_STRIP Strip line
// GL_LINE_LOOP Loop line
glBegin(GL_LINES | GL_LINE_STRIP | GL_LINE_LOOP);
	glVertex2i(2, 2);
	glVertex2i(2, 4);
	glVertex2i(2, 6);
glEnd();
```

## Drawing Triangles

```cpp
glColor3ub(255, 0, 0);
glPolygonMode(GL_FRONT, fill_mode) // filled by default
glBegin(GL_TRIANGLES | GL_TRIANGLE_STRIP | GL_TRIANGLE_FAN);
	glVertex2i(2, 2);
	glVertex2i(2, 4);
	glVertex2i(2, 6);
glEnd();
```

## Drawing Quads, Rectangles and Polygons

```cpp
// GL_QUADS
// glRectf
// GL_POLYGON
```

