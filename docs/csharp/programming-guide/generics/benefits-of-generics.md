---
title: Vantaggi dei generics (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], benefits
ms.assetid: 80f037cd-9ea7-48be-bfc1-219bfb2d4277
caps.latest.revision: 23
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
ms.openlocfilehash: 8b05a3a695064764618564293e6ccd92e2ce60be
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="benefits-of-generics-c-programming-guide"></a><span data-ttu-id="01be1-102">Vantaggi dei generics (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="01be1-102">Benefits of Generics (C# Programming Guide)</span></span>
<span data-ttu-id="01be1-103">I generics rappresentano la soluzione a una limitazione in versioni precedenti di Common Language Runtime e del linguaggio C# nelle quali la generalizzazione viene effettuata tramite il casting dei tipi nel e dal tipo di base universale <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="01be1-103">Generics provide the solution to a limitation in earlier versions of the common language runtime and the C# language in which generalization is accomplished by casting types to and from the universal base type <xref:System.Object>.</span></span> <span data-ttu-id="01be1-104">Creando una classe generica, è possibile creare una raccolta indipendente dai tipi in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="01be1-104">By creating a generic class, you can create a collection that is type-safe at compile-time.</span></span>  
  
 <span data-ttu-id="01be1-105">Per una dimostrazione delle limitazioni dell'uso di classi di raccolta non generiche, è possibile scrivere un breve programma che usa la classe di raccolta <xref:System.Collections.ArrayList> dalla libreria di classi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="01be1-105">The limitations of using non-generic collection classes can be demonstrated by writing a short program that uses the <xref:System.Collections.ArrayList> collection class from the .NET Framework class library.</span></span> <span data-ttu-id="01be1-106"><xref:System.Collections.ArrayList> è una classe di raccolta estremamente utile che può essere usata senza alcuna modifica per archiviare qualsiasi tipo riferimento o valore.</span><span class="sxs-lookup"><span data-stu-id="01be1-106"><xref:System.Collections.ArrayList> is a highly convenient collection class that can be used without modification to store any reference or value type.</span></span>  
  
 <span data-ttu-id="01be1-107">[!code-cs[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="01be1-107">[!code-cs[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]</span></span>  
  
 <span data-ttu-id="01be1-108">La comodità ha tuttavia un costo.</span><span class="sxs-lookup"><span data-stu-id="01be1-108">But this convenience comes at a cost.</span></span> <span data-ttu-id="01be1-109">Per qualsiasi tipo riferimento o valore aggiunto a <xref:System.Collections.ArrayList> viene effettuato l'upcast implicito a <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="01be1-109">Any reference or value type that is added to an <xref:System.Collections.ArrayList> is implicitly upcast to <xref:System.Object>.</span></span> <span data-ttu-id="01be1-110">Se gli elementi sono tipi valore, devono essere sottoposti a conversione boxing quando vengono aggiunti all'elenco e a conversione unboxing quando vengono recuperati.</span><span class="sxs-lookup"><span data-stu-id="01be1-110">If the items are value types, they must be boxed when they are added to the list, and unboxed when they are retrieved.</span></span> <span data-ttu-id="01be1-111">Sia il casting che le operazioni di conversione boxing e unboxing riducono le prestazioni. L'effetto delle conversioni boxing e unboxing può essere molto significativo in scenari in cui è necessario scorrere raccolte di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="01be1-111">Both the casting and the boxing and unboxing operations decrease performance; the effect of boxing and unboxing can be very significant in scenarios where you must iterate over large collections.</span></span>  
  
 <span data-ttu-id="01be1-112">L'altra limitazione è la mancanza di un controllo dei tipi in fase di compilazione. Dato che <xref:System.Collections.ArrayList> effettua il cast di tutti gli elementi in <xref:System.Object>, non esiste alcun modo in fase di compilazione per evitare che il codice client esegua operazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="01be1-112">The other limitation is lack of compile-time type checking; because an <xref:System.Collections.ArrayList> casts everything to <xref:System.Object>, there is no way at compile-time to prevent client code from doing something such as this:</span></span>  
  
 <span data-ttu-id="01be1-113">[!code-cs[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="01be1-113">[!code-cs[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]</span></span>  
  
 <span data-ttu-id="01be1-114">Anche se perfettamente accettabile e talvolta intenzionale se si sta creando un raccolta eterogenea, la combinazione di stringhe e `ints` in un singolo <xref:System.Collections.ArrayList> è più probabile che sia un errore di programmazione e questo errore non viene rilevato fino alla fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="01be1-114">Although perfectly acceptable and sometimes intentional if you are creating a heterogeneous collection, combining strings and `ints` in a single <xref:System.Collections.ArrayList> is more likely to be a programming error, and this error will not be detected until runtime.</span></span>  
  
 <span data-ttu-id="01be1-115">Nelle versioni 1.0 e 1.1 del linguaggio C#, è possibile evitare i pericoli del codice generalizzato nelle classi di raccolta della libreria di classi base di .NET Framework solo scrivendo raccolte personalizzate per tipi specifici.</span><span class="sxs-lookup"><span data-stu-id="01be1-115">In versions 1.0 and 1.1 of the C# language, you could avoid the dangers of generalized code in the .NET Framework base class library collection classes only by writing your own type specific collections.</span></span> <span data-ttu-id="01be1-116">Naturalmente, dato che una classe di questo tipo non è riutilizzabile per più di un tipo di dati, si perdono i vantaggi della generalizzazione ed è necessario riscrivere la classe per ogni tipo che verrà archiviato.</span><span class="sxs-lookup"><span data-stu-id="01be1-116">Of course, because such a class is not reusable for more than one data type, you lose the benefits of generalization, and you have to rewrite the class for each type that will be stored.</span></span>  
  
 <span data-ttu-id="01be1-117">Quello che serve effettivamente per <xref:System.Collections.ArrayList> e altre classi simili è un modo per specificare nel codice client, per ogni singola istanza, il tipo di dati specifico che si intende usare.</span><span class="sxs-lookup"><span data-stu-id="01be1-117">What <xref:System.Collections.ArrayList> and other similar classes really need is a way for client code to specify, on a per-instance basis, the particular data type that they intend to use.</span></span> <span data-ttu-id="01be1-118">In questo modo risulta inutile l'upcast a `T:System.Object` e il compilatore è inoltre in grado di eseguire il controllo dei tipi.</span><span class="sxs-lookup"><span data-stu-id="01be1-118">That would eliminate the need for the upcast to `T:System.Object` and would also make it possible for the compiler to do type checking.</span></span> <span data-ttu-id="01be1-119">In altre parole, <xref:System.Collections.ArrayList> richiede un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="01be1-119">In other words, <xref:System.Collections.ArrayList> needs a type parameter.</span></span> <span data-ttu-id="01be1-120">Questo è esattamente ciò che offre la funzionalità generics.</span><span class="sxs-lookup"><span data-stu-id="01be1-120">That is exactly what generics provide.</span></span> <span data-ttu-id="01be1-121">Nella raccolta generica <xref:System.Collections.Generic.List%601>, nello spazio dei nomi `N:System.Collections.Generic` la stessa operazione di aggiunta di elementi alla raccolta è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="01be1-121">In the generic <xref:System.Collections.Generic.List%601> collection, in the `N:System.Collections.Generic` namespace, the same operation of adding items to the collection resembles this:</span></span>  
  
 <span data-ttu-id="01be1-122">[!code-cs[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="01be1-122">[!code-cs[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]</span></span>  
  
 <span data-ttu-id="01be1-123">Per il codice client, l'unica sintassi aggiunta con <xref:System.Collections.Generic.List%601> rispetto a <xref:System.Collections.ArrayList> è l'argomento di tipo nella dichiarazione e nella creazione dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="01be1-123">For client code, the only added syntax with <xref:System.Collections.Generic.List%601> compared to <xref:System.Collections.ArrayList> is the type argument in the declaration and instantiation.</span></span> <span data-ttu-id="01be1-124">Al costo di codice leggermente più complesso, è possibile creare un elenco che non è solo più sicuro di <xref:System.Collections.ArrayList>, ma anche molto più rapido, specialmente quando gli elementi dell'elenco sono tipi valore.</span><span class="sxs-lookup"><span data-stu-id="01be1-124">In return for this slightly more coding complexity, you can create a list that is not only safer than <xref:System.Collections.ArrayList>, but also significantly faster, especially when the list items are value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01be1-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01be1-125">See Also</span></span>  
 <span data-ttu-id="01be1-126"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="01be1-126"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="01be1-127">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="01be1-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="01be1-128">[Introduzione ai generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="01be1-128">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 <span data-ttu-id="01be1-129">[Boxing e unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md) </span><span class="sxs-lookup"><span data-stu-id="01be1-129">[Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md) </span></span>  
 [<span data-ttu-id="01be1-130">Procedure consigliate per le raccolte</span><span class="sxs-lookup"><span data-stu-id="01be1-130">Collections Best Practices</span></span>](http://go.microsoft.com/fwlink/?LinkId=112403)

