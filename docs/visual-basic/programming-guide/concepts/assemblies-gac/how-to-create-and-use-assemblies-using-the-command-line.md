---
title: 'Procedura: Creare e usare assembly dalla riga di comando (Visual Basic)'
ms.date: 03/14/2018
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
ms.openlocfilehash: eecd644a7b91492f0a78cf969cfa71ae927609ab
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819401"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a><span data-ttu-id="52c1e-102">Procedura: Creare e usare assembly dalla riga di comando (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52c1e-102">How to: Create and Use Assemblies Using the Command Line (Visual Basic)</span></span>
<span data-ttu-id="52c1e-103">Un assembly, o libreria a collegamento dinamico (DLL), viene collegato al programma in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="52c1e-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="52c1e-104">Per illustrare la creazione e l'uso di una DLL, si consideri lo scenario seguente:</span><span class="sxs-lookup"><span data-stu-id="52c1e-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
-   <span data-ttu-id="52c1e-105">`MathLibrary.DLL`: il file libreria che contiene i metodi da chiamare in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="52c1e-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="52c1e-106">In questo esempio la DLL contiene due metodi: `Add` e `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="52c1e-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
-   <span data-ttu-id="52c1e-107">`Add`: il file di origine che contiene il metodo `Add`.</span><span class="sxs-lookup"><span data-stu-id="52c1e-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="52c1e-108">Restituisce la somma dei suoi parametri.</span><span class="sxs-lookup"><span data-stu-id="52c1e-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="52c1e-109">La classe `AddClass` che contiene il metodo `Add` è un membro dello spazio dei nomi `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="52c1e-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="52c1e-110">`Mult`: il codice sorgente che contiene il metodo `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="52c1e-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="52c1e-111">Restituisce il prodotto dei suoi parametri.</span><span class="sxs-lookup"><span data-stu-id="52c1e-111">It returns the product of its parameters.</span></span> <span data-ttu-id="52c1e-112">Anche la classe `MultiplyClass` che contiene il metodo `Multiply` è un membro dello spazio dei nomi `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="52c1e-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="52c1e-113">`TestCode`: il file che contiene il metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="52c1e-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="52c1e-114">Usa i metodi del file DLL per calcolare la somma e il prodotto degli argomenti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="52c1e-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52c1e-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="52c1e-115">Example</span></span>  
  
```vb  
' File: Add.vb   
Namespace UtilityMethods  
    Public Class AddClass  
        Public Shared Function Add(ByVal i As Long, ByVal j As Long) As Long  
            Return i + j  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: Mult.vb  
Namespace UtilityMethods  
    Public Class MultiplyClass  
        Public Shared Function Multiply(ByVal x As Long, ByVal y As Long) As Long  
            Return x * y  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: TestCode.vb  
  
Imports UtilityMethods  
  
Module Test  
  
    Sub Main(ByVal args As String())  
  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:")  
  
        If args.Length <> 2 Then  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>")  
            Return  
        End If  
  
        Dim num1 As Long = Long.Parse(args(0))  
        Dim num2 As Long = Long.Parse(args(1))  
  
        Dim sum As Long = AddClass.Add(num1, num2)  
        Dim product As Long = MultiplyClass.Multiply(num1, num2)  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum)  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product)  
  
    End Sub  
  
End Module  
  
' Output (assuming 1234 and 5678 are entered as command-line arguments):  
' Calling methods from MathLibrary.DLL:  
' 1234 + 5678 = 6912  
' 1234 * 5678 = 7006652  
```  
  
 <span data-ttu-id="52c1e-116">Questo file contiene l'algoritmo che usa i metodi della DLL: `Add` e `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="52c1e-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="52c1e-117">Inizia con l'analisi degli argomenti immessi dalla riga di comando: `num1` e `num2`.</span><span class="sxs-lookup"><span data-stu-id="52c1e-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="52c1e-118">Quindi calcola la somma usando il metodo `Add` sulla classe `AddClass` e il prodotto usando il metodo `Multiply` sulla classe `MultiplyClass`.</span><span class="sxs-lookup"><span data-stu-id="52c1e-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="52c1e-119">Si noti che il `Imports` istruzione all'inizio del file consente di usare i nomi di classe non qualificati per fare riferimento ai metodi della DLL in fase di compilazione, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="52c1e-119">Notice that the  `Imports` statement at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 <span data-ttu-id="52c1e-120">In caso contrario è necessario usare nomi completi, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="52c1e-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a><span data-ttu-id="52c1e-121">Esecuzione</span><span class="sxs-lookup"><span data-stu-id="52c1e-121">Execution</span></span>  
 <span data-ttu-id="52c1e-122">Per eseguire il programma immettere il nome del file EXE, seguito da due numeri, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="52c1e-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a><span data-ttu-id="52c1e-123">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="52c1e-123">Compiling the Code</span></span>  
 <span data-ttu-id="52c1e-124">Per compilare il file `MathLibrary.DLL`, compilare i due file `Add` e `Mult` usando la seguente riga di comando.</span><span class="sxs-lookup"><span data-stu-id="52c1e-124">To build the file `MathLibrary.DLL`, compile the two files `Add` and `Mult` by using the following command line.</span></span>  
  
```console  
vbc -target:library -out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 <span data-ttu-id="52c1e-125">Il [-target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) opzione del compilatore indica al compilatore di generare un file DLL anziché un file EXE.</span><span class="sxs-lookup"><span data-stu-id="52c1e-125">The [-target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) compiler option tells the compiler to output a DLL instead of an EXE file.</span></span> <span data-ttu-id="52c1e-126">Il [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) opzione del compilatore seguita da un nome di file consente di specificare il nome del file DLL.</span><span class="sxs-lookup"><span data-stu-id="52c1e-126">The [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) compiler option followed by a file name is used to specify the DLL file name.</span></span> <span data-ttu-id="52c1e-127">In caso contrario il compilatore usa il primo file (`Add.vb`) come nome della DLL.</span><span class="sxs-lookup"><span data-stu-id="52c1e-127">Otherwise, the compiler uses the first file (`Add.vb`) as the name of the DLL.</span></span>  
  
 <span data-ttu-id="52c1e-128">Per compilare il file eseguibile, `TestCode.exe`, usare la seguente riga di comando:</span><span class="sxs-lookup"><span data-stu-id="52c1e-128">To build the executable file, `TestCode.exe`, use the following command line:</span></span>  
  
```console  
vbc -out:TestCode.exe -reference:MathLibrary.DLL TestCode.vb  
```  
  
 <span data-ttu-id="52c1e-129">Il **-out** l'opzione del compilatore indica al compilatore di generare un file EXE e specifica il nome del file di output (`TestCode.exe`).</span><span class="sxs-lookup"><span data-stu-id="52c1e-129">The **-out** compiler option tells the compiler to output an EXE file and specifies the name of the output file (`TestCode.exe`).</span></span> <span data-ttu-id="52c1e-130">Questa opzione del compilatore è opzionale.</span><span class="sxs-lookup"><span data-stu-id="52c1e-130">This compiler option is optional.</span></span> <span data-ttu-id="52c1e-131">Il [-riferimenti (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) opzione del compilatore specifica i file DLL utilizzati dal programma.</span><span class="sxs-lookup"><span data-stu-id="52c1e-131">The [-reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) compiler option specifies the DLL file or files that this program uses.</span></span>  
  
 <span data-ttu-id="52c1e-132">Per altre informazioni sulla compilazione dalla riga di comando, vedere e [compilazione dalla riga di comando](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="52c1e-132">For more information about building from the command line, see  and [Building from the Command Line](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52c1e-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52c1e-133">See also</span></span>

- [<span data-ttu-id="52c1e-134">Nozioni di base sulla programmazione</span><span class="sxs-lookup"><span data-stu-id="52c1e-134">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="52c1e-135">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="52c1e-135">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="52c1e-136">Creazione di una classe che contenga le funzioni DLL</span><span class="sxs-lookup"><span data-stu-id="52c1e-136">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
