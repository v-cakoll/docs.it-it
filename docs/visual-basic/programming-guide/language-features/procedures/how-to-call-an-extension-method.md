---
title: 'Procedura: chiamare un metodo di estensione (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 25b5a86af15694e6f64f96a5d5d645a01f8f1f12
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-extension-method-visual-basic"></a><span data-ttu-id="96153-102">Procedura: chiamare un metodo di estensione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96153-102">How to: Call an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="96153-103">Metodi di estensione consentono di aggiungere metodi alla classe esistente.</span><span class="sxs-lookup"><span data-stu-id="96153-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="96153-104">Dopo che un metodo di estensione è dichiarato e inserito nell'ambito, è possibile chiamare questo metodo di istanza del tipo che estende.</span><span class="sxs-lookup"><span data-stu-id="96153-104">After an extension method is declared and brought into scope, you can call it like an instance method of the type that it extends.</span></span> <span data-ttu-id="96153-105">Per ulteriori informazioni su come scrivere un metodo di estensione, vedere [procedura: scrivere un metodo di estensione](./how-to-write-an-extension-method.md).</span><span class="sxs-lookup"><span data-stu-id="96153-105">For more information about how to write an extension method, see [How to: Write an Extension Method](./how-to-write-an-extension-method.md).</span></span>  
  
 <span data-ttu-id="96153-106">Le istruzioni seguenti fanno riferimento al metodo di estensione `PrintAndPunctuate`, che visualizza l'istanza di stringa che richiama, seguita dal valore inviato per il secondo parametro, `punc`.</span><span class="sxs-lookup"><span data-stu-id="96153-106">The following instructions refer to extension method `PrintAndPunctuate`, which will display the string instance that invokes it, followed by whatever value is sent in for the second parameter, `punc`.</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="96153-107">Il metodo deve essere nell'ambito quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="96153-107">The method must be in scope when it is called.</span></span>  
  
### <a name="to-call-an-extension-method"></a><span data-ttu-id="96153-108">Per chiamare un metodo di estensione</span><span class="sxs-lookup"><span data-stu-id="96153-108">To call an extension method</span></span>  
  
1.  <span data-ttu-id="96153-109">Dichiarare una variabile con il tipo di dati del primo parametro del metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="96153-109">Declare a variable that has the data type of the first parameter of the extension method.</span></span> <span data-ttu-id="96153-110">Per `PrintAndPunctuate`, è necessario un <xref:System.String> variabile:</span><span class="sxs-lookup"><span data-stu-id="96153-110">For `PrintAndPunctuate`, you need a <xref:System.String> variable:</span></span>  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2.  <span data-ttu-id="96153-111">Variabile richiama il metodo di estensione che il valore è associato il primo parametro, `aString`.</span><span class="sxs-lookup"><span data-stu-id="96153-111">That variable will invoke the extension method, and its value is bound to the first parameter, `aString`.</span></span> <span data-ttu-id="96153-112">Verrà visualizzata la seguente istruzione di chiamata `Ready?`.</span><span class="sxs-lookup"><span data-stu-id="96153-112">The following calling statement will display `Ready?`.</span></span>  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     <span data-ttu-id="96153-113">Si noti che la chiamata a questo metodo di estensione è analoga a una chiamata a uno qualsiasi del <xref:System.String> metodi che richiedono un parametro di istanza:</span><span class="sxs-lookup"><span data-stu-id="96153-113">Notice that the call to this extension method looks just like a call to any one of the <xref:System.String> instance methods that require one parameter:</span></span>  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3.  <span data-ttu-id="96153-114">Dichiarare un'altra variabile di stringa e chiamare nuovamente il metodo per verificare che funziona con qualsiasi stringa.</span><span class="sxs-lookup"><span data-stu-id="96153-114">Declare another string variable and call the method again to see that it works with any string.</span></span>  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     <span data-ttu-id="96153-115">In questo caso il risultato è: `or not!!!`.</span><span class="sxs-lookup"><span data-stu-id="96153-115">The result this time is: `or not!!!`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96153-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="96153-116">Example</span></span>  
 <span data-ttu-id="96153-117">Il codice seguente è un esempio completo di creazione e utilizzo di un metodo di estensione semplice.</span><span class="sxs-lookup"><span data-stu-id="96153-117">The following code is a complete example of the creation and use of a simple extension method.</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
Imports ConsoleApplication1.StringExtensions  
  
Module Module1  
  
    Sub Main()  
  
        Dim example = "Hello"  
        example.PrintAndPunctuate(".")  
        example.PrintAndPunctuate("!!!!")  
  
        Dim example2 = "Goodbye"  
        example2.PrintAndPunctuate("?")  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
End Module  
  
' Output:  
' Hello.  
' Hello!!!!  
' Goodbye?  
```  
  
## <a name="see-also"></a><span data-ttu-id="96153-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96153-118">See Also</span></span>  
 [<span data-ttu-id="96153-119">Procedura: Scrivere un metodo di estensione</span><span class="sxs-lookup"><span data-stu-id="96153-119">How to: Write an Extension Method</span></span>](./how-to-write-an-extension-method.md)  
 [<span data-ttu-id="96153-120">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="96153-120">Extension Methods</span></span>](./extension-methods.md)  
 [<span data-ttu-id="96153-121">Ambito in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96153-121">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
