---
title: 'Procedura: creare e usare assembly dalla riga di comando (C#)'
ms.date: 07/20/2015
ms.assetid: 408ddce3-89e3-4e12-8353-34a49beeb72b
ms.openlocfilehash: ef872992f17eaaeacf451fa10ef792c47445df80
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319644"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a><span data-ttu-id="91b69-102">Procedura: creare e usare assembly dalla riga di comando (C#)</span><span class="sxs-lookup"><span data-stu-id="91b69-102">How to: Create and Use Assemblies Using the Command Line (C#)</span></span>
<span data-ttu-id="91b69-103">Un assembly, o libreria a collegamento dinamico (DLL), viene collegato al programma in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="91b69-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="91b69-104">Per illustrare la creazione e l'uso di una DLL, si consideri lo scenario seguente:</span><span class="sxs-lookup"><span data-stu-id="91b69-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
-   <span data-ttu-id="91b69-105">`MathLibrary.DLL`: il file libreria che contiene i metodi da chiamare in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="91b69-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="91b69-106">In questo esempio la DLL contiene due metodi: `Add` e `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="91b69-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
-   <span data-ttu-id="91b69-107">`Add`: il file di origine che contiene il metodo `Add`.</span><span class="sxs-lookup"><span data-stu-id="91b69-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="91b69-108">Restituisce la somma dei suoi parametri.</span><span class="sxs-lookup"><span data-stu-id="91b69-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="91b69-109">La classe `AddClass` che contiene il metodo `Add` è un membro dello spazio dei nomi `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="91b69-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="91b69-110">`Mult`: il codice sorgente che contiene il metodo `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="91b69-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="91b69-111">Restituisce il prodotto dei suoi parametri.</span><span class="sxs-lookup"><span data-stu-id="91b69-111">It returns the product of its parameters.</span></span> <span data-ttu-id="91b69-112">Anche la classe `MultiplyClass` che contiene il metodo `Multiply` è un membro dello spazio dei nomi `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="91b69-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="91b69-113">`TestCode`: il file che contiene il metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="91b69-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="91b69-114">Usa i metodi del file DLL per calcolare la somma e il prodotto degli argomenti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="91b69-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91b69-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="91b69-115">Example</span></span>  
  
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
  
 <span data-ttu-id="91b69-116">Questo file contiene l'algoritmo che usa i metodi della DLL: `Add` e `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="91b69-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="91b69-117">Inizia con l'analisi degli argomenti immessi dalla riga di comando: `num1` e `num2`.</span><span class="sxs-lookup"><span data-stu-id="91b69-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="91b69-118">Quindi calcola la somma usando il metodo `Add` sulla classe `AddClass` e il prodotto usando il metodo `Multiply` sulla classe `MultiplyClass`.</span><span class="sxs-lookup"><span data-stu-id="91b69-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="91b69-119">Si noti che la direttiva `using` all'inizio del file consente di usare i nomi di classe non qualificati per fare riferimento ai metodi della DLL in fase di compilazione, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="91b69-119">Notice that the `using` directive at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```csharp  
MultiplyClass.Multiply(num1, num2);  
```  
  
 <span data-ttu-id="91b69-120">In caso contrario è necessario usare nomi completi, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="91b69-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```csharp  
UtilityMethods.MultiplyClass.Multiply(num1, num2);  
```  
  
## <a name="execution"></a><span data-ttu-id="91b69-121">Esecuzione</span><span class="sxs-lookup"><span data-stu-id="91b69-121">Execution</span></span>  
 <span data-ttu-id="91b69-122">Per eseguire il programma immettere il nome del file EXE, seguito da due numeri, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="91b69-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a><span data-ttu-id="91b69-123">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="91b69-123">Compiling the Code</span></span>  
 <span data-ttu-id="91b69-124">Per compilare il file `MathLibrary.DLL`, compilare i due file `Add` e `Mult` usando la seguente riga di comando.</span><span class="sxs-lookup"><span data-stu-id="91b69-124">To build the file `MathLibrary.DLL`, compile the two files `Add` and `Mult` by using the following command line.</span></span>  
  
```csharp  
csc /target:library /out:MathLibrary.DLL Add.cs Mult.cs  
```  
  
 <span data-ttu-id="91b69-125">L'opzione [/target:library](../../../../csharp/language-reference/compiler-options/target-library-compiler-option.md) del compilatore indica al compilatore di generare un file DLL anziché un file EXE.</span><span class="sxs-lookup"><span data-stu-id="91b69-125">The [/target:library](../../../../csharp/language-reference/compiler-options/target-library-compiler-option.md) compiler option tells the compiler to output a DLL instead of an EXE file.</span></span> <span data-ttu-id="91b69-126">L'opzione [/out](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) del compilatore seguita da un nome di file viene usata per specificare il nome di file della DLL.</span><span class="sxs-lookup"><span data-stu-id="91b69-126">The [/out](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) compiler option followed by a file name is used to specify the DLL file name.</span></span> <span data-ttu-id="91b69-127">In caso contrario il compilatore usa il primo file (`Add.cs`) come nome della DLL.</span><span class="sxs-lookup"><span data-stu-id="91b69-127">Otherwise, the compiler uses the first file (`Add.cs`) as the name of the DLL.</span></span>  
  
 <span data-ttu-id="91b69-128">Per compilare il file eseguibile, `TestCode.exe`, usare la seguente riga di comando:</span><span class="sxs-lookup"><span data-stu-id="91b69-128">To build the executable file, `TestCode.exe`, use the following command line:</span></span>  
  
```csharp  
csc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.cs  
```  
  
 <span data-ttu-id="91b69-129">L'opzione **/out** del compilatore indica al compilatore di generare un file EXE e specifica il nome del file che deve essere generato (`TestCode.exe`).</span><span class="sxs-lookup"><span data-stu-id="91b69-129">The **/out** compiler option tells the compiler to output an EXE file and specifies the name of the output file (`TestCode.exe`).</span></span> <span data-ttu-id="91b69-130">Questa opzione del compilatore è opzionale.</span><span class="sxs-lookup"><span data-stu-id="91b69-130">This compiler option is optional.</span></span> <span data-ttu-id="91b69-131">L'opzione [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md) del compilatore specifica il file o i file DLL utilizzati dal programma.</span><span class="sxs-lookup"><span data-stu-id="91b69-131">The [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md) compiler option specifies the DLL file or files that this program uses.</span></span> <span data-ttu-id="91b69-132">Per altre informazioni, vedere [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="91b69-132">For more information, see [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="91b69-133">Per altre informazioni sulla compilazione dalla riga di comando, vedere [Compilazione dalla riga di comando con csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="91b69-133">For more information about building from the command line, see [Command-line Building With csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91b69-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91b69-134">See Also</span></span>  
 [<span data-ttu-id="91b69-135">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="91b69-135">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="91b69-136">Assembly e Global Assembly Cache (C#)</span><span class="sxs-lookup"><span data-stu-id="91b69-136">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="91b69-137">Creazione di una classe che contenga le funzioni DLL</span><span class="sxs-lookup"><span data-stu-id="91b69-137">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
