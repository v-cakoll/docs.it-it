---
title: get (Riferimenti per C#)
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- get_CSharpKeyword
- get
dev_langs:
- CSharp
helpviewer_keywords:
- get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
caps.latest.revision: 11
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
ms.openlocfilehash: 88603864ae0a31a193cab211b8ce8061ec63c169
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="get-c-reference"></a><span data-ttu-id="03941-102">get (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="03941-102">get (C# Reference)</span></span>

<span data-ttu-id="03941-103">La parola chiave `get` definisce un metodo *funzione di accesso* in una proprietà o indicizzatore che restituisce il valore della proprietà o l'elemento dell'indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="03941-103">The `get` keyword defines an *accessor* method in a property or indexer that returns the property value or the indexer element.</span></span> <span data-ttu-id="03941-104">Per altre informazioni, vedere [Proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md), [Proprietà implementate automaticamente](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) e [Indicizzatori](../../../csharp/programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="03941-104">For more information, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) and [Indexers](../../../csharp/programming-guide/indexers/index.md).</span></span>  
  
<span data-ttu-id="03941-105">L'esempio seguente definisce le funzioni di accesso `get` e `set` per una proprietà denominata `Seconds`.</span><span class="sxs-lookup"><span data-stu-id="03941-105">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="03941-106">Usa il campo privato denominato `_seconds` per portare in secondo piano il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="03941-106">It uses a private field named `_seconds` to back the property value.</span></span>  
 
 <span data-ttu-id="03941-107">[!code-cs[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="03941-107">[!code-cs[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]</span></span>  
  
<span data-ttu-id="03941-108">Spesso la funzione di accesso `get` è costituita da una singola istruzione che restituisce un valore, come nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="03941-108">Often, the `get` accessor consists of a single statement that returns a value, as it did in the previous example.</span></span> <span data-ttu-id="03941-109">A partire da C# 7, è possibile implementare la funzione di accesso `get` come membro con corpo di espressione.</span><span class="sxs-lookup"><span data-stu-id="03941-109">Starting with C# 7, you can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="03941-110">L'esempio seguente implementa entrambe le funzioni di accesso `get` e `set` come membri con corpo di espressione.</span><span class="sxs-lookup"><span data-stu-id="03941-110">The following example implements both the `get` and the `set` accessor as expression-bodied members.</span></span>

 <span data-ttu-id="03941-111">[!code-cs[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="03941-111">[!code-cs[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]</span></span>   
 
<span data-ttu-id="03941-112">Per i casi semplici in cui le funzioni di accesso `get` e `set` di una proprietà non eseguono operazioni diverse dall'impostazione o recupero di un valore in un campo sottostante, è possibile sfruttare il supporto del compilatore C# per le proprietà implementate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="03941-112">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="03941-113">L'esempio seguente implementa `Hours` come una proprietà implementata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="03941-113">The following example implements `Hours` as an auto-implemented property.</span></span> 
  
 <span data-ttu-id="03941-114">[!code-cs[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="03941-114">[!code-cs[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="03941-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="03941-115">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="03941-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03941-116">See Also</span></span>  
 <span data-ttu-id="03941-117">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="03941-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="03941-118">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="03941-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="03941-119">[Parole chiave C#](../../../csharp/language-reference/keywords/index.md) [Proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md)</span><span class="sxs-lookup"><span data-stu-id="03941-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md)</span></span>

