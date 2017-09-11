---
title: Generics e matrici (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
caps.latest.revision: 17
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
ms.openlocfilehash: 46cea2733504e56aec5e65a4c9a8b655bc9431cf
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="f8439-102">Generics e matrici (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="f8439-102">Generics and Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="f8439-103">In C# 2.0 e versioni successive le matrici unidimensionali con limite inferiore pari a zero implementano automaticamente <xref:System.Collections.Generic.IList%601>.</span><span class="sxs-lookup"><span data-stu-id="f8439-103">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="f8439-104">Questo permette di creare metodi generici che possono usare lo stesso codice per eseguire l'iterazione di matrici e altri tipi di raccolta.</span><span class="sxs-lookup"><span data-stu-id="f8439-104">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="f8439-105">Questa tecnica è particolarmente utile per leggere dati nelle raccolte.</span><span class="sxs-lookup"><span data-stu-id="f8439-105">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="f8439-106">Non è possibile usare l'interfaccia <xref:System.Collections.Generic.IList%601> per aggiungere o rimuovere elementi in una matrice.</span><span class="sxs-lookup"><span data-stu-id="f8439-106">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="f8439-107">Se si prova a chiamare un metodo <xref:System.Collections.Generic.IList%601> come <xref:System.Collections.Generic.IList%601.RemoveAt%2A> in una matrice in questo contesto, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="f8439-107">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="f8439-108">L'esempio di codice seguente mostra in che modo un solo metodo generico che accetta un parametro di input <xref:System.Collections.Generic.IList%601> può eseguire l'iterazione sia di un elenco sia di una matrice, in questo caso una matrice di interi.</span><span class="sxs-lookup"><span data-stu-id="f8439-108">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 <span data-ttu-id="f8439-109">[!code-cs[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f8439-109">[!code-cs[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8439-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8439-110">See Also</span></span>  
 <span data-ttu-id="f8439-111"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="f8439-111"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="f8439-112">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f8439-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f8439-113">[Generics](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="f8439-113">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 <span data-ttu-id="f8439-114">[Matrici](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="f8439-114">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 [<span data-ttu-id="f8439-115">Generics</span><span class="sxs-lookup"><span data-stu-id="f8439-115">Generics</span></span>](~/docs/standard/generics/index.md)

