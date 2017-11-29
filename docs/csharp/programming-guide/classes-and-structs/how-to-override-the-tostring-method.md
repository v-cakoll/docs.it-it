---
title: 'Procedura: eseguire l''override del metodo ToString (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5b0f7bf35e5bd565e0bfa46fe91cf86aedcd2d8e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="4d221-102">Procedura: eseguire l'override del metodo ToString (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="4d221-102">How to: Override the ToString Method (C# Programming Guide)</span></span>
<span data-ttu-id="4d221-103">Ogni classe o struct in C# eredita in modo implicito la classe <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="4d221-103">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="4d221-104">Ogni oggetto in C# ottiene quindi il metodo <xref:System.Object.ToString%2A>, che restituisce una rappresentazione di stringa dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="4d221-104">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="4d221-105">Ad esempio, tutte le variabili di tipo `int` hanno un metodo `ToString` che consente loro di restituire il rispettivo contenuto sotto forma di stringa:</span><span class="sxs-lookup"><span data-stu-id="4d221-105">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]  
  
 <span data-ttu-id="4d221-106">Quando si crea una classe o uno struct personalizzato, eseguire l'override del metodo <xref:System.Object.ToString%2A> per fornire informazioni sul tipo al codice client.</span><span class="sxs-lookup"><span data-stu-id="4d221-106">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="4d221-107">Per informazioni sull'uso di stringhe di formato e altri tipi di formattazione personalizzata con il metodo `ToString`, vedere [Formattazione di tipi](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="4d221-107">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4d221-108">Dopo aver deciso quali informazioni comunicare tramite questo metodo, considerare se la classe o lo struct sarà usato da codice non attendibile.</span><span class="sxs-lookup"><span data-stu-id="4d221-108">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="4d221-109">Verificare attentamente di non indicare informazioni che potrebbero essere sfruttate da malware.</span><span class="sxs-lookup"><span data-stu-id="4d221-109">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
### <a name="to-override-the-tostring-method-in-your-class-or-struct"></a><span data-ttu-id="4d221-110">Per eseguire l'override del metodo ToString nella classe o nello struct</span><span class="sxs-lookup"><span data-stu-id="4d221-110">To override the ToString method in your class or struct</span></span>  
  
1.  <span data-ttu-id="4d221-111">Dichiarare un metodo `ToString` con i modificatori e il tipo restituito seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d221-111">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2.  <span data-ttu-id="4d221-112">Implementare il metodo in modo che restituisca una stringa.</span><span class="sxs-lookup"><span data-stu-id="4d221-112">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="4d221-113">L'esempio seguente restituisce il nome della classe oltre ai dati specifici per una particolare istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="4d221-113">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     [!code-csharp[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]  
  
     <span data-ttu-id="4d221-114">È anche possibile testare il metodo `ToString` come illustrato nel codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4d221-114">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="4d221-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d221-115">See Also</span></span>  
 <xref:System.IFormattable>  
 [<span data-ttu-id="4d221-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4d221-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4d221-117">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="4d221-117">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="4d221-118">Stringhe</span><span class="sxs-lookup"><span data-stu-id="4d221-118">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
 [<span data-ttu-id="4d221-119">string</span><span class="sxs-lookup"><span data-stu-id="4d221-119">string</span></span>](../../../csharp/language-reference/keywords/string.md)  
 [<span data-ttu-id="4d221-120">new</span><span class="sxs-lookup"><span data-stu-id="4d221-120">new</span></span>](../../../csharp/language-reference/keywords/new.md)  
 [<span data-ttu-id="4d221-121">override</span><span class="sxs-lookup"><span data-stu-id="4d221-121">override</span></span>](../../../csharp/language-reference/keywords/override.md)  
 [<span data-ttu-id="4d221-122">virtual</span><span class="sxs-lookup"><span data-stu-id="4d221-122">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)  
 [<span data-ttu-id="4d221-123">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="4d221-123">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
