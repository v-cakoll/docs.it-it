---
title: Come eseguire l'override del metodo ToString- C# Guida alla programmazione
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: 7c7196df56821c134b31982d7956a75039e9f929
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705574"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="3a258-102">Come eseguire l'override del metodo ToString (C# guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="3a258-102">How to override the ToString method (C# Programming Guide)</span></span>

<span data-ttu-id="3a258-103">Ogni classe o struct in C# eredita in modo implicito la classe <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="3a258-103">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="3a258-104">Ogni oggetto in C# ottiene quindi il metodo <xref:System.Object.ToString%2A>, che restituisce una rappresentazione di stringa dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="3a258-104">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="3a258-105">Ad esempio, tutte le variabili di tipo `int` hanno un metodo `ToString` che consente loro di restituire il rispettivo contenuto sotto forma di stringa:</span><span class="sxs-lookup"><span data-stu-id="3a258-105">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#37)]  
  
 <span data-ttu-id="3a258-106">Quando si crea una classe o uno struct personalizzato, eseguire l'override del metodo <xref:System.Object.ToString%2A> per fornire informazioni sul tipo al codice client.</span><span class="sxs-lookup"><span data-stu-id="3a258-106">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="3a258-107">Per informazioni sull'uso di stringhe di formato e altri tipi di formattazione personalizzata con il metodo `ToString`, vedere [Formattazione di tipi](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="3a258-107">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3a258-108">Dopo aver deciso quali informazioni comunicare tramite questo metodo, considerare se la classe o lo struct sarà usato da codice non attendibile.</span><span class="sxs-lookup"><span data-stu-id="3a258-108">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="3a258-109">Verificare attentamente di non indicare informazioni che potrebbero essere sfruttate da malware.</span><span class="sxs-lookup"><span data-stu-id="3a258-109">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
<span data-ttu-id="3a258-110">Per eseguire l'override del metodo `ToString` nella classe o nello struct:</span><span class="sxs-lookup"><span data-stu-id="3a258-110">To override the `ToString` method in your class or struct:</span></span>
  
1. <span data-ttu-id="3a258-111">Dichiarare un metodo `ToString` con i modificatori e il tipo restituito seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a258-111">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2. <span data-ttu-id="3a258-112">Implementare il metodo in modo che restituisca una stringa.</span><span class="sxs-lookup"><span data-stu-id="3a258-112">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="3a258-113">L'esempio seguente restituisce il nome della classe oltre ai dati specifici per una particolare istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="3a258-113">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     [!code-csharp[csProgGuideInheritance#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#36)]  
  
     <span data-ttu-id="3a258-114">È anche possibile testare il metodo `ToString` come illustrato nel codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="3a258-114">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="3a258-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a258-115">See also</span></span>

- <xref:System.IFormattable>
- [<span data-ttu-id="3a258-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3a258-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3a258-117">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="3a258-117">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="3a258-118">Stringhe</span><span class="sxs-lookup"><span data-stu-id="3a258-118">Strings</span></span>](../strings/index.md)
- [<span data-ttu-id="3a258-119">string</span><span class="sxs-lookup"><span data-stu-id="3a258-119">string</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="3a258-120">override</span><span class="sxs-lookup"><span data-stu-id="3a258-120">override</span></span>](../../language-reference/keywords/override.md)
- [<span data-ttu-id="3a258-121">virtual</span><span class="sxs-lookup"><span data-stu-id="3a258-121">virtual</span></span>](../../language-reference/keywords/virtual.md)
- [<span data-ttu-id="3a258-122">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="3a258-122">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
