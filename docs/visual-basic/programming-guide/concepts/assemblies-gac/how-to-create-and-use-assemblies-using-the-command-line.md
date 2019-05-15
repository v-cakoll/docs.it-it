---
title: 'Procedura: Creare e usare assembly dalla riga di comando (Visual Basic)'
ms.date: 03/14/2018
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
ms.openlocfilehash: a30d4b3ea203a8b4d3ba621fc7b0310477ddf10d
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592679"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a><span data-ttu-id="7742b-102">Procedura: Creare e usare assembly dalla riga di comando (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7742b-102">How to: Create and Use Assemblies Using the Command Line (Visual Basic)</span></span>
<span data-ttu-id="7742b-103">Un assembly, o libreria a collegamento dinamico (DLL), viene collegato al programma in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7742b-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="7742b-104">Per illustrare la creazione e l'uso di una DLL, si consideri lo scenario seguente:</span><span class="sxs-lookup"><span data-stu-id="7742b-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
- <span data-ttu-id="7742b-105">`MathLibrary.DLL`: il file libreria che contiene i metodi da chiamare in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7742b-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="7742b-106">In questo esempio la DLL contiene due metodi: `Add` e `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="7742b-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
- <span data-ttu-id="7742b-107">`Add`: il file di origine che contiene il metodo `Add`.</span><span class="sxs-lookup"><span data-stu-id="7742b-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="7742b-108">Restituisce la somma dei suoi parametri.</span><span class="sxs-lookup"><span data-stu-id="7742b-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="7742b-109">La classe `AddClass` che contiene il metodo `Add` è un membro dello spazio dei nomi `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="7742b-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
- <span data-ttu-id="7742b-110">`Mult`: il codice sorgente che contiene il metodo `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="7742b-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="7742b-111">Restituisce il prodotto dei suoi parametri.</span><span class="sxs-lookup"><span data-stu-id="7742b-111">It returns the product of its parameters.</span></span> <span data-ttu-id="7742b-112">Anche la classe `MultiplyClass` che contiene il metodo `Multiply` è un membro dello spazio dei nomi `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="7742b-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
- <span data-ttu-id="7742b-113">`TestCode`: il file che contiene il metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="7742b-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="7742b-114">Usa i metodi del file DLL per calcolare la somma e il prodotto degli argomenti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7742b-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7742b-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="7742b-115">Example</span></span>  
  
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
  
 <span data-ttu-id="7742b-116">Questo file contiene l'algoritmo che usa i metodi della DLL: `Add` e `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="7742b-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="7742b-117">Inizia con l'analisi degli argomenti immessi dalla riga di comando: `num1` e `num2`.</span><span class="sxs-lookup"><span data-stu-id="7742b-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="7742b-118">Quindi calcola la somma usando il metodo `Add` sulla classe `AddClass` e il prodotto usando il metodo `Multiply` sulla classe `MultiplyClass`.</span><span class="sxs-lookup"><span data-stu-id="7742b-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="7742b-119">Si noti che il `Imports` istruzione all'inizio del file consente di usare i nomi di classe non qualificati per fare riferimento ai metodi della DLL in fase di compilazione, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7742b-119">Notice that the  `Imports` statement at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 <span data-ttu-id="7742b-120">In caso contrario è necessario usare nomi completi, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7742b-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a><span data-ttu-id="7742b-121">Esecuzione</span><span class="sxs-lookup"><span data-stu-id="7742b-121">Execution</span></span>  
 <span data-ttu-id="7742b-122">Per eseguire il programma immettere il nome del file EXE, seguito da due numeri, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7742b-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="see-also"></a><span data-ttu-id="7742b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7742b-123">See also</span></span>

- [<span data-ttu-id="7742b-124">Nozioni di base sulla programmazione</span><span class="sxs-lookup"><span data-stu-id="7742b-124">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="7742b-125">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="7742b-125">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="7742b-126">Creazione di una classe che contenga le funzioni DLL</span><span class="sxs-lookup"><span data-stu-id="7742b-126">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
