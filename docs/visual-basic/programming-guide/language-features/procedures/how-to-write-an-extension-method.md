---
title: 'Procedura: scrivere un metodo di estensione (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: e220a025c39757b492be033caeb8924523515804
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648733"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="6c39f-102">Procedura: scrivere un metodo di estensione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c39f-102">How to: Write an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="6c39f-103">Metodi di estensione consentono di aggiungere metodi alla classe esistente.</span><span class="sxs-lookup"><span data-stu-id="6c39f-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="6c39f-104">Il metodo di estensione può essere chiamato come se fosse un'istanza di tale classe.</span><span class="sxs-lookup"><span data-stu-id="6c39f-104">The extension method can be called as if it were an instance of that class.</span></span>  
  
### <a name="to-define-an-extension-method"></a><span data-ttu-id="6c39f-105">Per definire un metodo di estensione</span><span class="sxs-lookup"><span data-stu-id="6c39f-105">To define an extension method</span></span>  
  
1.  <span data-ttu-id="6c39f-106">Aprire un'applicazione nuova o esistente di Visual Basic in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6c39f-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="6c39f-107">Nella parte superiore del file in cui si desidera definire un metodo di estensione, includere l'istruzione di importazione seguente:</span><span class="sxs-lookup"><span data-stu-id="6c39f-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3.  <span data-ttu-id="6c39f-108">All'interno di un modulo nuovo o esistente nell'applicazione in uso, iniziare la definizione di metodo con l'attributo di estensione:</span><span class="sxs-lookup"><span data-stu-id="6c39f-108">Within a module in your new or existing application, begin the method definition with the extension attribute:</span></span>  
  
    ```  
    <Extension()>  
    ```  
  
4.  <span data-ttu-id="6c39f-109">Dichiarare il metodo in modo normale, ad eccezione del fatto che il tipo del primo parametro deve essere il tipo di dati che si desidera estendere.</span><span class="sxs-lookup"><span data-stu-id="6c39f-109">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## <a name="example"></a><span data-ttu-id="6c39f-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="6c39f-110">Example</span></span>  
 <span data-ttu-id="6c39f-111">Nell'esempio seguente viene dichiarato un metodo di estensione nel modulo `StringExtensions`.</span><span class="sxs-lookup"><span data-stu-id="6c39f-111">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="6c39f-112">Un secondo modulo `Module1`, Importa `StringExtensions` e chiama il metodo.</span><span class="sxs-lookup"><span data-stu-id="6c39f-112">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="6c39f-113">Il metodo di estensione deve essere nell'ambito quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="6c39f-113">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="6c39f-114">Metodo di estensione `PrintAndPunctuate` estende la <xref:System.String> classe con un metodo che visualizza l'istanza di stringa seguiti da una stringa di segni di punteggiatura inviati come parametro.</span><span class="sxs-lookup"><span data-stu-id="6c39f-114">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>  
  
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
  
 <span data-ttu-id="6c39f-115">Si noti che il metodo viene definito con due parametri e chiamato con una sola.</span><span class="sxs-lookup"><span data-stu-id="6c39f-115">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="6c39f-116">Il primo parametro, `aString`, nel metodo di definizione è associato a `example`, l'istanza di `String` che chiama il metodo.</span><span class="sxs-lookup"><span data-stu-id="6c39f-116">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="6c39f-117">L'output dell'esempio è la seguente:</span><span class="sxs-lookup"><span data-stu-id="6c39f-117">The output of the example is as follows:</span></span>  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a><span data-ttu-id="6c39f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c39f-118">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>  
 [<span data-ttu-id="6c39f-119">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="6c39f-119">Extension Methods</span></span>](./extension-methods.md)  
 [<span data-ttu-id="6c39f-120">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="6c39f-120">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [<span data-ttu-id="6c39f-121">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="6c39f-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="6c39f-122">Ambito in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6c39f-122">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
