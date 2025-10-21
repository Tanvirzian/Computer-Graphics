#include <windows.h>  // for MS Windows
#include <GL/glut.h>  // GLUT, include glu.h and gl.h
#include<math.h>>
# define PI           3.14159265358979323846





GLfloat position = 0.0f;
GLfloat speed = 0.003f;

GLfloat position2 = 0.0f;//for the 1st  boat of river
GLfloat speed2 = -0.005f;//for the 1st  boat of river


GLfloat position3 = 0.0f;
GLfloat speed3 = 0.001f;


GLfloat position4 = 0.0f;
GLfloat speed4 = -0.02f;


void update(int value)
{

    if(position >2)
        position = -0.6f;

    position += speed; //position=position-speed;1-.1=.9

    glutPostRedisplay();


    glutTimerFunc(100, update, 0);
}





void update2(int value)
{

    if(position2 <-1.5)
        position2 = 0.8f;

    position2 += speed2; //position=position-speed;1-.1=.9

    glutPostRedisplay();


    glutTimerFunc(100, update2, 0);
}




void update3(int value)
{

    if(position3 <-1.5)
        position3 = 0.8f;

    position3 += speed3; //position=position-speed;1-.1=.9

    glutPostRedisplay();


    glutTimerFunc(100, update3, 0);
}



void update4(int value)
{

    if(position4 <-1.9)
        position4 = 0.2f;

    position4 += speed4; //position=position-speed;1-.1=.9

    glutPostRedisplay();


    glutTimerFunc(100, update4, 0);
}



int flag =2;
int night =0;

void city()
{



    glClearColor(0.0f, 0.0f, 0.0f, 1.0f);
    glClear(GL_COLOR_BUFFER_BIT);

    glLineWidth(3);


    //glutPostRedisplay();

    glBegin(GL_QUADS);//Sky
    glColor3ub(135,206,235);
    glVertex2f(1, 1);
    glVertex2f(-1,1);
    glVertex2f(-1,-0.2);
    glVertex2f(1,-0.2);
    glEnd();






    glBegin(GL_QUADS);//sand //sand
    glColor3ub(203,189,147);
    glVertex2f(1, 0.25);
    glVertex2f(-1,0.25);
    glVertex2f(-1,-0.2);
    glVertex2f(1,-0.2);
    glEnd();



    glBegin(GL_QUADS);//Road
    glColor3ub(58,61,62);
    glVertex2f(1, -0.0);
    glVertex2f(-1,-0.0);
    glVertex2f(-1,-0.3);
    glVertex2f(1,-0.3);
    glEnd();




    glBegin(GL_QUADS);//Grass
    glColor3ub(126,200,80);
    glVertex2f(1, -0.3);
    glVertex2f(-1,-0.3);
    glVertex2f(-1,-0.37);
    glVertex2f(1,-0.37);
    glEnd();

    glBegin(GL_QUADS);//water water
    glColor3ub(0,84,147);
    glVertex2f(1, -0.35);
    glVertex2f(-1,-0.35);
    glVertex2f(-1,-1);
    glVertex2f(1,-1);
    glEnd();



    glPushMatrix();
    glTranslatef(0,-0.05,0);

    glBegin(GL_QUADS);//white shadow 1
    glColor3ub(255,255,255);
    glVertex2f(-0.80, -0.06);
    glVertex2f(-1,-0.06);
    glVertex2f(-1,-0.09);
    glVertex2f(-0.80,-0.09);
    glEnd();

    glBegin(GL_QUADS);//white shadow 2
    glColor3ub(255,255,255);
    glVertex2f(-0.50, -0.06);
    glVertex2f(-0.70,-0.06);
    glVertex2f(-0.70,-0.09);
    glVertex2f(-0.50,-0.09);
    glEnd();


    glBegin(GL_QUADS);//white shadow3
    glColor3ub(255,255,255);
    glVertex2f(-0.20, -0.06);
    glVertex2f(-0.40,-0.06);
    glVertex2f(-0.40,-0.09);
    glVertex2f(-0.20,-0.09);
    glEnd();

    glBegin(GL_QUADS);//white shadow4
    glColor3ub(255,255,255);
    glVertex2f(0.1, -0.06);
    glVertex2f(-0.1,-0.06);
    glVertex2f(-0.1,-0.09);
    glVertex2f(0.1,-0.09);
    glEnd();


    glBegin(GL_QUADS);//white shadow5
    glColor3ub(255,255,255);
    glVertex2f(0.4, -0.06);
    glVertex2f(0.2,-0.06);
    glVertex2f(0.2,-0.09);
    glVertex2f(0.4,-0.09);
    glEnd();


    glBegin(GL_QUADS);//white shadow6
    glColor3ub(255,255,255);
    glVertex2f(0.7, -0.06);
    glVertex2f(0.5,-0.06);
    glVertex2f(0.5,-0.09);
    glVertex2f(0.7,-0.09);
    glEnd();

    glBegin(GL_QUADS);//white shadow7
    glColor3ub(255,255,255);
    glVertex2f(1, -0.06);
    glVertex2f(0.8,-0.06);
    glVertex2f(0.8,-0.09);
    glVertex2f(1,-0.09);
    glEnd();

    glPopMatrix();





    glBegin(GL_QUADS);//ATC tower start
    glColor3ub(227,220,208);
    glVertex2f(-0.8, 0.65);
    glVertex2f(-0.9,0.65);
    glVertex2f(-0.9,0.25);
    glVertex2f(-0.8,0.25);
    glEnd();


    glBegin(GL_QUADS);//ATC tower start
    glColor3ub(227,220,208);
    glVertex2f(-0.75, 0.75);
    glVertex2f(-0.95,0.75);
    glVertex2f(-0.95,0.65);
    glVertex2f(-0.75,0.65);
    glEnd();







    //car //car

    //mini car///mini car///mini car///mini car///mini car///mini car/


    glPushMatrix();
    glTranslatef(position4,0.0,0.0);

    glPushMatrix();
    glTranslatef(0,0.27,0);


    glBegin(GL_QUADS);//
    glColor3ub(255, 0, 0);
    glVertex2f(0.7, -0.32);
    glVertex2f(0.6,-0.35);
    glVertex2f(0.6,-0.42);
    glVertex2f(0.7, -0.42);
    glEnd();


    glBegin(GL_QUADS);//
    glColor3ub(255, 0, 0);
    glVertex2f(0.9, -0.35);
    glVertex2f(0.7,-0.35);
    glVertex2f(0.7,-0.42);
    glVertex2f(0.9, -0.42);
    glEnd();


    glLineWidth(3);
    glBegin(GL_LINES);//
    glColor3ub(255,0,0);
    glVertex2f(0.77, -0.3);
    glVertex2f(0.75,-0.42);
    glEnd();


    glBegin(GL_QUADS);//
    glColor3ub(255,0,0);
    glVertex2f(0.9, -0.33);
    glVertex2f(0.82,-0.33);
    glVertex2f(0.8,-0.42);
    glVertex2f(0.9, -0.42);
    glEnd();



//
//    wheel//wheel//wheel//wheel//wheel//wheel//wheel//


    GLfloat xc=0.82;
    GLfloat yc=-0.42;
    GLfloat radiusc =.037f;
    GLfloat triangleAmountc = 20; //# of triangles used to draw circle# of triangles used to draw circle# of triangles used to draw circle

    //GLfloat radius = 0.8f; //radius
    GLfloat twicePic = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3ub(0,0,0);
    glVertex2f(xc, yc); // center of circle
    for(int i = 0; i <= triangleAmountc; i++)
    {
        glVertex2f(
            xc + (radiusc * cos(i *  twicePic / triangleAmountc)),
            yc + (radiusc * sin(i * twicePic / triangleAmountc))
        );
    }
    glEnd();


    xc=0.82;
    yc=-0.42;
    radiusc =.019f;
    triangleAmountc = 20; //# of triangles used to draw circle# of triangles used to draw circle# of triangles used to draw circle

    //GLfloat radius = 0.8f; //radius
    twicePic = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3ub(164,141,12);
    glVertex2f(xc, yc); // center of circle
    for(int i = 0; i <= triangleAmountc; i++)
    {
        glVertex2f(
            xc + (radiusc * cos(i *  twicePic / triangleAmountc)),
            yc + (radiusc * sin(i * twicePic / triangleAmountc))
        );
    }
    glEnd();


    //    wheel//wheel//wheel//wheel//wheel//wheel//wheel//


    xc=0.68;
    yc=-0.42;
    radiusc =.037f;
    triangleAmountc = 20; //# of triangles used to draw circle# of triangles used to draw circle# of triangles used to draw circle

    //GLfloat radius = 0.8f; //radius
    twicePic = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3ub(0,10,0);
    glVertex2f(xc, yc); // center of circle
    for(int i = 0; i <= triangleAmountc; i++)
    {
        glVertex2f(
            xc + (radiusc * cos(i *  twicePic / triangleAmountc)),
            yc + (radiusc * sin(i * twicePic / triangleAmountc))
        );
    }
    glEnd();
//
//
    xc=0.68;
    yc=-0.42;
    radiusc =.019f;
    triangleAmountc = 20; //# of triangles used to draw circle# of triangles used to draw circle# of triangles used to draw circle

    //GLfloat radius = 0.8f; //radius
    twicePic = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3ub(164,141,12);
    glVertex2f(xc, yc); // center of circle
    for(int i = 0; i <= triangleAmountc; i++)
    {
        glVertex2f(
            xc + (radiusc * cos(i *  twicePic / triangleAmountc)),
            yc + (radiusc * sin(i * twicePic / triangleAmountc))
        );
    }
    glEnd();


    glPopMatrix();
    glPopMatrix();

////car end //car end////car end //car end////car end //car end////car end //car end////car end //car end


    //circle 1
    int i;
    GLfloat x=-0.85;
    GLfloat y=0.81;
    GLfloat radius =.06f;
    int triangleAmount = 20; //# of triangles used to draw circle# of triangles used to draw circle# of triangles used to draw circle

    //GLfloat radius = 0.8f; //radius
    GLfloat twicePi = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3ub(255,145,109);
    glVertex2f(x, y); // center of circle
    for(i = 0; i <= triangleAmount; i++)
    {
        glVertex2f(
            x + (radius * cos(i *  twicePi / triangleAmount)),
            y + (radius * sin(i * twicePi / triangleAmount))
        );
    }
    glEnd();


    glBegin(GL_QUADS);//Large Building//Large Building//Large Building//Large Building//Large Building
    glColor3ub(114,93,83);
    glVertex2f(0.5, 0.65);
    glVertex2f(-0.0,0.65);
    glVertex2f(-0.0,0.25);
    glVertex2f(0.5,0.25);
    glEnd();


    glBegin(GL_LINES);//black 1st line
    glColor3f(0,0,0);
    glVertex2f(0.5, 0.65);
    glVertex2f(0.0, 0.65);
    glEnd();

    glBegin(GL_LINES);//black 2nd line
    glColor3f(0,0,0);
    glVertex2f(0.5, 0.5);
    glVertex2f(0.0, 0.5);
    glEnd();

    glBegin(GL_LINES);//black 3rd line
    glColor3f(0,0,0);
    glVertex2f(0.5, 0.35);
    glVertex2f(0.0, 0.35);
    glEnd();

    glBegin(GL_LINES);//black y axis  line
    glColor3f(0,0,0);
    glVertex2f(0.25, 0.65);
    glVertex2f(0.25, 0.35);
    glEnd();


    glBegin(GL_QUADS);//door
    glColor3ub(205,153,130);
    glVertex2f(0.32, 0.33);
    glVertex2f(0.17,0.33);
    glVertex2f(0.17,0.25);
    glVertex2f(0.32,0.25);
    glEnd();



    glBegin(GL_QUADS);//mini window 1
    glColor3ub(228,228,228);
    glVertex2f(0.14, 0.59);
    glVertex2f(0.07,0.59);
    glVertex2f(0.07,0.54);
    glVertex2f(0.14, 0.54);
    glEnd();

    glBegin(GL_QUADS);//mini window 2
    glColor3ub(228,228,228);
    glVertex2f(0.43, 0.59);
    glVertex2f(0.36,0.59);
    glVertex2f(0.36,0.54);
    glVertex2f(0.43, 0.54);
    glEnd();


    glBegin(GL_QUADS);//mini window 3
    glColor3ub(228,228,228);
    glVertex2f(0.14, 0.44);
    glVertex2f(0.07,0.44);
    glVertex2f(0.07,0.39);
    glVertex2f(0.14, 0.39);
    glEnd();

    glBegin(GL_QUADS);//mini window 4
    glColor3ub(228,228,228);
    glVertex2f(0.43, 0.44);
    glVertex2f(0.36,0.44);
    glVertex2f(0.36,0.39);
    glVertex2f(0.43, 0.39);
    glEnd();

    glBegin(GL_QUADS);//mini Building//mini Building//mini Building//mini Building//mini Building
    glColor3ub(114,93,83);
    glVertex2f(-0.05, 0.5);
    glVertex2f(-0.5,0.5);
    glVertex2f(-0.5,0.25);
    glVertex2f(-0.05,0.25);
    glEnd();

    glBegin(GL_LINES);//black 1st line
    glColor3f(0,0,0);
    glVertex2f(-0.05, 0.5);
    glVertex2f(-0.5, 0.5);
    glEnd();

    glBegin(GL_LINES);////black 2nd  line
    glColor3f(0,0,0);
    glVertex2f(-0.05, 0.35);
    glVertex2f(-0.5, 0.35);
    glEnd();

    glBegin(GL_LINES);//black y axis  line
    glColor3f(0,0,0);
    glVertex2f(-0.27, 0.5);
    glVertex2f(-0.27, 0.35);
    glEnd();


    glBegin(GL_QUADS);//door
    glColor3ub(205,153,130);
    glVertex2f(-0.19, 0.31);
    glVertex2f(-0.34,0.31);
    glVertex2f(-0.34,0.25);
    glVertex2f(-0.19, 0.25);
    glEnd();


    glBegin(GL_QUADS);//mini window 1
    glColor3ub(228,228,228);
    glVertex2f(-0.37, 0.44);
    glVertex2f(-0.44,0.44);
    glVertex2f(-0.44,0.39);
    glVertex2f(-0.37, 0.39);
    glEnd();

    glBegin(GL_QUADS);//mini window 2
    glColor3ub(228,228,228);
    glVertex2f(-0.12, 0.44);
    glVertex2f(-0.19,0.44);
    glVertex2f(-0.19,0.39);
    glVertex2f(-0.12, 0.39);
    glEnd();

    //Sun //Sun//Sun//Sun//Sun//Sun//Sun
    i=0;
    x=0.85;
    y=0.9;
    radius =.103f;
    triangleAmount = 20; //# of triangles used to draw circle# of triangles used to draw circle# of triangles used to draw circle

    //GLfloat radius = 0.8f; //radius
    twicePi = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3ub(249,215,28);
    glVertex2f(x, y); // center of circle
    for(i = 0; i <= triangleAmount; i++)
    {
        glVertex2f(
            x + (radius * cos(i *  twicePi / triangleAmount)),
            y + (radius * sin(i * twicePi / triangleAmount))
        );
    }
    glEnd();


    glFlush();

    flag = 1;

}




void nightCity()
{



    glClearColor(0.0f, 0.0f, 0.0f, 1.0f);
    glClear(GL_COLOR_BUFFER_BIT);

    glLineWidth(3);


    //glutPostRedisplay();


    //night sky//night sky//night sky//night sky//night sky
    glBegin(GL_QUADS);//Sky
    glColor3ub(19,24,98);
    glVertex2f(1, 1);
    glVertex2f(-1,1);
    glVertex2f(-1,-0.2);
    glVertex2f(1,-0.2);
    glEnd();






    glBegin(GL_QUADS);//sand //sand
    glColor3ub(203,189,147);
    glVertex2f(1, 0.25);
    glVertex2f(-1,0.25);
    glVertex2f(-1,-0.2);
    glVertex2f(1,-0.2);
    glEnd();



    glBegin(GL_QUADS);//Road
    glColor3ub(58,61,62);
    glVertex2f(1, -0.0);
    glVertex2f(-1,-0.0);
    glVertex2f(-1,-0.3);
    glVertex2f(1,-0.3);
    glEnd();




    glBegin(GL_QUADS);//Grass
    glColor3ub(126,200,80);
    glVertex2f(1, -0.3);
    glVertex2f(-1,-0.3);
    glVertex2f(-1,-0.37);
    glVertex2f(1,-0.37);
    glEnd();

    glBegin(GL_QUADS);//water water
    glColor3ub(0,84,147);
    glVertex2f(1, -0.35);
    glVertex2f(-1,-0.35);
    glVertex2f(-1,-1);
    glVertex2f(1,-1);
    glEnd();



    glPushMatrix();
    glTranslatef(0,-0.05,0);

    glBegin(GL_QUADS);//white shadow 1
    glColor3ub(255,255,255);
    glVertex2f(-0.80, -0.06);
    glVertex2f(-1,-0.06);
    glVertex2f(-1,-0.09);
    glVertex2f(-0.80,-0.09);
    glEnd();

    glBegin(GL_QUADS);//white shadow 2
    glColor3ub(255,255,255);
    glVertex2f(-0.50, -0.06);
    glVertex2f(-0.70,-0.06);
    glVertex2f(-0.70,-0.09);
    glVertex2f(-0.50,-0.09);
    glEnd();


    glBegin(GL_QUADS);//white shadow3
    glColor3ub(255,255,255);
    glVertex2f(-0.20, -0.06);
    glVertex2f(-0.40,-0.06);
    glVertex2f(-0.40,-0.09);
    glVertex2f(-0.20,-0.09);
    glEnd();

    glBegin(GL_QUADS);//white shadow4
    glColor3ub(255,255,255);
    glVertex2f(0.1, -0.06);
    glVertex2f(-0.1,-0.06);
    glVertex2f(-0.1,-0.09);
    glVertex2f(0.1,-0.09);
    glEnd();


    glBegin(GL_QUADS);//white shadow5
    glColor3ub(255,255,255);
    glVertex2f(0.4, -0.06);
    glVertex2f(0.2,-0.06);
    glVertex2f(0.2,-0.09);
    glVertex2f(0.4,-0.09);
    glEnd();


    glBegin(GL_QUADS);//white shadow6
    glColor3ub(255,255,255);
    glVertex2f(0.7, -0.06);
    glVertex2f(0.5,-0.06);
    glVertex2f(0.5,-0.09);
    glVertex2f(0.7,-0.09);
    glEnd();

    glBegin(GL_QUADS);//white shadow7
    glColor3ub(255,255,255);
    glVertex2f(1, -0.06);
    glVertex2f(0.8,-0.06);
    glVertex2f(0.8,-0.09);
    glVertex2f(1,-0.09);
    glEnd();

    glPopMatrix();





    glBegin(GL_QUADS);//ATC tower start
    glColor3ub(227,220,208);
    glVertex2f(-0.8, 0.65);
    glVertex2f(-0.9,0.65);
    glVertex2f(-0.9,0.25);
    glVertex2f(-0.8,0.25);
    glEnd();


    glBegin(GL_QUADS);//ATC tower start
    glColor3ub(227,220,208);
    glVertex2f(-0.75, 0.75);
    glVertex2f(-0.95,0.75);
    glVertex2f(-0.95,0.65);
    glVertex2f(-0.75,0.65);
    glEnd();







    //car //car

    //mini car///mini car///mini car///mini car///mini car///mini car/


    glPushMatrix();
    glTranslatef(position4,0.0,0.0);

    glPushMatrix();
    glTranslatef(0,0.27,0);


    glBegin(GL_QUADS);//
    glColor3ub(255, 0, 0);
    glVertex2f(0.7, -0.32);
    glVertex2f(0.6,-0.35);
    glVertex2f(0.6,-0.42);
    glVertex2f(0.7, -0.42);
    glEnd();


    glBegin(GL_QUADS);//
    glColor3ub(255, 0, 0);
    glVertex2f(0.9, -0.35);
    glVertex2f(0.7,-0.35);
    glVertex2f(0.7,-0.42);
    glVertex2f(0.9, -0.42);
    glEnd();


    glLineWidth(3);
    glBegin(GL_LINES);//
    glColor3ub(255,0,0);
    glVertex2f(0.77, -0.3);
    glVertex2f(0.75,-0.42);
    glEnd();


    glBegin(GL_QUADS);//
    glColor3ub(255,0,0);
    glVertex2f(0.9, -0.33);
    glVertex2f(0.82,-0.33);
    glVertex2f(0.8,-0.42);
    glVertex2f(0.9, -0.42);
    glEnd();



//    wheel//wheel//wheel//wheel//wheel//wheel//wheel//


    GLfloat xc=0.82;
    GLfloat yc=-0.42;
    GLfloat radiusc =.037f;
    GLfloat triangleAmountc = 20; //# of triangles used to draw circle# of triangles used to draw circle# of triangles used to draw circle

    //GLfloat radius = 0.8f; //radius
    GLfloat twicePic = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3ub(0,0,0);
    glVertex2f(xc, yc); // center of circle
    for(int i = 0; i <= triangleAmountc; i++)
    {
        glVertex2f(
            xc + (radiusc * cos(i *  twicePic / triangleAmountc)),
            yc + (radiusc * sin(i * twicePic / triangleAmountc))
        );
    }
    glEnd();


    xc=0.82;
    yc=-0.42;
    radiusc =.019f;
    triangleAmountc = 20; //# of triangles used to draw circle# of triangles used to draw circle# of triangles used to draw circle

    //GLfloat radius = 0.8f; //radius
    twicePic = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3ub(164,141,12);
    glVertex2f(xc, yc); // center of circle
    for(int i = 0; i <= triangleAmountc; i++)
    {
        glVertex2f(
            xc + (radiusc * cos(i *  twicePic / triangleAmountc)),
            yc + (radiusc * sin(i * twicePic / triangleAmountc))
        );
    }
    glEnd();


    //    wheel//wheel//wheel//wheel//wheel//wheel//wheel//


    xc=0.68;
    yc=-0.42;
    radiusc =.037f;
    triangleAmountc = 20; //# of triangles used to draw circle# of triangles used to draw circle# of triangles used to draw circle

    //GLfloat radius = 0.8f; //radius
    twicePic = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3ub(0,10,0);
    glVertex2f(xc, yc); // center of circle
    for(int i = 0; i <= triangleAmountc; i++)
    {
        glVertex2f(
            xc + (radiusc * cos(i *  twicePic / triangleAmountc)),
            yc + (radiusc * sin(i * twicePic / triangleAmountc))
        );
    }
    glEnd();
//
//
    xc=0.68;
    yc=-0.42;
    radiusc =.019f;
    triangleAmountc = 20; //# of triangles used to draw circle# of triangles used to draw circle# of triangles used to draw circle

    //GLfloat radius = 0.8f; //radius
    twicePic = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3ub(164,141,12);
    glVertex2f(xc, yc); // center of circle
    for(int i = 0; i <= triangleAmountc; i++)
    {
        glVertex2f(
            xc + (radiusc * cos(i *  twicePic / triangleAmountc)),
            yc + (radiusc * sin(i * twicePic / triangleAmountc))
        );
    }
    glEnd();


    glPopMatrix();
    glPopMatrix();

////car end //car end////car end //car end////car end //car end////car end //car end////car end //car end


    //circle 1
    int i;
    GLfloat x=-0.85;
    GLfloat y=0.81;
    GLfloat radius =.06f;
    int triangleAmount = 20; //# of triangles used to draw circle# of triangles used to draw circle# of triangles used to draw circle

    //GLfloat radius = 0.8f; //radius
    GLfloat twicePi = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3ub(250,212,20);
    glVertex2f(x, y); // center of circle
    for(i = 0; i <= triangleAmount; i++)
    {
        glVertex2f(
            x + (radius * cos(i *  twicePi / triangleAmount)),
            y + (radius * sin(i * twicePi / triangleAmount))
        );
    }
    glEnd();


    glBegin(GL_QUADS);//Large Building//Large Building//Large Building//Large Building//Large Building
    glColor3ub(114,93,83);
    glVertex2f(0.5, 0.65);
    glVertex2f(-0.0,0.65);
    glVertex2f(-0.0,0.25);
    glVertex2f(0.5,0.25);
    glEnd();


    glBegin(GL_LINES);//black 1st line
    glColor3f(0,0,0);
    glVertex2f(0.5, 0.65);
    glVertex2f(0.0, 0.65);
    glEnd();

    glBegin(GL_LINES);//black 2nd line
    glColor3f(0,0,0);
    glVertex2f(0.5, 0.5);
    glVertex2f(0.0, 0.5);
    glEnd();

    glBegin(GL_LINES);//black 3rd line
    glColor3f(0,0,0);
    glVertex2f(0.5, 0.35);
    glVertex2f(0.0, 0.35);
    glEnd();

    glBegin(GL_LINES);//black y axis  line
    glColor3f(0,0,0);
    glVertex2f(0.25, 0.65);
    glVertex2f(0.25, 0.35);
    glEnd();


    glBegin(GL_QUADS);//door
    glColor3ub(205,153,130);
    glVertex2f(0.32, 0.33);
    glVertex2f(0.17,0.33);
    glVertex2f(0.17,0.25);
    glVertex2f(0.32,0.25);
    glEnd();



    glBegin(GL_QUADS);//mini window 1
    glColor3ub(250,212,20);
    glVertex2f(0.14, 0.59);
    glVertex2f(0.07,0.59);
    glVertex2f(0.07,0.54);
    glVertex2f(0.14, 0.54);
    glEnd();

    glBegin(GL_QUADS);//mini window 2
    glColor3ub(250,212,20);
    glVertex2f(0.43, 0.59);
    glVertex2f(0.36,0.59);
    glVertex2f(0.36,0.54);
    glVertex2f(0.43, 0.54);
    glEnd();


    glBegin(GL_QUADS);//mini window 3

    glVertex2f(0.14, 0.44);
    glVertex2f(0.07,0.44);
    glVertex2f(0.07,0.39);
    glVertex2f(0.14, 0.39);
    glEnd();

    glBegin(GL_QUADS);//mini window 4

    glVertex2f(0.43, 0.44);
    glVertex2f(0.36,0.44);
    glVertex2f(0.36,0.39);
    glVertex2f(0.43, 0.39);
    glEnd();

    glBegin(GL_QUADS);//mini Building//mini Building//mini Building//mini Building//mini Building

    glVertex2f(-0.05, 0.5);
    glVertex2f(-0.5,0.5);
    glVertex2f(-0.5,0.25);
    glVertex2f(-0.05,0.25);
    glEnd();

    glBegin(GL_LINES);//black 1st line
    glColor3f(0,0,0);
    glVertex2f(-0.05, 0.5);
    glVertex2f(-0.5, 0.5);
    glEnd();

    glBegin(GL_LINES);////black 2nd  line
    glColor3f(0,0,0);
    glVertex2f(-0.05, 0.35);
    glVertex2f(-0.5, 0.35);
    glEnd();

    glBegin(GL_LINES);//black y axis  line
    glColor3f(0,0,0);
    glVertex2f(-0.27, 0.5);
    glVertex2f(-0.27, 0.35);
    glEnd();


    glBegin(GL_QUADS);//door
    glColor3ub(205,153,130);
    glVertex2f(-0.19, 0.31);
    glVertex2f(-0.34,0.31);
    glVertex2f(-0.34,0.25);
    glVertex2f(-0.19, 0.25);
    glEnd();


    glBegin(GL_QUADS);//mini window 1
    glColor3ub(228,228,228);
    glVertex2f(-0.37, 0.44);
    glVertex2f(-0.44,0.44);
    glVertex2f(-0.44,0.39);
    glVertex2f(-0.37, 0.39);
    glEnd();

    glBegin(GL_QUADS);//mini window 2
    glColor3ub(228,228,228);
    glVertex2f(-0.12, 0.44);
    glVertex2f(-0.19,0.44);
    glVertex2f(-0.19,0.39);
    glVertex2f(-0.12, 0.39);
    glEnd();

    //moon //moon//moon //moon//moon //moon//moon //moon
    i=0;
    x=0.80;
    y=0.8;
    radius =.07f;
    triangleAmount = 20; //# of triangles used to draw circle# of triangles used to draw circle# of triangles used to draw circle

    //GLfloat radius = 0.8f; //radius
    twicePi = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3ub(218, 217, 215);
    glVertex2f(x, y); // center of circle
    for(i = 0; i <= triangleAmount; i++)
    {
        glVertex2f(
            x + (radius * cos(i *  twicePi / triangleAmount)),
            y + (radius * sin(i * twicePi / triangleAmount))
        );
    }
    glEnd();


    glFlush();

    flag = 1;
    night = 1;

}




void village()
{







    glClearColor(0.0f, 0.0f, 0.0f, 1.0f); // Set background color to black and opaque
    glClear(GL_COLOR_BUFFER_BIT);         // Clear the color buffer (background)



    glBegin(GL_QUADS);// sky //// sky //// sky //// sky //
    glColor3ub(155,206,235);//135,206,235
    glVertex2f(1, 1);
    glVertex2f(-1,1);
    glVertex2f(-1,-1);
    glVertex2f(1,-1);
    glEnd();








    //mountain//mountain//mountain//mountain//mountain


    GLfloat x2=0.9;
    GLfloat y2=-0.7;
    GLfloat radius2 =.4f;
    int triangleAmount2 = 50; //# of triangles used to draw circle# of triangles used to draw circle# of triangles used to draw circle

    //GLfloat radius = 0.8f; //radius
    GLfloat twicePi2 = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3ub(163,155,121);
    glVertex2f(x2, y2); // center of circle
    for(int i = 0; i <= triangleAmount2; i++)
    {
        glVertex2f(
            x2 + (radius2 * cos(i *  twicePi2 / triangleAmount2)),
            y2 + (radius2 * sin(i * twicePi2 / triangleAmount2))
        );
    }
    glEnd();









    glBegin(GL_TRIANGLES);
    glColor3ub(173,165,111);
    glVertex2f(0.9, -0.45);
    glVertex2f(0.5, 0.1);
    glVertex2f(-0.1,  -0.45);
    glEnd();

    GLfloat x1=-0.78;
    GLfloat y1=-0.65;
    GLfloat radius1 =.4f;
    int triangleAmount1 = 50; //# of triangles used to draw circle# of triangles used to draw circle# of triangles used to draw circle

    //GLfloat radius = 0.8f; //radius
    GLfloat twicePi1 = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3ub(163,155,121);
    glVertex2f(x1, y1); // center of circle
    for(int i = 0; i <= triangleAmount1; i++)
    {
        glVertex2f(
            x1 + (radius1 * cos(i *  twicePi1 / triangleAmount1)),
            y1+ (radius1 * sin(i * twicePi1 / triangleAmount1))
        );
    }
    glEnd();



    GLfloat x=-0.15;
    GLfloat y=-0.5;
    GLfloat radius =.4f;
    int triangleAmount = 50; //# of triangles used to draw circle# of triangles used to draw circle# of triangles used to draw circle

    //GLfloat radius = 0.8f; //radius
    GLfloat twicePi = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3ub(163,155,121);
    glVertex2f(x, y); // center of circle
    for(int i = 0; i <= triangleAmount; i++)
    {
        glVertex2f(
            x + (radius * cos(i *  twicePi / triangleAmount)),
            y + (radius * sin(i * twicePi / triangleAmount))
        );
    }
    glEnd();





    glBegin(GL_TRIANGLES);
    glColor3ub(153,155,111);
    glVertex2f(-0.1, -0.45);
    glVertex2f(-0.35, 0.15);
    glVertex2f(-0.5,  -0.45);
    glEnd();

    glBegin(GL_TRIANGLES);
    glColor3ub(163,165,111);
    glVertex2f(-0.4, -0.45);
    glVertex2f(-0.5, -0.1);
    glVertex2f(-0.7,  -0.45);
    glEnd();






    glBegin(GL_QUADS);//grass//grass//grass//grass
    glColor3ub(163,175,111);
    glVertex2f(1, -0.45);
    glVertex2f(-1,-0.45);
    glVertex2f(-1,-1);
    glVertex2f(1,-1);
    glEnd();








    //tree1//tree1//tree1//tree1//tree1//tree1//tree1
    glBegin(GL_QUADS);
    glColor3ub(118,92,72);
    glVertex2f(-0.62,-0.3);
    glVertex2f(-0.62,0.1);
    glVertex2f(-0.65,0.1);
    glVertex2f(-0.65,-0.3);
    glEnd();


    glBegin(GL_TRIANGLES);
    glColor3ub(66,105,41);
    glVertex2f(-0.57, -0.1);
    glVertex2f(-0.635, 0.15);
    glVertex2f(-0.7,  -0.1);
    glEnd();

    glBegin(GL_TRIANGLES);
    glColor3ub(66,105,41);
    glVertex2f(-0.57, -0.03);
    glVertex2f(-0.635, 0.12);
    glVertex2f(-0.7,  -0.03);
    glEnd();


    glBegin(GL_TRIANGLES);
    glColor3ub(66,105,41);
    glVertex2f(-0.58, 0.04);
    glVertex2f(-0.635, 0.19);
    glVertex2f(-0.69,  0.04);
    glEnd();


    //tree2//tree2//tree2//tree2//tree2//tree2//tree2//tree2//tree2
    glPushMatrix();

    glScalef(0.4,0.65,1);
    glTranslatef(0.75,0.04,0);
    {


        glBegin(GL_QUADS);
        glColor3ub(118,92,72);
        glVertex2f(-0.62,-0.3);
        glVertex2f(-0.62,0.1);
        glVertex2f(-0.65,0.1);
        glVertex2f(-0.65,-0.3);
        glEnd();


        glBegin(GL_TRIANGLES);
        glColor3ub(66,105,41);
        glVertex2f(-0.57, -0.1);
        glVertex2f(-0.635, 0.15);
        glVertex2f(-0.7,  -0.1);
        glEnd();

        glBegin(GL_TRIANGLES);
        glColor3ub(66,105,41);
        glVertex2f(-0.57, -0.03);
        glVertex2f(-0.635, 0.12);
        glVertex2f(-0.7,  -0.03);
        glEnd();


        glBegin(GL_TRIANGLES);
        glColor3ub(66,105,41);
        glVertex2f(-0.58, 0.04);
        glVertex2f(-0.635, 0.19);
        glVertex2f(-0.69,  0.04);
        glEnd();

    }

    glPopMatrix();



    //tree3//tree3//tree3//tree3//tree3//tree3//tree3//tree3
    glPushMatrix();

    glScalef(0.4,0.65,1);
    glTranslatef(3.0,-0.2,0);
    {


        glBegin(GL_QUADS);
        glColor3ub(118,92,72);
        glVertex2f(-0.62,-0.3);
        glVertex2f(-0.62,0.1);
        glVertex2f(-0.65,0.1);
        glVertex2f(-0.65,-0.3);
        glEnd();


        glBegin(GL_TRIANGLES);
        glColor3ub(66,105,41);
        glVertex2f(-0.57, -0.1);
        glVertex2f(-0.635, 0.15);
        glVertex2f(-0.7,  -0.1);
        glEnd();

        glBegin(GL_TRIANGLES);
        glColor3ub(66,105,41);
        glVertex2f(-0.57, -0.03);
        glVertex2f(-0.635, 0.12);
        glVertex2f(-0.7,  -0.03);
        glEnd();


        glBegin(GL_TRIANGLES);
        glColor3ub(66,105,41);
        glVertex2f(-0.58, 0.04);
        glVertex2f(-0.635, 0.19);
        glVertex2f(-0.69,  0.04);
        glEnd();

    }

    glPopMatrix();

    //tree4//tree4//tree4//tree4//tree4//tree4//tree4
    glPushMatrix();

    glScalef(0.4,0.65,1);
    glTranslatef(2.75,-0.2,0);
    {


        glBegin(GL_QUADS);
        glColor3ub(118,92,72);
        glVertex2f(-0.62,-0.3);
        glVertex2f(-0.62,0.1);
        glVertex2f(-0.65,0.1);
        glVertex2f(-0.65,-0.3);
        glEnd();


        glBegin(GL_TRIANGLES);
        glColor3ub(66,105,41);
        glVertex2f(-0.57, -0.1);
        glVertex2f(-0.635, 0.15);
        glVertex2f(-0.7,  -0.1);
        glEnd();

        glBegin(GL_TRIANGLES);
        glColor3ub(66,105,41);
        glVertex2f(-0.57, -0.03);
        glVertex2f(-0.635, 0.12);
        glVertex2f(-0.7,  -0.03);
        glEnd();


        glBegin(GL_TRIANGLES);
        glColor3ub(66,105,41);
        glVertex2f(-0.58, 0.04);
        glVertex2f(-0.635, 0.19);
        glVertex2f(-0.69,  0.04);
        glEnd();

    }

    glPopMatrix();



    //tree5//tree5//tree5//tree5//tree5//tree5//tree5//tree5
    glPushMatrix();

    glScalef(0.9,1.2,1);
    glTranslatef(0.8,-0.072,0);
    {


        glBegin(GL_QUADS);
        glColor3ub(118,92,72);
        glVertex2f(-0.62,-0.3);
        glVertex2f(-0.62,0.1);
        glVertex2f(-0.65,0.1);
        glVertex2f(-0.65,-0.3);
        glEnd();


        glBegin(GL_TRIANGLES);
        glColor3ub(66,105,41);
        glVertex2f(-0.57, -0.1);
        glVertex2f(-0.635, 0.15);
        glVertex2f(-0.7,  -0.1);
        glEnd();

        glBegin(GL_TRIANGLES);
        glColor3ub(66,105,41);
        glVertex2f(-0.57, -0.03);
        glVertex2f(-0.635, 0.12);
        glVertex2f(-0.7,  -0.03);
        glEnd();


        glBegin(GL_TRIANGLES);
        glColor3ub(66,105,41);
        glVertex2f(-0.58, 0.04);
        glVertex2f(-0.635, 0.19);
        glVertex2f(-0.69,  0.04);
        glEnd();

    }

    glPopMatrix();


    //tree6 //tree6 //tree6 //tree6 //tree6 //tree6 //tree6 //tree6 //tree6
    glPushMatrix();

    glScalef(0.9,1.2,1);
    glTranslatef(1.12,-0.072,0);
    {


        glBegin(GL_QUADS);
        glColor3ub(118,92,72);
        glVertex2f(-0.62,-0.3);
        glVertex2f(-0.62,0.1);
        glVertex2f(-0.65,0.1);
        glVertex2f(-0.65,-0.3);
        glEnd();


        glBegin(GL_TRIANGLES);
        glColor3ub(66,105,41);
        glVertex2f(-0.57, -0.1);
        glVertex2f(-0.635, 0.15);
        glVertex2f(-0.7,  -0.1);
        glEnd();

        glBegin(GL_TRIANGLES);
        glColor3ub(66,105,41);
        glVertex2f(-0.57, -0.03);
        glVertex2f(-0.635, 0.12);
        glVertex2f(-0.7,  -0.03);
        glEnd();


        glBegin(GL_TRIANGLES);
        glColor3ub(66,105,41);
        glVertex2f(-0.58, 0.04);
        glVertex2f(-0.635, 0.19);
        glVertex2f(-0.69,  0.04);
        glEnd();

    }

    glPopMatrix();

    //tree7//tree7//tree7//tree7//tree7//tree7//tree7
    glPushMatrix();

    glScalef(0.9,1.2,1);
    glTranslatef(1.42,-0.072,0);
    {


        glBegin(GL_QUADS);
        glColor3ub(118,92,72);
        glVertex2f(-0.62,-0.3);
        glVertex2f(-0.62,0.1);
        glVertex2f(-0.65,0.1);
        glVertex2f(-0.65,-0.3);
        glEnd();


        glBegin(GL_TRIANGLES);
        glColor3ub(66,105,41);
        glVertex2f(-0.57, -0.1);
        glVertex2f(-0.635, 0.15);
        glVertex2f(-0.7,  -0.1);
        glEnd();

        glBegin(GL_TRIANGLES);
        glColor3ub(66,105,41);
        glVertex2f(-0.57, -0.03);
        glVertex2f(-0.635, 0.12);
        glVertex2f(-0.7,  -0.03);
        glEnd();


        glBegin(GL_TRIANGLES);
        glColor3ub(66,105,41);
        glVertex2f(-0.58, 0.04);
        glVertex2f(-0.635, 0.19);
        glVertex2f(-0.69,  0.04);
        glEnd();

    }

    glPopMatrix();




    //rail line//rail line//rail line//rail line//rail line//rail line
    glBegin(GL_QUADS);
    glColor3ub(64,54,44);
    glVertex2f(1, -0.60);
    glVertex2f(-1,-0.60);
    glVertex2f(-1,-0.62);
    glVertex2f(1,-0.62);
    glEnd();

    //rail sand///rail sand///rail sand///rail sand/
    glBegin(GL_QUADS);
    glColor3ub(194,165,135);
    glVertex2f(1, -0.62);
    glVertex2f(-1,-0.62);
    glVertex2f(-1,-0.72);
    glVertex2f(1,-0.72);
    glEnd();


    //rail line wood//rail line wood//rail line wood//rail line wood//rail line wood
    /*
    //rail line wood
    glBegin(GL_QUADS);
    glColor3ub(90,92,72);
    glVertex2f(-0.85, -0.7);
    glVertex2f(-0.9,-0.7);
    glVertex2f(-0.9,-0.713);
    glVertex2f(-0.85,-0.713);
    glEnd();
    */
    //rail line wood//rail line wood//rail line wood//rail line wood//rail line wood
    float a1,a2,increment;
    a1=-0.85;
    a2=-0.9;
    increment=0;

    for(int i=0; i<10; i++)
    {

        glBegin(GL_QUADS);
        glColor3ub(90,92,72);
        glVertex2f(a1+increment, -0.62);
        glVertex2f(a2+increment,-0.62);
        glVertex2f(a2+increment,-0.633);
        glVertex2f(a1+increment,-0.633);
        glEnd();
        increment=increment+0.2;

    }




    //water//water//water//water//water//water//water
    glBegin(GL_QUADS);
    glColor3ub(127,197,222);
    glVertex2f(1, -0.72);
    glVertex2f(-1,-0.72);
    glVertex2f(-1,-1);
    glVertex2f(1,-1);
    glEnd();



    //boat1//boat1//boat1//boat1//boat1//boat1
    glPushMatrix();//move
    glTranslatef(position2,0.0,0);
    {



        glPushMatrix();

        glScalef(0.04, 0.05, 1.0);

        glTranslatef(5, -19, 0.0);
        {
            glBegin(GL_POLYGON);
            glColor3f(0.0, 0.0, 0.0);
            glVertex3f(0.0, 0.0, 0.0);
            glVertex3f(1.0, 0.0, 0.0);
            glVertex3f(2.0, 1.0, 0.0);
            glVertex3f(-2.0, 1.0, 0.0);
            glVertex3f(-1.0, 0.0, 0.0);
            glEnd();

            glBegin(GL_POLYGON);
            glColor3f(1.0, 1.0, 0.0);
            glVertex3f(0.6, 1.2, 0.0);
            glVertex3f(0.4, 1.2, 0.0);
            glVertex3f(0.4, 1.4, 0.0);
            glVertex3f(0.6, 1.4, 0.0);
            glEnd();

            glBegin(GL_POLYGON);
            glColor3f(1.0, 1.0, 0.0);
            glVertex3f(-0.6, 1.2, 0.0);
            glVertex3f(-0.4, 1.2, 0.0);
            glVertex3f(-0.4, 1.4, 0.0);
            glVertex3f(-0.6, 1.4, 0.0);
            glEnd();

            glBegin(GL_POLYGON);
            glColor3f(0.698, 0.133, 0.133);
            glVertex3f(-1.0, 1.0, 0.0);
            glVertex3f(1.0, 1.0, 0.0);
            glVertex3f(1.0, 2.0, 0.0);
            glVertex3f(-1.0, 2.0, 0.0);
            glEnd();

        }
        glPopMatrix();
    }
    glPopMatrix();






    glPushMatrix();
    glTranslatef(position,0.0,0);

    glPushMatrix();
    glScalef(0.95,1.3,1);
    glTranslatef(-0.05,-0.2,0);
    {
        //cloud start //cloud start //cloud start //cloud start //cloud start
        glLineWidth(1);

        GLfloat x=-0.92f;
        GLfloat y=.725f;
        GLfloat radius =.055f;

        int lineAmount = 100; //# of triangles used to draw circle

        //GLfloat radius = 0.8f; //radius
        GLfloat twicePi = 2.0f * PI;

        glBegin(GL_TRIANGLE_FAN);
        glColor3ub(208,222,236);
        for(int i = 0; i <= lineAmount; i++)
        {
            glVertex2f(
                x + (radius * cos(i *  twicePi / lineAmount)),
                y + (radius* sin(i * twicePi / lineAmount))
            );
        }
        glEnd();




        glLineWidth(1);

        x=-0.765f;
        y=.725f;
        radius =.045f;

        lineAmount = 100; //# of triangles used to draw circle

        //GLfloat radius = 0.8f; //radius
        twicePi = 2.0f * PI;

        glBegin(GL_TRIANGLE_FAN);
        glColor3ub(208,222,236);
        for(int i = 0; i <= lineAmount; i++)
        {
            glVertex2f(
                x + (radius * cos(i *  twicePi / lineAmount)),
                y + (radius* sin(i * twicePi / lineAmount))
            );
        }
        glEnd();



        glLineWidth(1);

        x=-0.85f;
        y=.75f;
        radius =.08f;

        lineAmount = 100; //# of triangles used to draw circle

        //GLfloat radius = 0.8f; //radius
        twicePi = 2.0f * PI;

        glBegin(GL_TRIANGLE_FAN);
        glColor3ub(208,222,236);
        for(int i = 0; i <= lineAmount; i++)
        {
            glVertex2f(
                x + (radius * cos(i *  twicePi / lineAmount)),
                y + (radius* sin(i * twicePi / lineAmount))
            );
        }
        glEnd();

    }

    glPopMatrix();
    glPopMatrix();



    glPushMatrix();
    glTranslatef(position3,0.0,0);


    glPushMatrix();
    glScalef(0.8,0.8,1);
    glTranslatef(0.5,0.4,0);
    {
        //cloud start //cloud start //cloud start //cloud start //cloud start
        glLineWidth(1);

        GLfloat x=-0.92f;
        GLfloat y=.725f;
        GLfloat radius =.055f;

        int lineAmount = 100; //# of triangles used to draw circle

        //GLfloat radius = 0.8f; //radius
        GLfloat twicePi = 2.0f * PI;

        glBegin(GL_TRIANGLE_FAN);
        glColor3ub(208,222,236);
        for(int i = 0; i <= lineAmount; i++)
        {
            glVertex2f(
                x + (radius * cos(i *  twicePi / lineAmount)),
                y + (radius* sin(i * twicePi / lineAmount))
            );
        }
        glEnd();




        glLineWidth(1);

        x=-0.78f;
        y=.73f;
        radius =.049f;

        lineAmount = 100; //# of triangles used to draw circle

        //GLfloat radius = 0.8f; //radius
        twicePi = 2.0f * PI;

        glBegin(GL_TRIANGLE_FAN);
        glColor3ub(208,222,236);
        for(int i = 0; i <= lineAmount; i++)
        {
            glVertex2f(
                x + (radius * cos(i *  twicePi / lineAmount)),
                y + (radius* sin(i * twicePi / lineAmount))
            );
        }
        glEnd();



        glLineWidth(1);

        x=-0.85f;
        y=.73f;
        radius =.06f;

        lineAmount = 100; //# of triangles used to draw circle

        //GLfloat radius = 0.8f; //radius
        twicePi = 2.0f * PI;

        glBegin(GL_TRIANGLE_FAN);
        glColor3ub(208,222,236);
        for(int i = 0; i <= lineAmount; i++)
        {
            glVertex2f(
                x + (radius * cos(i *  twicePi / lineAmount)),
                y + (radius* sin(i * twicePi / lineAmount))
            );
        }
        glEnd();

    }

    glPopMatrix();
    glPopMatrix();






    glFlush();  // Render now


    flag = 2;
}




void display()
{
    if(flag == 1 && night == 1)
    {
        nightCity();
    }

    if(flag == 1 && night == 0)
    {
        city();
    }

    if(flag == 2)
    {
        village();
    }




}



// Keyboard input callback
void handleKeypress(unsigned char key, int x, int y)
{
    switch (key)
    {
    case 'c':
        flag = 1;
        break;
    case 'C':
        flag = 1;
        break;
    case 'v':
        flag = 2;
        break;
    case 'V':
        flag = 2;
        break;

    case 'n':
         night = 1;
        break;
    case 'N':
        night = 1;
        break;

    case 'd':
         night = 0;
        break;
    case 'D':
        night = 0;
        break;
    }
    glutPostRedisplay(); // Redraw the scene
}



int main(int argc, char** argv)
{
    glutInit(&argc, argv);
    glutCreateWindow("Lab task ");
    glutInitWindowSize(320, 320);

    glutDisplayFunc(display);//

    glutKeyboardFunc(handleKeypress);

    glutTimerFunc(100, update, 0);
    glutTimerFunc(100, update2, 0);
    glutTimerFunc(100, update3, 0);
    glutTimerFunc(100, update4, 0);

    glutMainLoop();
    return 0;
}










