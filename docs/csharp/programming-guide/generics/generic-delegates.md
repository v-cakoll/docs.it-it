---
title: Delegati generici - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: 4e57256328fc81a485670b47fcf8fd1c38e26fac
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712221"
---
# <a name="generic-delegates-c-programming-guide"></a><span data-ttu-id="77c7a-102">Delegati generici (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="77c7a-102">Generic Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="77c7a-103">Un [delegato](../../language-reference/builtin-types/reference-types.md) può definire i propri parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="77c7a-103">A [delegate](../../language-reference/builtin-types/reference-types.md) can define its own type parameters.</span></span> <span data-ttu-id="77c7a-104">Il codice che fa riferimento al delegato generico può specificare l'argomento tipo per creare un tipo costruito chiuso, proprio come per la creazione di un'istanza di una classe generica o la chiamata di un metodo generico, come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="77c7a-104">Code that references the generic delegate can specify the type argument to create a closed constructed type, just like when instantiating a generic class or calling a generic method, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#36)]  
  
 <span data-ttu-id="77c7a-105">C# versione 2.0 include una nuova funzionalità chiamata conversione di gruppi di metodi, applicabile a tipi delegato sia concreti sia generici, e che permette di scrivere la riga precedente con questa sintassi semplificata:</span><span class="sxs-lookup"><span data-stu-id="77c7a-105">C# version 2.0 has a new feature called method group conversion, which applies to concrete as well as generic delegate types, and enables you to write the previous line with this simplified syntax:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#37)]  
  
 <span data-ttu-id="77c7a-106">I delegati definiti in una classe generica possono usare parametri di tipo di classe generica allo stesso modo dei metodi della classe.</span><span class="sxs-lookup"><span data-stu-id="77c7a-106">Delegates defined within a generic class can use the generic class type parameters in the same way that class methods do.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#38)]  
  
 <span data-ttu-id="77c7a-107">Il codice che fa riferimento al delegato deve specificare l'argomento tipo della classe che lo contiene, in questo modo:</span><span class="sxs-lookup"><span data-stu-id="77c7a-107">Code that references the delegate must specify the type argument of the containing class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#39)]  
  
 <span data-ttu-id="77c7a-108">I delegati generici sono particolarmente utili per definire eventi basati sul normale schema progettuale, perché l'argomento sender può essere fortemente tipizzato e non è più necessario eseguirne il cast a e da <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="77c7a-108">Generic delegates are especially useful in defining events based on the typical design pattern because the sender argument can be strongly typed and no longer has to be cast to and from <xref:System.Object>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#40)]  
  
## <a name="see-also"></a><span data-ttu-id="77c7a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77c7a-109">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="77c7a-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="77c7a-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="77c7a-111">Introduzione ai generics</span><span class="sxs-lookup"><span data-stu-id="77c7a-111">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="77c7a-112">Metodi generici</span><span class="sxs-lookup"><span data-stu-id="77c7a-112">Generic Methods</span></span>](./generic-methods.md)
- [<span data-ttu-id="77c7a-113">Classi generiche</span><span class="sxs-lookup"><span data-stu-id="77c7a-113">Generic Classes</span></span>](./generic-classes.md)
- [<span data-ttu-id="77c7a-114">Interfacce generiche</span><span class="sxs-lookup"><span data-stu-id="77c7a-114">Generic Interfaces</span></span>](./generic-interfaces.md)
- [<span data-ttu-id="77c7a-115">Delegati</span><span class="sxs-lookup"><span data-stu-id="77c7a-115">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="77c7a-116">Generics</span><span class="sxs-lookup"><span data-stu-id="77c7a-116">Generics</span></span>](../../../standard/generics/index.md)
