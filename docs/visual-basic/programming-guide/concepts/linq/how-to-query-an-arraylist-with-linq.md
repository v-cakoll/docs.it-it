---
title: 'Procedura: eseguire Query su un ArrayList con LINQ (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 176358a9-d765-4b57-9557-7feb4428138d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 59dd2fb9af093e2e27d5db75e0e7b886f47f2a57
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017

---
# <a name="how-to-query-an-arraylist-with-linq-visual-basic"></a><span data-ttu-id="4ea9b-102">Procedura: eseguire Query su un ArrayList con LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ea9b-102">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>
<span data-ttu-id="4ea9b-103">Quando si utilizza LINQ per non query generica <xref:System.Collections.IEnumerable>raccolte, ad esempio <xref:System.Collections.ArrayList>, è necessario dichiarare in modo esplicito il tipo della variabile di intervallo in base al tipo specifico di oggetti nella raccolta.</xref:System.Collections.ArrayList> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="4ea9b-103">When using LINQ to query non-generic <xref:System.Collections.IEnumerable> collections such as <xref:System.Collections.ArrayList>, you must explicitly declare the type of the range variable to reflect the specific type of the objects in the collection.</span></span> <span data-ttu-id="4ea9b-104">Ad esempio, se si dispone di un <xref:System.Collections.ArrayList>di `Student` oggetti, il [dalla clausola](../../../../visual-basic/language-reference/queries/from-clause.md) dovrebbe essere simile al seguente:</xref:System.Collections.ArrayList></span><span class="sxs-lookup"><span data-stu-id="4ea9b-104">For example, if you have an <xref:System.Collections.ArrayList> of `Student` objects, your [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md) should look like this:</span></span>  
  
```  
Dim query = From student As Student In arrList   
...  
```  
  
 <span data-ttu-id="4ea9b-105">Specificando il tipo della variabile di intervallo, si esegue il cast di ogni elemento di <xref:System.Collections.ArrayList>per un `Student`.</xref:System.Collections.ArrayList></span><span class="sxs-lookup"><span data-stu-id="4ea9b-105">By specifying the type of the range variable, you are casting each item in the <xref:System.Collections.ArrayList> to a `Student`.</span></span>  
  
 <span data-ttu-id="4ea9b-106">L'utilizzo di una variabile di intervallo tipizzata in modo esplicito in un'espressione di query è equivalente alla chiamata di <xref:System.Linq.Enumerable.Cast%2A>(metodo).</xref:System.Linq.Enumerable.Cast%2A></span><span class="sxs-lookup"><span data-stu-id="4ea9b-106">The use of an explicitly typed range variable in a query expression is equivalent to calling the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="4ea9b-107"><xref:System.Linq.Enumerable.Cast%2A>genera un'eccezione se non è possibile eseguire il cast specificato.</xref:System.Linq.Enumerable.Cast%2A></span><span class="sxs-lookup"><span data-stu-id="4ea9b-107"><xref:System.Linq.Enumerable.Cast%2A> throws an exception if the specified cast cannot be performed.</span></span> <span data-ttu-id="4ea9b-108"><xref:System.Linq.Enumerable.Cast%2A>e <xref:System.Linq.Enumerable.OfType%2A>sono i due metodi di operatore di Query Standard che operano su non generica <xref:System.Collections.IEnumerable>tipi.</xref:System.Collections.IEnumerable> </xref:System.Linq.Enumerable.OfType%2A></xref:System.Linq.Enumerable.Cast%2A></span><span class="sxs-lookup"><span data-stu-id="4ea9b-108"><xref:System.Linq.Enumerable.Cast%2A> and <xref:System.Linq.Enumerable.OfType%2A> are the two Standard Query Operator methods that operate on non-generic <xref:System.Collections.IEnumerable> types.</span></span> <span data-ttu-id="4ea9b-109">In Visual Basic, è necessario chiamare esplicitamente il <xref:System.Linq.Enumerable.Cast%2A>metodo sull'origine dati per garantire un tipo di variabile di intervallo specifico.</xref:System.Linq.Enumerable.Cast%2A></span><span class="sxs-lookup"><span data-stu-id="4ea9b-109">In Visual Basic, you must explicitly call the <xref:System.Linq.Enumerable.Cast%2A> method on the data source to ensure a specific range variable type.</span></span> <span data-ttu-id="4ea9b-110">Per ulteriori informazioni, vedere[relazioni tra i tipi nelle operazioni di Query (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="4ea9b-110">For more information, see[Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ea9b-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ea9b-111">Example</span></span>  
 <span data-ttu-id="4ea9b-112">Nell'esempio seguente viene illustrata una semplice query su un <xref:System.Collections.ArrayList>.</xref:System.Collections.ArrayList></span><span class="sxs-lookup"><span data-stu-id="4ea9b-112">The following example shows a simple query over an <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="4ea9b-113">Si noti che in questo esempio utilizza gli inizializzatori di oggetto quando il codice chiama il <xref:System.Collections.ArrayList.Add%2A>(metodo), ma questo non è un requisito.</xref:System.Collections.ArrayList.Add%2A></span><span class="sxs-lookup"><span data-stu-id="4ea9b-113">Note that this example uses object initializers when the code calls the <xref:System.Collections.ArrayList.Add%2A> method, but this is not a requirement.</span></span>  
  
```vb  
Imports System.Collections  
Imports System.Linq  
  
Module Module1  
  
    Public Class Student  
        Public Property FirstName As String  
        Public Property LastName As String  
        Public Property Scores As Integer()  
    End Class  
  
    Sub Main()  
  
        Dim student1 As New Student With {.FirstName = "Svetlana",   
                                     .LastName = "Omelchenko",   
                                     .Scores = New Integer() {98, 92, 81, 60}}  
        Dim student2 As New Student With {.FirstName = "Claire",   
                                    .LastName = "O'Donnell",   
                                    .Scores = New Integer() {75, 84, 91, 39}}  
        Dim student3 As New Student With {.FirstName = "Cesar",   
                                    .LastName = "Garcia",   
                                    .Scores = New Integer() {97, 89, 85, 82}}  
        Dim student4 As New Student With {.FirstName = "Sven",   
                                    .LastName = "Mortensen",   
                                    .Scores = New Integer() {88, 94, 65, 91}}  
  
        Dim arrList As New ArrayList()  
        arrList.Add(student1)  
        arrList.Add(student2)  
        arrList.Add(student3)  
        arrList.Add(student4)  
  
        ' Use an explicit type for non-generic collections  
        Dim query = From student As Student In arrList   
                    Where student.Scores(0) > 95   
                    Select student  
  
        For Each student As Student In query  
            Console.WriteLine(student.LastName & ": " & student.Scores(0))  
        Next  
        ' Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
End Module  
' Output:  
'   Omelchenko: 98  
'   Garcia: 97  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ea9b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ea9b-114">See Also</span></span>  
 [<span data-ttu-id="4ea9b-115">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ea9b-115">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)

