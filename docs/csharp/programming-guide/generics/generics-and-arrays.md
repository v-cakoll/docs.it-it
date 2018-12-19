---
title: Generics e matrici - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
ms.openlocfilehash: 50d649c4662114e76fdc0a6161ab0cbbeb04756d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237454"
---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="70969-102">Generics e matrici (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="70969-102">Generics and Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="70969-103">In C# 2.0 e versioni successive le matrici unidimensionali con limite inferiore pari a zero implementano automaticamente <xref:System.Collections.Generic.IList%601>.</span><span class="sxs-lookup"><span data-stu-id="70969-103">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="70969-104">Questo permette di creare metodi generici che possono usare lo stesso codice per eseguire l'iterazione di matrici e altri tipi di raccolta.</span><span class="sxs-lookup"><span data-stu-id="70969-104">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="70969-105">Questa tecnica è particolarmente utile per leggere dati nelle raccolte.</span><span class="sxs-lookup"><span data-stu-id="70969-105">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="70969-106">Non è possibile usare l'interfaccia <xref:System.Collections.Generic.IList%601> per aggiungere o rimuovere elementi in una matrice.</span><span class="sxs-lookup"><span data-stu-id="70969-106">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="70969-107">Se si prova a chiamare un metodo <xref:System.Collections.Generic.IList%601> come <xref:System.Collections.Generic.IList%601.RemoveAt%2A> in una matrice in questo contesto, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="70969-107">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="70969-108">L'esempio di codice seguente mostra in che modo un solo metodo generico che accetta un parametro di input <xref:System.Collections.Generic.IList%601> può eseguire l'iterazione sia di un elenco sia di una matrice, in questo caso una matrice di interi.</span><span class="sxs-lookup"><span data-stu-id="70969-108">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="70969-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70969-109">See Also</span></span>

- <xref:System.Collections.Generic>  
- [<span data-ttu-id="70969-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="70969-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="70969-111">Generics</span><span class="sxs-lookup"><span data-stu-id="70969-111">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)  
- [<span data-ttu-id="70969-112">Matrici</span><span class="sxs-lookup"><span data-stu-id="70969-112">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
- [<span data-ttu-id="70969-113">Generics</span><span class="sxs-lookup"><span data-stu-id="70969-113">Generics</span></span>](~/docs/standard/generics/index.md)
