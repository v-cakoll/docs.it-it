---
title: Accesso di membro condiviso tramite un'istanza; l'espressione di qualificazione non verrà valutata
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 311f4c025072162e0cfb6b87587f8602d33fcd19
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64646874"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a><span data-ttu-id="72fb4-102">Accesso di membro condiviso tramite un'istanza; l'espressione di qualificazione non verrà valutata</span><span class="sxs-lookup"><span data-stu-id="72fb4-102">Access of shared member through an instance; qualifying expression will not be evaluated</span></span>
<span data-ttu-id="72fb4-103">Una variabile di istanza di una classe o struttura viene usata per accedere a un `Shared` variabile, proprietà, routine o evento definito in quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="72fb4-103">An instance variable of a class or structure is used to access a `Shared` variable, property, procedure, or event defined in that class or structure.</span></span> <span data-ttu-id="72fb4-104">Questo avviso può verificarsi anche se una variabile di istanza viene utilizzata per accedere a un membro condiviso in modo implicito di una classe o struttura, ad esempio una costante o enumerazione, o una classe annidata o una struttura.</span><span class="sxs-lookup"><span data-stu-id="72fb4-104">This warning can also occur if an instance variable is used to access an implicitly shared member of a class or structure, such as a constant or enumeration, or a nested class or structure.</span></span>  
  
 <span data-ttu-id="72fb4-105">Lo scopo della condivisione di un membro consiste nel creare una sola copia di tale membro e rendere disponibili per ogni istanza della classe o struttura in cui è dichiarata unica copia.</span><span class="sxs-lookup"><span data-stu-id="72fb4-105">The purpose of sharing a member is to create only a single copy of that member and make that single copy available to every instance of the class or structure in which it is declared.</span></span> <span data-ttu-id="72fb4-106">È coerenza con lo scopo per accedere a un `Shared` membro tramite il nome della relativa classe o struttura, anziché tramite una variabile che contiene una singola istanza di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="72fb4-106">It is consistent with this purpose to access a `Shared` member through the name of its class or structure, rather than through a variable that holds an individual instance of that class or structure.</span></span>  
  
 <span data-ttu-id="72fb4-107">L'accesso a un `Shared` membro tramite una variabile di istanza può rendere più difficile da comprendere nascondendo il fatto che il membro è il codice `Shared`.</span><span class="sxs-lookup"><span data-stu-id="72fb4-107">Accessing a `Shared` member through an instance variable can make your code more difficult to understand by obscuring the fact that the member is `Shared`.</span></span> <span data-ttu-id="72fb4-108">Inoltre, se tale accesso fa parte di un'espressione che esegue altre azioni, ad esempio un `Function` procedure che restituisce un'istanza del membro condiviso, Visual Basic consente di ignorare l'espressione e tutte le altre azioni che altrimenti verrebbero eseguite.</span><span class="sxs-lookup"><span data-stu-id="72fb4-108">Furthermore, if such access is part of an expression that performs other actions, such as a `Function` procedure that returns an instance of the shared member, Visual Basic bypasses the expression and any other actions it would otherwise perform.</span></span>  
  
 <span data-ttu-id="72fb4-109">Per altre informazioni e un esempio, vedere [condiviso](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="72fb4-109">For more information and an example, see [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
 <span data-ttu-id="72fb4-110">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="72fb4-110">By default, this message is a warning.</span></span> <span data-ttu-id="72fb4-111">Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="72fb4-111">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="72fb4-112">**ID errore:** BC42025</span><span class="sxs-lookup"><span data-stu-id="72fb4-112">**Error ID:** BC42025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="72fb4-113">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="72fb4-113">To correct this error</span></span>  
  
- <span data-ttu-id="72fb4-114">Usare il nome della classe o struttura che definisca il `Shared` membro per accedervi, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="72fb4-114">Use the name of the class or structure that defines the `Shared` member to access it, as shown in the following example.</span></span>  
  
```vb  
Public Class testClass  
    Public Shared Sub sayHello()  
        MsgBox("Hello")  
    End Sub  
End Class  
  
Module testModule  
    Public Sub Main()  
        ' Access a shared method through an instance variable.  
        ' This generates a warning.  
        Dim tc As New testClass  
        tc.sayHello()  
  
        ' Access a shared method by using the class name.  
        ' This does not generate a warning.  
        testClass.sayHello()  
    End Sub  
End Module  
```  
  
> [!NOTE]
>  <span data-ttu-id="72fb4-115">Prestare particolare attenzione agli effetti dell'ambito quando due elementi di programmazione hanno lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="72fb4-115">Be alert for the effects of scope when two programming elements have the same name.</span></span> <span data-ttu-id="72fb4-116">Nell'esempio precedente, se si dichiara un'istanza usando `Dim testClass as testClass = Nothing`, il compilatore considera una chiamata a `testClass.sayHello()` non appena si verifica un accesso al metodo tramite il nome della classe e alcun messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="72fb4-116">In the previous example, if you declare an instance by using `Dim testClass as testClass = Nothing`, the compiler treats a call to `testClass.sayHello()` as an access of the method through the class name, and no warning occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72fb4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72fb4-117">See also</span></span>

- [<span data-ttu-id="72fb4-118">Shared</span><span class="sxs-lookup"><span data-stu-id="72fb4-118">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="72fb4-119">Scope in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="72fb4-119">Scope in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
