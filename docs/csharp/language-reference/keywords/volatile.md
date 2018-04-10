---
title: volatile (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1cefa39313c3c551e8d05fbc31e528b86c6888d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="volatile-c-reference"></a><span data-ttu-id="e162e-102">volatile (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e162e-102">volatile (C# Reference)</span></span>
<span data-ttu-id="e162e-103">La parola chiave `volatile` indica che un campo potrebbe essere modificato da più thread eseguiti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="e162e-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="e162e-104">Un campo dichiarato `volatile` non è soggetto a ottimizzazioni del compilatore che presuppongono l'accesso da parte di un singolo thread.</span><span class="sxs-lookup"><span data-stu-id="e162e-104">Fields that are declared `volatile` are not subject to compiler optimizations that assume access by a single thread.</span></span> <span data-ttu-id="e162e-105">Ciò garantisce che il valore più aggiornato sia sempre presente nel campo.</span><span class="sxs-lookup"><span data-stu-id="e162e-105">This ensures that the most up-to-date value is present in the field at all times.</span></span>  
  
 <span data-ttu-id="e162e-106">Il modificatore `volatile` si usa in genere per un campo a cui accedono più thread senza usare l'istruzione [lock](../../../csharp/language-reference/keywords/lock-statement.md) per serializzare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e162e-106">The `volatile` modifier is usually used for a field that is accessed by multiple threads without using the [lock](../../../csharp/language-reference/keywords/lock-statement.md) statement to serialize access.</span></span>  
  
 <span data-ttu-id="e162e-107">La parola chiave `volatile` può essere applicata ai campi di questi tipi:</span><span class="sxs-lookup"><span data-stu-id="e162e-107">The `volatile` keyword can be applied to fields of these types:</span></span>  
  
-   <span data-ttu-id="e162e-108">Tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="e162e-108">Reference types.</span></span>  
  
-   <span data-ttu-id="e162e-109">Tipi di puntatore (in un contesto non sicuro).</span><span class="sxs-lookup"><span data-stu-id="e162e-109">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="e162e-110">Si noti che sebbene il puntatore in sé possa essere volatile, non può esserlo l'oggetto a cui punta.</span><span class="sxs-lookup"><span data-stu-id="e162e-110">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="e162e-111">In altre parole, non è possibile dichiarare un "puntatore a volatile".</span><span class="sxs-lookup"><span data-stu-id="e162e-111">In other words, you cannot declare a "pointer to volatile."</span></span>  
  
-   <span data-ttu-id="e162e-112">Tipi come sbyte, byte, short, ushort, int, uint, char, float e bool.</span><span class="sxs-lookup"><span data-stu-id="e162e-112">Types such as sbyte, byte, short, ushort, int, uint, char, float, and bool.</span></span>  
  
-   <span data-ttu-id="e162e-113">Un tipo enum con uno dei seguenti tipi di base: byte, sbyte, short, ushort, int o uint.</span><span class="sxs-lookup"><span data-stu-id="e162e-113">An enum type with one of the following base types: byte, sbyte, short, ushort, int, or uint.</span></span>  
  
-   <span data-ttu-id="e162e-114">Parametri di tipo generico noti come tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="e162e-114">Generic type parameters known to be reference types.</span></span>  
  
-   <span data-ttu-id="e162e-115"><xref:System.IntPtr> e <xref:System.UIntPtr>.</span><span class="sxs-lookup"><span data-stu-id="e162e-115"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>  
  
 <span data-ttu-id="e162e-116">La parola chiave volatile può essere applicata solo a campi di una classe o struct.</span><span class="sxs-lookup"><span data-stu-id="e162e-116">The volatile keyword can only be applied to fields of a class or struct.</span></span> <span data-ttu-id="e162e-117">Le variabili locali non possono essere dichiarate `volatile`.</span><span class="sxs-lookup"><span data-stu-id="e162e-117">Local variables cannot be declared `volatile`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e162e-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="e162e-118">Example</span></span>  
 <span data-ttu-id="e162e-119">Nell'esempio riportato di seguito viene illustrato come dichiarare `volatile` una variabile di campo pubblico.</span><span class="sxs-lookup"><span data-stu-id="e162e-119">The following example shows how to declare a public field variable as `volatile`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="e162e-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="e162e-120">Example</span></span>  
 <span data-ttu-id="e162e-121">Nell'esempio seguente viene illustrato come un thread di lavoro o ausiliario può essere creato e usato per eseguire l'elaborazione in parallelo con quella del thread principale.</span><span class="sxs-lookup"><span data-stu-id="e162e-121">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="e162e-122">Per informazioni di base sul multithreading, vedere [Threading](../../../standard/threading/index.md) and [Threading](../../programming-guide/concepts/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="e162e-122">For background information about multithreading, see [Threading](../../../standard/threading/index.md) and [Threading](../../programming-guide/concepts/threading/index.md).</span></span>  
  
 [!code-csharp[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="e162e-123">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e162e-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e162e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e162e-124">See Also</span></span>  
 [<span data-ttu-id="e162e-125">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e162e-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e162e-126">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e162e-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e162e-127">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="e162e-127">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="e162e-128">Modificatori</span><span class="sxs-lookup"><span data-stu-id="e162e-128">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
