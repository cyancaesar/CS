- Enable testing the depth of objects: `GL_DEPTH_TEST`
- `glClear(GL_DEPTH_BUFFER_BIT)` before drawing
- Z-buffer known as depth

`gluLookAt(eyex, eyey, eyez, ax, ay, az, upx, upy, upz)` - to setup the camera in a 3D world (or eye)
`eye` location of the camera
`a*` aim of the camera
`up*` up-vector 

To produce perspective projection, we use `gluPerspective` or `glFrustum`

