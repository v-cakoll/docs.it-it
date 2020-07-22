---
title: Come eseguire l'override del metodo ToString (Guida per programmatori C#)
description: Informazioni su come eseguire l'override del metodo ToString in C#. Ogni classe o struct eredita l'oggetto e ottiene il metodo ToString, che restituisce una rappresentazione di stringa di tale oggetto.
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: 65b34b485d4b90173a4c956dd0ebaaa590a0c7c9
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865008"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="e4d65-104">Come eseguire l'override del metodo ToString (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e4d65-104">How to override the ToString method (C# Programming Guide)</span></span>

<span data-ttu-id="e4d65-105">Ogni classe o struct in C# eredita in modo implicito la classe <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="e4d65-105">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="e4d65-106">Ogni oggetto in C# ottiene quindi il metodo <xref:System.Object.ToString%2A>, che restituisce una rappresentazione di stringa dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="e4d65-106">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="e4d65-107">Ad esempio, tutte le variabili di tipo `int` hanno un metodo `ToString` che consente loro di restituire il rispettivo contenuto sotto forma di stringa:</span><span class="sxs-lookup"><span data-stu-id="e4d65-107">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#37)]  
  
 <span data-ttu-id="e4d65-108">Quando si crea una classe o uno struct personalizzato, eseguire l'override del metodo <xref:System.Object.ToString%2A> per fornire informazioni sul tipo al codice client.</span><span class="sxs-lookup"><span data-stu-id="e4d65-108">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="e4d65-109">Per informazioni sull'uso di stringhe di formato e altri tipi di formattazione personalizzata con il metodo `ToString`, vedere [Formattazione di tipi](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="e4d65-109">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e4d65-110">Dopo aver deciso quali informazioni comunicare tramite questo metodo, considerare se la classe o lo struct sarà usato da codice non attendibile.</span><span class="sxs-lookup"><span data-stu-id="e4d65-110">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="e4d65-111">Verificare attentamente di non indicare informazioni che potrebbero essere sfruttate da malware.</span><span class="sxs-lookup"><span data-stu-id="e4d65-111">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
<span data-ttu-id="e4d65-112">Per eseguire l'override del metodo `ToString` nella classe o nello struct:</span><span class="sxs-lookup"><span data-stu-id="e4d65-112">To override the `ToString` method in your class or struct:</span></span>
  
1. <span data-ttu-id="e4d65-113">Dichiarare un metodo `ToString` con i modificatori e il tipo restituito seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4d65-113">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2. <span data-ttu-id="e4d65-114">Implementare il metodo in modo che restituisca una stringa.</span><span class="sxs-lookup"><span data-stu-id="e4d65-114">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="e4d65-115">L'esempio seguente restituisce il nome della classe oltre ai dati specifici per una particolare istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="e4d65-115">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     [!code-csharp[csProgGuideInheritance#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#36)]  
  
     <span data-ttu-id="e4d65-116">È anche possibile testare il metodo `ToString` come illustrato nel codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e4d65-116">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="e4d65-117">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="e4d65-117">See also</span></span>

- <xref:System.IFormattable>
- [<span data-ttu-id="e4d65-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e4d65-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e4d65-119">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="e4d65-119">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="e4d65-120">Stringhe</span><span class="sxs-lookup"><span data-stu-id="e4d65-120">Strings</span></span>](../strings/index.md)
- [<span data-ttu-id="e4d65-121">string</span><span class="sxs-lookup"><span data-stu-id="e4d65-121">string</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="e4d65-122">override</span><span class="sxs-lookup"><span data-stu-id="e4d65-122">override</span></span>](../../language-reference/keywords/override.md)
- [<span data-ttu-id="e4d65-123">virtuale</span><span class="sxs-lookup"><span data-stu-id="e4d65-123">virtual</span></span>](../../language-reference/keywords/virtual.md)
- [<span data-ttu-id="e4d65-124">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="e4d65-124">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
