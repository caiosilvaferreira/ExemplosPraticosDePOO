# Exemplos praticos de POO (Versão 1,2,3)

essa é a versão 1 do exercicio

```sql
using PrimeiroProjeto;
using System;
using System.Globalization;
using System.Security.Cryptography.X509Certificates;

internal class Program {

    static double Pi = 3.14;

    
     static void Main(string[] args) {

        Console.WriteLine("Entre com valor do raio: ");
        double raio = double.Parse(Console.ReadLine(),CultureInfo.InvariantCulture);

        double circ = Circunferencia(raio); /* ele puxa o metodo abaixo e interliga com o raio acima*/
        double volume = Volume(raio);
        Console.WriteLine("Circunferencia = " + circ.ToString("F2", CultureInfo.InvariantCulture));
        Console.WriteLine("Volume = " + volume.ToString("F2", CultureInfo.InvariantCulture));
        Console.WriteLine("Valor de PI = " + Pi.ToString("F2",CultureInfo.InvariantCulture));
    }

    static double Circunferencia(double raio /*essa funcão não é o mesmo que o raio de cima*/){
            return 2.0 * Pi* raio;
        }

    static double Volume(double raio) {

        return 4.0 / 3.0 * Pi * Math.Pow(3.0, raio);
    }

}
```

Versão 2.0 do exercício

a diferença aqui seria em separa a parte logica com o codigo principal, a logica ficaria na parte da classe, e depois somente instanciamos a classe e espelhamos isso no codigo principal tambem criando as variaveis

```sql
using PrimeiroProjeto;
using System;
using System.Globalization;
using System.Security.Cryptography.X509Certificates;

internal class Program {
     static void Main(string[] args) {

        Area dados = new Area();

        Console.WriteLine("Entre com valor do raio: ");
        double raio = double.Parse(Console.ReadLine(),CultureInfo.InvariantCulture);

        double circ = dados.Circunferencia(raio);
        double volume = dados.Volume(raio);
        Console.WriteLine("Circunferencia = " + circ.ToString("F2", CultureInfo.InvariantCulture));
        Console.WriteLine("Volume = " + volume.ToString("F2", CultureInfo.InvariantCulture));
        Console.WriteLine("Valor de PI = " + dados.Pi.ToString("F2",CultureInfo.InvariantCulture));
    }

    
}
```

Classe Area:

```sql
using System;
using System.Globalization;
namespace PrimeiroProjeto {
    internal class Area {

         public  double Pi = 3.14;

        public  double Circunferencia(double raio ) {
            return 2.0 * Pi* raio;
        }

        public  double Volume(double raio) {

            return 4.0 / 3.0 * Pi * Math.Pow(3.0, raio);
        }

    }
}
```

Versão 3.0 do exercicio

a difença entre a versão 2, é que a essa versão alem de ser menor, faz a mesma função. colocando o static podemos facilmente instancia o nome da classe ex: Area.volume assim por diante

```sql

using PrimeiroProjeto;
using System;
using System.Globalization;

internal class Program {
     static void Main(string[] args) {

        Console.WriteLine("Entre com valor do raio: ");
        double raio = double.Parse(Console.ReadLine(),CultureInfo.InvariantCulture);

        double circ = Area.Circunferencia(raio); /* ele puxa o metodo abaixo e interliga com o raio acima*/
        double volume = Area.Volume(raio);
        Console.WriteLine("Circunferencia = " + circ.ToString("F2", CultureInfo.InvariantCulture));
        Console.WriteLine("Volume = " + volume.ToString("F2", CultureInfo.InvariantCulture));
        Console.WriteLine("Valor de PI = " + Area.Pi.ToString("F2",CultureInfo.InvariantCulture));
    }

    
}
```

Classe Area:

```sql
using System;
using System.Globalization;
namespace PrimeiroProjeto {
    internal class Area {

         public static double Pi = 3.14;

        public static double Circunferencia(double raio /*essa funcão não é o mesmo que o raio de cima*/) {
            return 2.0 * Pi* raio;
        }

        public static double Volume(double raio) {

            return 4.0 / 3.0 * Pi * Math.Pow(3.0, raio);
        }
    }
}
```
