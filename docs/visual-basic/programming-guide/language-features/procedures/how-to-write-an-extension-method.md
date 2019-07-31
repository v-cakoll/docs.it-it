---
title: 'Procedura: Scrivere un metodo di estensione (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 7a7a9d16d9f69071e9d1dacb0558f7ca92e1d21e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631029"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="a80ea-102">Procedura: Scrivere un metodo di estensione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a80ea-102">How to: Write an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="a80ea-103">I metodi di estensione consentono di aggiungere metodi a una classe esistente.</span><span class="sxs-lookup"><span data-stu-id="a80ea-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="a80ea-104">Il metodo di estensione può essere chiamato come se fosse un'istanza di tale classe.</span><span class="sxs-lookup"><span data-stu-id="a80ea-104">The extension method can be called as if it were an instance of that class.</span></span>

### <a name="to-define-an-extension-method"></a><span data-ttu-id="a80ea-105">Per definire un metodo di estensione</span><span class="sxs-lookup"><span data-stu-id="a80ea-105">To define an extension method</span></span>

1. <span data-ttu-id="a80ea-106">Aprire un'applicazione Visual Basic nuova o esistente in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a80ea-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>

2. <span data-ttu-id="a80ea-107">Nella parte superiore del file in cui si desidera definire un metodo di estensione, includere l'istruzione import seguente:</span><span class="sxs-lookup"><span data-stu-id="a80ea-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. <span data-ttu-id="a80ea-108">All'interno di un modulo nell'applicazione nuova o esistente, iniziare la definizione del metodo con l'attributo di estensione:</span><span class="sxs-lookup"><span data-stu-id="a80ea-108">Within a module in your new or existing application, begin the method definition with the extension attribute:</span></span>

    ```vb
    <Extension()>
    ```

4. <span data-ttu-id="a80ea-109">Dichiarare il metodo nel modo consueto, ad eccezione del fatto che il tipo del primo parametro deve essere il tipo di dati che si desidera estendere.</span><span class="sxs-lookup"><span data-stu-id="a80ea-109">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>

    ```vb
    <Extension()>
    Public Sub SubName (ByVal para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a><span data-ttu-id="a80ea-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="a80ea-110">Example</span></span>
 <span data-ttu-id="a80ea-111">Nell'esempio seguente viene dichiarato un metodo di estensione nel `StringExtensions`modulo.</span><span class="sxs-lookup"><span data-stu-id="a80ea-111">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="a80ea-112">Un secondo modulo, `Module1`, importa `StringExtensions` e chiama il metodo.</span><span class="sxs-lookup"><span data-stu-id="a80ea-112">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="a80ea-113">Il metodo di estensione deve essere nell'ambito quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="a80ea-113">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="a80ea-114">Il metodo `PrintAndPunctuate` di estensione <xref:System.String> estende la classe con un metodo che Visualizza l'istanza di stringa seguita da una stringa di segni di punteggiatura inviati come parametro.</span><span class="sxs-lookup"><span data-stu-id="a80ea-114">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>
  
```vb
' Declarations will typically be in a separate module.
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
        Console.WriteLine(aString & punc)
    End Sub

End Module
```

```vb
' Import the module that holds the extension method you want to use,
' and call it.

Imports ConsoleApplication2.StringExtensions

Module Module1
  
    Sub Main()
        Dim example = "Hello"
        example.PrintAndPunctuate("?")
        example.PrintAndPunctuate("!!!!")
    End Sub
    
End Module
```
  
 <span data-ttu-id="a80ea-115">Si noti che il metodo viene definito con due parametri e viene chiamato con una sola.</span><span class="sxs-lookup"><span data-stu-id="a80ea-115">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="a80ea-116">Il primo parametro, `aString`, nella definizione del metodo è associato a `example`, l'istanza di `String` che chiama il metodo.</span><span class="sxs-lookup"><span data-stu-id="a80ea-116">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="a80ea-117">L'output dell'esempio è il seguente:</span><span class="sxs-lookup"><span data-stu-id="a80ea-117">The output of the example is as follows:</span></span>
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a><span data-ttu-id="a80ea-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a80ea-118">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="a80ea-119">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="a80ea-119">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="a80ea-120">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="a80ea-120">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="a80ea-121">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="a80ea-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a80ea-122">Ambito in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a80ea-122">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
