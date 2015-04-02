#include <GL/gl.h>
#include <GL/glu.h>
#include <GL/glut.h>
#include <stdlib.h>
#include <stdio.h>
#include <iostream>
#include <string.h>


char *color[30];
char *menu[50];
void text (char *color);
using namespace std;
void specialKeys(unsigned char key, int x, int y);
void ponerMaterial();

void init(void)
{
glEnable(GL_LIGHTING);
glEnable(GL_LIGHT0); //Activamos las luces en 0
glDepthFunc(GL_LESS); //comparación de profundidad
glEnable(GL_DEPTH_TEST); //activa GL_DEPTH_TEST
}
void reshape(int w, int h)
{
glViewport(0, 0, (GLsizei) w, (GLsizei) h);
// Activamos la matriz de proyeccion.
glMatrixMode(GL_PROJECTION);
// "limpiamos" esta con la matriz identidad.
glLoadIdentity();
// Usamos proyeccion ortogonal
glOrtho(-300, 300, -300, 300, -300, 300);
// Activamos la matriz de modelado/visionado.
glMatrixMode(GL_MODELVIEW);
// "Limpiamos" la matriz
glLoadIdentity();
}
void display(void)
{
char color[]={"Cambien color a la Tetera"};
char menu[]={"Menu >> [1-Jade 2-Obsidian 3-Perl 4-Ruby 5-Turquois]"};
/*GLfloat mat_ambient[] = { 0.329412f, 0.223529f, 0.027451f,1.0f };
GLfloat mat_diffuse[] = { 0.780392f, 0.568627f, 0.113725f, 1.0f };
GLfloat mat_specular[] = { 0.992157f, 0.941176f, 0.807843f, 1.0f };
GLfloat shine[] = {27.8974f};*/
// "Limpiamos" el frame buffer con el color de "Clear", en este
// caso negro.
glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
glMatrixMode( GL_MODELVIEW_MATRIX );
glLoadIdentity();
// Rotacion de 25 grados en torno al eje x
glRotated(25.0, 1.0, 0.0, 0.0);
// Rotacion de -30 grados en torno al eje y
glRotated(-30.0, 0.0, 1.0, 0.0);
// Dibujamos una "Tetera" y le aplico el material
glPushMatrix();
/*glMaterialfv(GL_FRONT, GL_AMBIENT, mat_ambient);
glMaterialfv(GL_FRONT, GL_DIFFUSE, mat_diffuse);
glMaterialfv(GL_FRONT, GL_SPECULAR, mat_specular);
glMaterialfv(GL_FRONT, GL_SHININESS, shine);*/
//setMaterial
text(color);
glRasterPos2f(-280, 200);
text(menu);
glRasterPos2f(-130, 260);
glutSolidTeapot(125.0);
glFlush();
}
int main(int argc, char **argv)
{
// Inicializo OpenGL
glutInit(&argc, argv);
// Activamos buffer simple y colores del tipo RGB
glutInitDisplayMode (GLUT_RGB | GLUT_DEPTH);
// Definimos una ventana de medidas 800 x 600 como ventana
// de visualizacion en pixels
glutInitWindowSize (800, 600);
// Posici0onamos la ventana en la esquina superior izquierda de
// la pantalla.
glutInitWindowPosition (0, 0);
// Creamos literalmente la ventana y le adjudicamos el nombre que se
// observara en su barra de titulo.
glutCreateWindow ("Cambio de color de Tetera");
// Inicializamos el sistema

init();
glutDisplayFunc(display);
glutReshapeFunc(reshape);
glutKeyboardFunc(specialKeys);
glutMainLoop();
return 0;
}


void ponerMaterial(GLfloat a, GLfloat b, GLfloat c,GLfloat d, GLfloat e, GLfloat f, GLfloat g, GLfloat h, GLfloat i, GLfloat s){
    GLfloat mat_ambient[] = { a, b, c };
    GLfloat mat_diffuse[] = { d, e, f };
    GLfloat mat_specular[] = { g, h, i};
    GLfloat shine[] = { s };

    glMaterialfv(GL_FRONT, GL_AMBIENT, mat_ambient);
    glMaterialfv(GL_FRONT, GL_DIFFUSE, mat_diffuse);
    glMaterialfv(GL_FRONT, GL_SPECULAR, mat_specular);
    glMaterialfv(GL_FRONT, GL_SHININESS, shine);
}


void specialKeys( unsigned char key, int x, int y ) {

    switch (key){
    case 49:
        {
        /*Jade*/
        ponerMaterial(0.135f,0.2225f,0.1575f,0.54f,0.89f,0.63f,0.316228f,0.316228f,0.316228f,0.3);
        char color[] = {"Jade"};
//        text(color);
//        glRasterPos2f(200,200);
        break;
        }

    case 50:
        {
        ponerMaterial(0.05375f,0.05f,0.06625f,0.18275f,0.17f,0.22525f,0.332741f,0.328634f,0.346435f,0.3);
//        char color[]={"Obsidian"};
//        text(color);
        break;
        }

    case 51:
//pearl
        {
        ponerMaterial(0.25f,0.20725f,0.20725f,1.0f,0.829f,0.829f,0.296648f,0.296648f,0.296648f,0.088);
//        char color[]={"Perl"};
//        text(color);
        break;
        }

    case 52:
        {
        //ruby
        ponerMaterial(0.1745f,0.01175f,0.01175f,0.61424f,0.04136f,0.04136f,0.727811f,0.626959f,0.626959f,0.6);
//        char color[]={"Ruby"};
//        text(color);
        }
    break;
    case 53:
        {
//      turquoise
        ponerMaterial(0.1f,0.18725f,0.1745f,0.396f,0.74151f,0.69102f,0.297254f,0.30829f,0.306678f,0.1f);
//        char color[]={"Turquose"};
//        text(color);
        break;
        }

    case 54:
         {
        ponerMaterial(0.329412f, 0.223529f, 0.027451f,0.780392f, 0.568627f, 0.113725f,0.992157f, 0.941176f, 0.807843f,27.8974f);
//        char color[]={"Brazz"};
//        text(color);
        break;
         }
    default:
//turquoise
    break;
    }
  glutPostRedisplay();

}
void text (char *s){
unsigned int i;

 for (i=0; i<strlen(s); i++){
	glutBitmapCharacter(GLUT_BITMAP_TIMES_ROMAN_24 , s[i]);
 }
    cout<<s;
//  glRasterPos2f(-200, 200);
    glutPostRedisplay();
 }
