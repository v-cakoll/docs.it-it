---
title: 'Procedura: Scrivere un metodo di estensione (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: d01596d50db8ba1078e8ac82caa951418645c977
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004609"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="c065b-102">Procedura: Scrivere un metodo di estensione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c065b-102">How to: Write an Extension Method (Visual Basic)</span></span>

<span data-ttu-id="c065b-103">I metodi di estensione consentono di aggiungere metodi a una classe esistente.</span><span class="sxs-lookup"><span data-stu-id="c065b-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="c065b-104">Il metodo di estensione può essere chiamato come se fosse un'istanza di tale classe.</span><span class="sxs-lookup"><span data-stu-id="c065b-104">The extension method can be called as if it were an instance of that class.</span></span>

### <a name="to-define-an-extension-method"></a><span data-ttu-id="c065b-105">Per definire un metodo di estensione</span><span class="sxs-lookup"><span data-stu-id="c065b-105">To define an extension method</span></span>

1. <span data-ttu-id="c065b-106">Aprire un'applicazione Visual Basic nuova o esistente in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c065b-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>

2. <span data-ttu-id="c065b-107">Nella parte superiore del file in cui si desidera definire un metodo di estensione, includere l'istruzione import seguente:</span><span class="sxs-lookup"><span data-stu-id="c065b-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. <span data-ttu-id="c065b-108">All'interno di un modulo nell'applicazione nuova o esistente, iniziare la definizione del metodo con l'attributo [`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute) :</span><span class="sxs-lookup"><span data-stu-id="c065b-108">Within a module in your new or existing application, begin the method definition with the [`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute) attribute:</span></span>

    ```vb
    <Extension()>
    ```
 
   <span data-ttu-id="c065b-109">Si noti che l'attributo `Extension` può essere applicato solo a un metodo, ovvero una procedura `Sub` o `Function`, in un [modulo](../../../language-reference/statements/module-statement.md)Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c065b-109">Note that the `Extension` attribute can only be applied to a method (a `Sub` or `Function` procedure) in a Visual Basic [Module](../../../language-reference/statements/module-statement.md).</span></span> <span data-ttu-id="c065b-110">Se lo si applica a un metodo in un `Class` o un `Structure`, il compilatore Visual Basic genera l'errore [BC36551](../../../misc/bc36551.md)"i metodi di estensione possono essere definiti solo nei moduli".</span><span class="sxs-lookup"><span data-stu-id="c065b-110">If you apply it to a method in a `Class` or a `Structure`, the Visual Basic compiler generates error [BC36551](../../../misc/bc36551.md), "Extension methods can be defined only in modules."</span></span>

4. <span data-ttu-id="c065b-111">Dichiarare il metodo nel modo consueto, ad eccezione del fatto che il tipo del primo parametro deve essere il tipo di dati che si desidera estendere.</span><span class="sxs-lookup"><span data-stu-id="c065b-111">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>

    ```vb
    <Extension()>
    Public Sub SubName(para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a><span data-ttu-id="c065b-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="c065b-112">Example</span></span>

 <span data-ttu-id="c065b-113">Nell'esempio seguente viene dichiarato un metodo di estensione nel modulo `StringExtensions`.</span><span class="sxs-lookup"><span data-stu-id="c065b-113">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="c065b-114">Un secondo modulo, `Module1`, importa `StringExtensions` e chiama il metodo.</span><span class="sxs-lookup"><span data-stu-id="c065b-114">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="c065b-115">Il metodo di estensione deve essere nell'ambito quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="c065b-115">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="c065b-116">Il metodo di estensione `PrintAndPunctuate` estende la classe <xref:System.String> con un metodo che Visualizza l'istanza di stringa seguita da una stringa di simboli di punteggiatura inviati come parametro.</span><span class="sxs-lookup"><span data-stu-id="c065b-116">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>
  
```vb
' Declarations will typically be in a separate module.
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(aString As String, punc As String)
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
  
 <span data-ttu-id="c065b-117">Si noti che il metodo viene definito con due parametri e viene chiamato con una sola.</span><span class="sxs-lookup"><span data-stu-id="c065b-117">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="c065b-118">Il primo parametro, `aString`, nella definizione del metodo è associato a `example`, l'istanza di `String` che chiama il metodo.</span><span class="sxs-lookup"><span data-stu-id="c065b-118">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="c065b-119">L'output dell'esempio è il seguente:</span><span class="sxs-lookup"><span data-stu-id="c065b-119">The output of the example is as follows:</span></span>
  
 ```console
 Hello?
 Hello!!!!
 ```
  
## <a name="see-also"></a><span data-ttu-id="c065b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c065b-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="c065b-121">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="c065b-121">Extension Methods</span></span>](extension-methods.md)
- [<span data-ttu-id="c065b-122">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="c065b-122">Module Statement</span></span>](../../../language-reference/statements/module-statement.md)
- [<span data-ttu-id="c065b-123">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="c065b-123">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="c065b-124">Ambito in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c065b-124">Scope in Visual Basic</span></span>](../declared-elements/scope.md)
