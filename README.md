Profesor
using System;
using System.Collections.Generic;
using System.Linq;
using System.Runtime.InteropServices;
using System.Text;
using System.Threading.Tasks;

namespace alumno_y_profe
{
    internal class Profesor
    {
        private string nombre_profesor;
        public Alumno Alumno;

        public string Nombre_profesor { get => nombre_profesor; set => nombre_profesor = value; }
        internal Alumno Alumno1 { get => Alumno; set => Alumno = value; }
        public Profesor()
        {
            Alumno = new Alumno();
        }
        public void capturar_Datos_Alumno()
        {
            Console.Write("Ingrese el número de lista del alumno: ");
            Alumno.Nl = int.Parse(Console.ReadLine());

            Console.Write("Ingrese el nombre del alumno: ");
            Alumno.Nombre_Alumno = Console.ReadLine();
        }
        public void capturar_Materias()
        {
            Console.WriteLine("Ingrese las materias del alumno (ingrese 'listo' para terminar):");
            string materia;
            while ((materia = Console.ReadLine()) != "listo")
            {
                Alumno.agregarMaterias(materia);
            }
        }
        public void capturar_Calificaciones()
        {
            Console.WriteLine("Ingrese las calificaciones del alumno ( ingrese -1 para terminar):");
            int calificación;
            while ((calificación = int.Parse(Console.ReadLine())) != -1)
            {
                Alumno.agregarCalificación(calificación);
            }
        }
    }
}

Alumno
using System;
using System.Collections;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace alumno_y_profe
{
    internal class Alumno
    {
        private int nl;
        private string nombre_alumno;
        private ArrayList materias = new ArrayList();
        private ArrayList calificaciones = new ArrayList();

        public int Nl { get => nl; set => nl = value; }
        public string Nombre_Alumno { get => nombre_alumno; set => nombre_alumno = value; }
        public ArrayList Materias { get => materias; set => materias = value; }
        public ArrayList Calificaciones { get => calificaciones; set => calificaciones = value; }
        public Alumno()
        {
            Materias = new ArrayList();
            Calificaciones = new ArrayList();
        }
        public void agregarMaterias(string materia)
        {
            materias.Add(materia);
        }
        public void agregarCalificación(int calificación)
        {
            calificaciones.Add(calificación);
        }
    }
}


Principal
using alumno_y_profe;
Profesor profesor = new Profesor();
Console.WriteLine("\nDatos del Profe:");
Console.WriteLine("Ingresa el Nombre del profesor");
profesor.Nombre_profesor = Console.ReadLine();

profesor.capturar_Datos_Alumno();
profesor.capturar_Materias();
profesor.capturar_Calificaciones();

Console.WriteLine($"El nombre del profesor es {profesor.Nombre_profesor}");
Console.WriteLine($"El Nombre de el alumno es{profesor.Alumno.Nombre_Alumno}");

Console.WriteLine("Materias:");
foreach (string materia in profesor.Alumno.Materias)
{
    Console.WriteLine($"- {materia}");
}

Console.WriteLine("Calificaciones");
foreach (int calificaciones in profesor.Alumno.Calificaciones)
{
    Console.WriteLine($"-{calificaciones}");
}













