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
