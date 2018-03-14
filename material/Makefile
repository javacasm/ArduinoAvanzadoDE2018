
all: 1 2 3 4

S1="Tema 1 - Introducción a Arduino.md"
F1="Tema 1 - Introducción a Arduino.docx"
S2="Tema 2 - Hardware de  Arduino.md"
F2="Tema 2 - Hardware de  Arduino.docx"
S3="Tema 3 - Programación de  Arduino.md"
F3="Tema 3 - Programación de  Arduino.docx"
S4="Tema 4 - Controlando el mundo físico con Arduino.md"
F4="Tema 4 - Controlando el mundo físico con Arduino.docx"
F5="Tema 5 - Programacion avanzada.docx"

1:
	pandoc --latex-engine=xelatex   \
					-V papersize:a4paper    \
					--template=./LaTeX_ES.latex    \
					-o  $(S1)  \
					Cabecera.md        \
					$(F1)
2:
	pandoc --latex-engine=xelatex   \
					-V papersize:a4paper    \
					--template=./LaTeX_ES.latex    \
					-o $(F2)     \
					Cabecera.md        \
					$(S2)

3:
	pandoc --latex-engine=xelatex \
					--from=markdown \
					-V papersize:a4paper \
					--template=./LaTeX_ES.latex \
		      -o $(F3) \
		       Cabecera.md     \
		      $(S3)
4:
	pandoc --latex-engine=xelatex       \
					-V papersize:a4paper        \
					--template=./LaTeX_ES.latex \
					-o $(F4) \
					Cabecera.md           \
					$(S4)

5:
	pandoc --latex-engine=xelatex       \
					-V papersize:a4paper        \
					--template=./LaTeX_ES.latex \
					-o $(F5) \
					Cabecera.md           \
					T5_Programacion_C++.md \
					T5_practicas_programacion.md \
					T5_tiempos.md \
					T5_ProcesoCompilacion.md 

clean:
	rm $(F1) $(F2) $(F3) $(F4) $(F5)

cp:
	cp $(F1) $(F2) $(F3) $(F4) $(F5) /home/javacasm/Dropbox/1_proyectos/javacasm-DarwinEventur/2018/01_arduino_completo_online/materiales/

push:
	git commit -m "update" $(F1);
	git commit -m "update" $(F2);
	git commit -m "update" $(F3);
	git commit -m "update" $(F4);
	git commit -m "update" T5_*.md;
 	git push;
