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
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a><span data-ttu-id="cc3b6-102">Procedura: Creare e usare assembly dalla riga di comando (C#)</span><span class="sxs-lookup"><span data-stu-id="cc3b6-102">How to: Create and Use Assemblies Using the Command Line (C#)</span></span>
<span data-ttu-id="cc3b6-103">Un assembly, o libreria a collegamento dinamico (DLL), viene collegato al programma in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="cc3b6-104">Per illustrare la creazione e l'uso di una DLL, si consideri lo scenario seguente:</span><span class="sxs-lookup"><span data-stu-id="cc3b6-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
- <span data-ttu-id="cc3b6-105">`MathLibrary.DLL`: il file libreria che contiene i metodi da chiamare in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="cc3b6-106">In questo esempio la DLL contiene due metodi: `Add` e `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
- <span data-ttu-id="cc3b6-107">`Add`: il file di origine che contiene il metodo `Add`.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="cc3b6-108">Restituisce la somma dei suoi parametri.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="cc3b6-109">La classe `AddClass` che contiene il metodo `Add` è un membro dello spazio dei nomi `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
- <span data-ttu-id="cc3b6-110">`Mult`: il codice sorgente che contiene il metodo `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="cc3b6-111">Restituisce il prodotto dei suoi parametri.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-111">It returns the product of its parameters.</span></span> <span data-ttu-id="cc3b6-112">Anche la classe `MultiplyClass` che contiene il metodo `Multiply` è un membro dello spazio dei nomi `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
- <span data-ttu-id="cc3b6-113">`TestCode`: il file che contiene il metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="cc3b6-114">Usa i metodi del file DLL per calcolare la somma e il prodotto degli argomenti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc3b6-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="cc3b6-115">Example</span></span>  
  
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
  
 <span data-ttu-id="cc3b6-116">Questo file contiene l'algoritmo che usa i metodi della DLL: `Add` e `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="cc3b6-117">Inizia con l'analisi degli argomenti immessi dalla riga di comando: `num1` e `num2`.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="cc3b6-118">Quindi calcola la somma usando il metodo `Add` sulla classe `AddClass` e il prodotto usando il metodo `Multiply` sulla classe `MultiplyClass`.</span><span class="sxs-lookup"><span data-stu-id="cc3b6-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="cc3b6-119">Si noti che la direttiva `using` all'inizio del file consente di usare i nomi di classe non qualificati per fare riferimento ai metodi della DLL in fase di compilazione, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cc3b6-119">Notice that the `using` directive at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```csharp  
MultiplyClass.Multiply(num1, num2);  
```  
  
 <span data-ttu-id="cc3b6-120">In caso contrario è necessario usare nomi completi, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cc3b6-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```csharp  
UtilityMethods.MultiplyClass.Multiply(num1, num2);  
```  
  
## <a name="execution"></a><span data-ttu-id="cc3b6-121">Esecuzione</span><span class="sxs-lookup"><span data-stu-id="cc3b6-121">Execution</span></span>  
 <span data-ttu-id="cc3b6-122">Per eseguire il programma immettere il nome del file EXE, seguito da due numeri, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cc3b6-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="see-also"></a><span data-ttu-id="cc3b6-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc3b6-123">See also</span></span>

- [<span data-ttu-id="cc3b6-124">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="cc3b6-124">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="cc3b6-125">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="cc3b6-125">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="cc3b6-126">Creazione di una classe che contenga le funzioni DLL</span><span class="sxs-lookup"><span data-stu-id="cc3b6-126">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
