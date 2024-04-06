public class Program
{
    static void Main(string[] args)
    {

        Random random = new Random();
        bool jugarDeNuevo = true, Ganastes = false;
        int Jugadores = 0, num, rangoMax = 0, numAlea = 0;
        string respuesta;

        while (jugarDeNuevo)
        {

            Console.WriteLine("Ingrese la cantidad de jugadores  2 a 4: ");

            Jugadores = Convert.ToInt32(Console.ReadLine());

            switch (Jugadores)
            {
                case 2:
                    rangoMax = 50;
                    break;
                case 3:
                    rangoMax = 100;
                    break;
                case 4:
                    rangoMax = 200;
                    break;
                default:
                    Console.WriteLine("Cantidad de jugadores ingresada no es valida");
                    continue;
            }

            numAlea = random.Next(rangoMax + 1);

            for (int i = 1; i <= Jugadores && !Ganastes; i++)
            {
                Console.WriteLine($"\n Turno del jugador {i}");

                Console.WriteLine("Ingresa un número: ");
               num = Convert.ToInt32(Console.ReadLine());

                if (num < numAlea)
                {
                    Console.WriteLine("MAYOR");
                }
                else if (num > numAlea)
                {
                    Console.WriteLine("MENOR");
                }
                else
                {
                    Console.WriteLine("¡HAS GANADO!");
                    Ganastes = true;
                }
            }
            Console.WriteLine("\n ¿Desea jugar nuevamente? (Si/No): ");
            respuesta = Console.ReadLine().ToLower();

            if (respuesta != "si")
            {
                jugarDeNuevo = false;
            }
            Console.Clear();
        }
        Console.WriteLine("¡ mil gracias por jugar!");
    }
}
