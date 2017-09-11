---
title: Accesso agli attributi tramite Reflection (Visual Basic) | Documenti di Microsoft
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
ms.assetid: c56e41da-5433-464f-a7bf-2a722e78bc9f
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ac1e017ae13fc1291fd41e5747171160a9d70238
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="accessing-attributes-by-using-reflection-visual-basic"></a><span data-ttu-id="35c03-102">Accesso agli attributi tramite Reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35c03-102">Accessing Attributes by Using Reflection (Visual Basic)</span></span>
<span data-ttu-id="35c03-103">Il fatto che è possibile definire gli attributi personalizzati e inserirli nel codice sorgente sarebbe di scarso valore senza un metodo per recuperare le informazioni e che agisce su di esso.</span><span class="sxs-lookup"><span data-stu-id="35c03-103">The fact that you can define custom attributes and place them in your source code would be of little value without some way of retrieving that information and acting on it.</span></span> <span data-ttu-id="35c03-104">Tramite la reflection per recuperare le informazioni che è state definite con gli attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="35c03-104">By using reflection, you can retrieve the information that was defined with custom attributes.</span></span> <span data-ttu-id="35c03-105">Il metodo chiave è `GetCustomAttributes`, che restituisce una matrice di oggetti che rappresentano gli equivalenti in fase di esecuzione degli attributi di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="35c03-105">The key method is `GetCustomAttributes`, which returns an array of objects that are the run-time equivalents of the source code attributes.</span></span> <span data-ttu-id="35c03-106">Questo metodo dispone di diverse versioni di overload.</span><span class="sxs-lookup"><span data-stu-id="35c03-106">This method has several overloaded versions.</span></span> <span data-ttu-id="35c03-107">Per ulteriori informazioni, vedere <xref:System.Attribute>.</xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="35c03-107">For more information, see <xref:System.Attribute>.</span></span>  
  
 <span data-ttu-id="35c03-108">Specifica un attributo, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="35c03-108">An attribute specification such as:</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 <span data-ttu-id="35c03-109">è concettualmente equivalente a questa:</span><span class="sxs-lookup"><span data-stu-id="35c03-109">is conceptually equivalent to this:</span></span>  
  
```vb  
Dim anonymousAuthorObject As Author = New Author("P. Ackerman")  
anonymousAuthorObject.version = 1.1  
```  
  
 <span data-ttu-id="35c03-110">Tuttavia, il codice viene eseguito solo `SampleClass` viene eseguita una query per gli attributi.</span><span class="sxs-lookup"><span data-stu-id="35c03-110">However, the code is not executed until `SampleClass` is queried for attributes.</span></span> <span data-ttu-id="35c03-111">La chiamata a `GetCustomAttributes` su `SampleClass` provoca un `Author` oggetto viene costruito e inizializzato come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="35c03-111">Calling `GetCustomAttributes` on `SampleClass` causes an `Author` object to be constructed and initialized as above.</span></span> <span data-ttu-id="35c03-112">Se la classe dispone di altri attributi, gli altri oggetti attributo sono costruiti in modo analogo.</span><span class="sxs-lookup"><span data-stu-id="35c03-112">If the class has other attributes, other attribute objects are constructed similarly.</span></span> <span data-ttu-id="35c03-113">`GetCustomAttributes`Restituisce quindi il `Author` oggetto e altri oggetti attributo in una matrice.</span><span class="sxs-lookup"><span data-stu-id="35c03-113">`GetCustomAttributes` then returns the `Author` object and any other attribute objects in an array.</span></span> <span data-ttu-id="35c03-114">È quindi possibile scorrere questa matrice, determinare gli attributi che sono stati applicati in base al tipo di ogni elemento della matrice ed estrarre informazioni da oggetti attributo.</span><span class="sxs-lookup"><span data-stu-id="35c03-114">You can then iterate over this array, determine what attributes were applied based on the type of each array element, and extract information from the attribute objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35c03-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="35c03-115">Example</span></span>  
 <span data-ttu-id="35c03-116">Ecco un esempio completo.</span><span class="sxs-lookup"><span data-stu-id="35c03-116">Here is a complete example.</span></span> <span data-ttu-id="35c03-117">Un attributo personalizzato viene definito, applicato a varie entità e recuperato tramite reflection.</span><span class="sxs-lookup"><span data-stu-id="35c03-117">A custom attribute is defined, applied to several entities, and retrieved via reflection.</span></span>  
  
```vb  
' Multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
    Private name As String  
    Public version As Double  
    Sub New(ByVal authorName As String)  
        name = authorName  
  
        ' Default value  
        version = 1.0  
    End Sub  
  
    Function GetName() As String  
        Return name  
    End Function          
End Class  
  
' Class with the Author attribute  
<Author("P. Ackerman")>   
Public Class FirstClass  
End Class  
  
' Class without the Author attribute  
Public Class SecondClass  
End Class  
  
' Class with multiple Author attributes.  
<Author("P. Ackerman"), Author("R. Koch", Version:=2.0)>   
Public Class ThirdClass  
End Class  
  
Class TestAuthorAttribute  
    Sub Main()  
        PrintAuthorInfo(GetType(FirstClass))  
        PrintAuthorInfo(GetType(SecondClass))  
        PrintAuthorInfo(GetType(ThirdClass))  
    End Sub  
  
    Private Shared Sub PrintAuthorInfo(ByVal t As System.Type)  
        System.Console.WriteLine("Author information for {0}", t)  
  
        ' Using reflection  
        Dim attrs() As System.Attribute = System.Attribute.GetCustomAttributes(t)  
  
        ' Displaying output  
        For Each attr In attrs  
            Dim a As Author = CType(attr, Author)  
            System.Console.WriteLine("   {0}, version {1:f}", a.GetName(), a.version)  
        Next              
    End Sub  
  
    ' Output:  
    '   Author information for FirstClass  
    '     P. Ackerman, version 1.00  
    ' Author information for SecondClass  
    ' Author information for ThirdClass  
    '  R. Koch, version 2.00  
    '  P. Ackerman, version 1.00  
  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="35c03-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35c03-118">See Also</span></span>  
 <span data-ttu-id="35c03-119"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="35c03-119"><xref:System.Reflection></span></span>   
 <span data-ttu-id="35c03-120"><xref:System.Attribute></xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="35c03-120"><xref:System.Attribute></span></span>   
<span data-ttu-id="35c03-121"> [Guida per programmatori Visual Basic](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="35c03-121"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="35c03-122"> [Recupero di informazioni memorizzate negli attributi](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c) </span><span class="sxs-lookup"><span data-stu-id="35c03-122"> [Retrieving Information Stored in Attributes](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c) </span></span>  
<span data-ttu-id="35c03-123"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="35c03-123"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="35c03-124"> [Attributi (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="35c03-124"> [Attributes (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="35c03-125"> [Creazione di attributi personalizzati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="35c03-125"> [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)</span></span>
