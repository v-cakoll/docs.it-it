---
title: 'Procedura: eseguire l''override del metodo ToString (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 60cec855286a3bb572a0bacd08c0f7920a1fc912
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="af085-102">Procedura: eseguire l'override del metodo ToString (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="af085-102">How to: Override the ToString Method (C# Programming Guide)</span></span>
<span data-ttu-id="af085-103">Ogni classe o struct in C# eredita in modo implicito la classe <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="af085-103">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="af085-104">Ogni oggetto in C# ottiene quindi il metodo <xref:System.Object.ToString%2A>, che restituisce una rappresentazione di stringa dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="af085-104">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="af085-105">Ad esempio, tutte le variabili di tipo `int` hanno un metodo `ToString` che consente loro di restituire il rispettivo contenuto sotto forma di stringa:</span><span class="sxs-lookup"><span data-stu-id="af085-105">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 <span data-ttu-id="af085-106">[!code-cs[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="af085-106">[!code-cs[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]</span></span>  
  
 <span data-ttu-id="af085-107">Quando si crea una classe o uno struct personalizzato, eseguire l'override del metodo <xref:System.Object.ToString%2A> per fornire informazioni sul tipo al codice client.</span><span class="sxs-lookup"><span data-stu-id="af085-107">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="af085-108">Per informazioni sull'uso di stringhe di formato e altri tipi di formattazione personalizzata con il metodo `ToString`, vedere [Formattazione di tipi](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="af085-108">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="af085-109">Dopo aver deciso quali informazioni comunicare tramite questo metodo, considerare se la classe o lo struct sarà usato da codice non attendibile.</span><span class="sxs-lookup"><span data-stu-id="af085-109">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="af085-110">Verificare attentamente di non indicare informazioni che potrebbero essere sfruttate da malware.</span><span class="sxs-lookup"><span data-stu-id="af085-110">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
### <a name="to-override-the-tostring-method-in-your-class-or-struct"></a><span data-ttu-id="af085-111">Per eseguire l'override del metodo ToString nella classe o nello struct</span><span class="sxs-lookup"><span data-stu-id="af085-111">To override the ToString method in your class or struct</span></span>  
  
1.  <span data-ttu-id="af085-112">Dichiarare un metodo `ToString` con i modificatori e il tipo restituito seguenti:</span><span class="sxs-lookup"><span data-stu-id="af085-112">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2.  <span data-ttu-id="af085-113">Implementare il metodo in modo che restituisca una stringa.</span><span class="sxs-lookup"><span data-stu-id="af085-113">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="af085-114">L'esempio seguente restituisce il nome della classe oltre ai dati specifici per una particolare istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="af085-114">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     <span data-ttu-id="af085-115">[!code-cs[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="af085-115">[!code-cs[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]</span></span>  
  
     <span data-ttu-id="af085-116">È anche possibile testare il metodo `ToString` come illustrato nel codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="af085-116">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     <span data-ttu-id="af085-117">[!code-cs[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="af085-117">[!code-cs[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af085-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af085-118">See Also</span></span>  
 <span data-ttu-id="af085-119"><xref:System.IFormattable></span><span class="sxs-lookup"><span data-stu-id="af085-119"><xref:System.IFormattable></span></span>   
 <span data-ttu-id="af085-120">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="af085-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="af085-121">[Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="af085-121">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="af085-122">[Stringhe](../../../csharp/programming-guide/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="af085-122">[Strings](../../../csharp/programming-guide/strings/index.md) </span></span>  
 <span data-ttu-id="af085-123">[string](../../../csharp/language-reference/keywords/string.md) </span><span class="sxs-lookup"><span data-stu-id="af085-123">[string](../../../csharp/language-reference/keywords/string.md) </span></span>  
 <span data-ttu-id="af085-124">[new](../../../csharp/language-reference/keywords/new.md) </span><span class="sxs-lookup"><span data-stu-id="af085-124">[new](../../../csharp/language-reference/keywords/new.md) </span></span>  
 <span data-ttu-id="af085-125">[override](../../../csharp/language-reference/keywords/override.md) </span><span class="sxs-lookup"><span data-stu-id="af085-125">[override](../../../csharp/language-reference/keywords/override.md) </span></span>  
 <span data-ttu-id="af085-126">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span><span class="sxs-lookup"><span data-stu-id="af085-126">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span></span>  
 [<span data-ttu-id="af085-127">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="af085-127">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)

