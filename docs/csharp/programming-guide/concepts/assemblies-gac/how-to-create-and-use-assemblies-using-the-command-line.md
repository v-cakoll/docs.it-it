---
title: 'Procedura: Creare e usare assembly dalla riga di comando (C#)'
ms.date: 07/20/2015
ms.assetid: 408ddce3-89e3-4e12-8353-34a49beeb72b
ms.openlocfilehash: 0a8db22a05d834d15f6e6b7f049f59f86bc1fe1d
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595971"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a>Procedura: Creare e usare assembly dalla riga di comando (C#)
Un assembly, o libreria a collegamento dinamico (DLL), viene collegato al programma in fase di esecuzione. Per illustrare la creazione e l'uso di una DLL, si consideri lo scenario seguente:  
  
- `MathLibrary.DLL`: il file libreria che contiene i metodi da chiamare in fase di esecuzione. In questo esempio la DLL contiene due metodi: `Add` e `Multiply`.  
  
- `Add`: il file di origine che contiene il metodo `Add`. Restituisce la somma dei suoi parametri. La classe `AddClass` che contiene il metodo `Add` è un membro dello spazio dei nomi `UtilityMethods`.  
  
- `Mult`: il codice sorgente che contiene il metodo `Multiply`. Restituisce il prodotto dei suoi parametri. Anche la classe `MultiplyClass` che contiene il metodo `Multiply` è un membro dello spazio dei nomi `UtilityMethods`.  
  
- `TestCode`: il file che contiene il metodo `Main`. Usa i metodi del file DLL per calcolare la somma e il prodotto degli argomenti in fase di esecuzione.  
  
## <a name="example"></a>Esempio  
  
```csharp  
// File: Add.cs   
namespace UtilityMethods  
{  
    public class AddClass   
    {  
        public static long Add(long i, long j)   
        {   
            return (i + j);  
        }  
    }  
}  
```  
  
```csharp  
// File: Mult.cs  
namespace UtilityMethods   
{  
    public class MultiplyClass  
    {  
        public static long Multiply(long x, long y)   
        {  
            return (x * y);   
        }  
    }  
}  
```  
  
```csharp  
// File: TestCode.cs  
  
using UtilityMethods;  
  
class TestCode  
{  
    static void Main(string[] args)   
    {  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:");  
  
        if (args.Length != 2)  
        {  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>");  
            return;  
        }  
  
        long num1 = long.Parse(args[0]);  
        long num2 = long.Parse(args[1]);  
  
        long sum = AddClass.Add(num1, num2);  
        long product = MultiplyClass.Multiply(num1, num2);  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum);  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product);  
    }  
}  
/* Output (assuming 1234 and 5678 are entered as command-line arguments):  
    Calling methods from MathLibrary.DLL:  
    1234 + 5678 = 6912  
    1234 * 5678 = 7006652          
*/  
```  
  
 Questo file contiene l'algoritmo che usa i metodi della DLL: `Add` e `Multiply`. Inizia con l'analisi degli argomenti immessi dalla riga di comando: `num1` e `num2`. Quindi calcola la somma usando il metodo `Add` sulla classe `AddClass` e il prodotto usando il metodo `Multiply` sulla classe `MultiplyClass`.  
  
 Si noti che la direttiva `using` all'inizio del file consente di usare i nomi di classe non qualificati per fare riferimento ai metodi della DLL in fase di compilazione, come indicato di seguito:  
  
```csharp  
MultiplyClass.Multiply(num1, num2);  
```  
  
 In caso contrario è necessario usare nomi completi, come indicato di seguito:  
  
```csharp  
UtilityMethods.MultiplyClass.Multiply(num1, num2);  
```  
  
## <a name="execution"></a>Esecuzione  
 Per eseguire il programma immettere il nome del file EXE, seguito da due numeri, come indicato di seguito:  
  
 `TestCode 1234 5678`  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../index.md)
- [Assembly in .NET](../../../../standard/assembly/index.md)
- [Creazione di una classe che contenga le funzioni DLL](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
