---
title: Accesso agli attributi tramite reflection
ms.date: 07/20/2015
ms.assetid: c56e41da-5433-464f-a7bf-2a722e78bc9f
ms.openlocfilehash: c0da5c4ae00eb2bc80b10f63f4bfd39763445e55
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400758"
---
# <a name="accessing-attributes-by-using-reflection-visual-basic"></a><span data-ttu-id="df092-102">Accesso agli attributi tramite reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df092-102">Accessing Attributes by Using Reflection (Visual Basic)</span></span>

<span data-ttu-id="df092-103">La possibilità di definire attributi personalizzati e inserirli nel codice sorgente sarebbe di scarso valore senza un metodo per recuperare e usare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="df092-103">The fact that you can define custom attributes and place them in your source code would be of little value without some way of retrieving that information and acting on it.</span></span> <span data-ttu-id="df092-104">Tramite l'uso di reflection, è possibile recuperare le informazioni definite con gli attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="df092-104">By using reflection, you can retrieve the information that was defined with custom attributes.</span></span> <span data-ttu-id="df092-105">Il metodo chiave è `GetCustomAttributes`, che restituisce una matrice di oggetti che rappresentano gli equivalenti in fase di esecuzione degli attributi di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="df092-105">The key method is `GetCustomAttributes`, which returns an array of objects that are the run-time equivalents of the source code attributes.</span></span> <span data-ttu-id="df092-106">Questo metodo ha versioni diverse sottoposte a overload.</span><span class="sxs-lookup"><span data-stu-id="df092-106">This method has several overloaded versions.</span></span> <span data-ttu-id="df092-107">Per altre informazioni, vedere <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="df092-107">For more information, see <xref:System.Attribute>.</span></span>

<span data-ttu-id="df092-108">Una specifica di attributo come la seguente:</span><span class="sxs-lookup"><span data-stu-id="df092-108">An attribute specification such as:</span></span>

```vb
<Author("P. Ackerman", Version:=1.1)>
Class SampleClass
    ' P. Ackerman's code goes here...
End Class
```

 <span data-ttu-id="df092-109">è concettualmente equivalente a questa:</span><span class="sxs-lookup"><span data-stu-id="df092-109">is conceptually equivalent to this:</span></span>

```vb
Dim anonymousAuthorObject As Author = New Author("P. Ackerman")
anonymousAuthorObject.version = 1.1
```

<span data-ttu-id="df092-110">Il codice non viene tuttavia eseguito fino a quando non vengono eseguite query su `SampleClass` per gli attributi.</span><span class="sxs-lookup"><span data-stu-id="df092-110">However, the code is not executed until `SampleClass` is queried for attributes.</span></span> <span data-ttu-id="df092-111">La chiamata a `GetCustomAttributes` in `SampleClass` causa la costruzione e l'inizializzazione di un oggetto `Author` come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="df092-111">Calling `GetCustomAttributes` on `SampleClass` causes an `Author` object to be constructed and initialized as above.</span></span> <span data-ttu-id="df092-112">Se la classe ha altri attributi, gli altri oggetti di attributo vengono costruiti in modo analogo.</span><span class="sxs-lookup"><span data-stu-id="df092-112">If the class has other attributes, other attribute objects are constructed similarly.</span></span> <span data-ttu-id="df092-113">`GetCustomAttributes` restituisce quindi l'oggetto `Author` e tutti gli altri oggetti di attributo in una matrice.</span><span class="sxs-lookup"><span data-stu-id="df092-113">`GetCustomAttributes` then returns the `Author` object and any other attribute objects in an array.</span></span> <span data-ttu-id="df092-114">È quindi possibile eseguire l'iterazione di questa matrice, determinare gli attributi applicati in base al tipo di ogni elemento della matrice ed estrarre informazioni dagli oggetti di attributo.</span><span class="sxs-lookup"><span data-stu-id="df092-114">You can then iterate over this array, determine what attributes were applied based on the type of each array element, and extract information from the attribute objects.</span></span>

## <a name="example"></a><span data-ttu-id="df092-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="df092-115">Example</span></span>

<span data-ttu-id="df092-116">Questo è un esempio completo.</span><span class="sxs-lookup"><span data-stu-id="df092-116">Here is a complete example.</span></span> <span data-ttu-id="df092-117">Un attributo personalizzato viene definito, applicato a varie entità e recuperato tramite reflection.</span><span class="sxs-lookup"><span data-stu-id="df092-117">A custom attribute is defined, applied to several entities, and retrieved via reflection.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="df092-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df092-118">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="df092-119">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="df092-119">Visual Basic Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="df092-120">Recupero di informazioni memorizzate negli attributi</span><span class="sxs-lookup"><span data-stu-id="df092-120">Retrieving Information Stored in Attributes</span></span>](../../../../standard/attributes/retrieving-information-stored-in-attributes.md)
- [<span data-ttu-id="df092-121">Reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df092-121">Reflection (Visual Basic)</span></span>](../reflection.md)
- [<span data-ttu-id="df092-122">Attributi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df092-122">Attributes (Visual Basic)</span></span>](../../../language-reference/attributes.md)
- [<span data-ttu-id="df092-123">Creazione di attributi personalizzati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df092-123">Creating Custom Attributes (Visual Basic)</span></span>](creating-custom-attributes.md)
