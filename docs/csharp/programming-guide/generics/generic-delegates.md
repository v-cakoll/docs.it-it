---
title: Delegati generici (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
caps.latest.revision: 16
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
ms.openlocfilehash: be067e2a2e2a192da8ccc92b60af81f0999c449a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="generic-delegates-c-programming-guide"></a><span data-ttu-id="e8c5e-102">Delegati generici (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e8c5e-102">Generic Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="e8c5e-103">Un [delegato](../../../csharp/language-reference/keywords/delegate.md) può definire i propri parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="e8c5e-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) can define its own type parameters.</span></span> <span data-ttu-id="e8c5e-104">Il codice che fa riferimento al delegato generico può specificare l'argomento tipo per creare un tipo costruito chiuso, proprio come per la creazione di un'istanza di una classe generica o la chiamata di un metodo generico, come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e8c5e-104">Code that references the generic delegate can specify the type argument to create a closed constructed type, just like when instantiating a generic class or calling a generic method, as shown in the following example:</span></span>  
  
 <span data-ttu-id="e8c5e-105">[!code-cs[csProgGuideGenerics#36](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e8c5e-105">[!code-cs[csProgGuideGenerics#36](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_1.cs)]</span></span>  
  
 <span data-ttu-id="e8c5e-106">C# versione 2.0 include una nuova funzionalità chiamata conversione di gruppi di metodi, applicabile a tipi delegato sia concreti sia generici, e che permette di scrivere la riga precedente con questa sintassi semplificata:</span><span class="sxs-lookup"><span data-stu-id="e8c5e-106">C# version 2.0 has a new feature called method group conversion, which applies to concrete as well as generic delegate types, and enables you to write the previous line with this simplified syntax:</span></span>  
  
 <span data-ttu-id="e8c5e-107">[!code-cs[csProgGuideGenerics#37](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e8c5e-107">[!code-cs[csProgGuideGenerics#37](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_2.cs)]</span></span>  
  
 <span data-ttu-id="e8c5e-108">I delegati definiti in una classe generica possono usare parametri di tipo di classe generica allo stesso modo dei metodi della classe.</span><span class="sxs-lookup"><span data-stu-id="e8c5e-108">Delegates defined within a generic class can use the generic class type parameters in the same way that class methods do.</span></span>  
  
 <span data-ttu-id="e8c5e-109">[!code-cs[csProgGuideGenerics#38](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="e8c5e-109">[!code-cs[csProgGuideGenerics#38](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_3.cs)]</span></span>  
  
 <span data-ttu-id="e8c5e-110">Il codice che fa riferimento al delegato deve specificare l'argomento tipo della classe che lo contiene, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="e8c5e-110">Code that references the delegate must specify the type argument of the containing class, as follows:</span></span>  
  
 <span data-ttu-id="e8c5e-111">[!code-cs[csProgGuideGenerics#39](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="e8c5e-111">[!code-cs[csProgGuideGenerics#39](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_4.cs)]</span></span>  
  
 <span data-ttu-id="e8c5e-112">I delegati generici sono particolarmente utili per definire eventi basati sul normale schema progettuale, perché l'argomento sender può essere fortemente tipizzato e non è più necessario eseguirne il cast a e da <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="e8c5e-112">Generic delegates are especially useful in defining events based on the typical design pattern because the sender argument can be strongly typed and no longer has to be cast to and from <xref:System.Object>.</span></span>  
  
 <span data-ttu-id="e8c5e-113">[!code-cs[csProgGuideGenerics#40](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="e8c5e-113">[!code-cs[csProgGuideGenerics#40](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8c5e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8c5e-114">See Also</span></span>  
 <span data-ttu-id="e8c5e-115"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="e8c5e-115"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="e8c5e-116">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e8c5e-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e8c5e-117">[Introduzione ai generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="e8c5e-117">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 <span data-ttu-id="e8c5e-118">[Metodi generici](../../../csharp/programming-guide/generics/generic-methods.md) </span><span class="sxs-lookup"><span data-stu-id="e8c5e-118">[Generic Methods](../../../csharp/programming-guide/generics/generic-methods.md) </span></span>  
 <span data-ttu-id="e8c5e-119">[Classi generiche](../../../csharp/programming-guide/generics/generic-classes.md) </span><span class="sxs-lookup"><span data-stu-id="e8c5e-119">[Generic Classes](../../../csharp/programming-guide/generics/generic-classes.md) </span></span>  
 <span data-ttu-id="e8c5e-120">[Interfacce generiche](../../../csharp/programming-guide/generics/generic-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="e8c5e-120">[Generic Interfaces](../../../csharp/programming-guide/generics/generic-interfaces.md) </span></span>  
 <span data-ttu-id="e8c5e-121">[Delegati](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="e8c5e-121">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 [<span data-ttu-id="e8c5e-122">Generics</span><span class="sxs-lookup"><span data-stu-id="e8c5e-122">Generics</span></span>](~/docs/standard/generics/index.md)

