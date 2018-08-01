---
title: volatile (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: 64bd5ce7d7dfe3265c3c645467493ab7d8792172
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936878"
---
# <a name="volatile-c-reference"></a><span data-ttu-id="2ffd9-102">volatile (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2ffd9-102">volatile (C# Reference)</span></span>
<span data-ttu-id="2ffd9-103">La parola chiave `volatile` indica che un campo potrebbe essere modificato da più thread eseguiti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="2ffd9-104">Un campo dichiarato `volatile` non è soggetto a ottimizzazioni del compilatore che presuppongono l'accesso da parte di un singolo thread.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-104">Fields that are declared `volatile` are not subject to compiler optimizations that assume access by a single thread.</span></span> <span data-ttu-id="2ffd9-105">Queste limitazioni garantiscono che tutti i thread considereranno scritture di tipo volatile eseguite da altri thread nell'ordine in cui sono stati eseguiti.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-105">These restrictions ensure that all threads will observe volatile writes performed by any other thread in the order in which they were performed.</span></span> <span data-ttu-id="2ffd9-106">Non c'è garanzia di un singolo ordinamento totale delle scritture volatili come osservato da tutti i thread di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-106">There is no guarantee of a single total ordering of volatile writes as seen from all threads of execution.</span></span>  
  
 <span data-ttu-id="2ffd9-107">Il modificatore `volatile` si usa in genere per un campo a cui accedono più thread senza usare l'istruzione [lock](../../../csharp/language-reference/keywords/lock-statement.md) per serializzare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-107">The `volatile` modifier is usually used for a field that is accessed by multiple threads without using the [lock](../../../csharp/language-reference/keywords/lock-statement.md) statement to serialize access.</span></span>  
  
 <span data-ttu-id="2ffd9-108">La parola chiave `volatile` può essere applicata ai campi di questi tipi:</span><span class="sxs-lookup"><span data-stu-id="2ffd9-108">The `volatile` keyword can be applied to fields of these types:</span></span>  
  
-   <span data-ttu-id="2ffd9-109">Tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-109">Reference types.</span></span>  
  
-   <span data-ttu-id="2ffd9-110">Tipi di puntatore (in un contesto non sicuro).</span><span class="sxs-lookup"><span data-stu-id="2ffd9-110">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="2ffd9-111">Si noti che sebbene il puntatore in sé possa essere volatile, non può esserlo l'oggetto a cui punta.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-111">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="2ffd9-112">In altre parole, non è possibile dichiarare un "puntatore a volatile".</span><span class="sxs-lookup"><span data-stu-id="2ffd9-112">In other words, you cannot declare a "pointer to volatile."</span></span>  
  
-   <span data-ttu-id="2ffd9-113">Tipi come sbyte, byte, short, ushort, int, uint, char, float e bool.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-113">Types such as sbyte, byte, short, ushort, int, uint, char, float, and bool.</span></span>  
  
-   <span data-ttu-id="2ffd9-114">Un tipo enum con uno dei seguenti tipi di base: byte, sbyte, short, ushort, int o uint.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-114">An enum type with one of the following base types: byte, sbyte, short, ushort, int, or uint.</span></span>  
  
-   <span data-ttu-id="2ffd9-115">Parametri di tipo generico noti come tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-115">Generic type parameters known to be reference types.</span></span>  
  
-   <span data-ttu-id="2ffd9-116"><xref:System.IntPtr> e <xref:System.UIntPtr>.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-116"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>  
  
 <span data-ttu-id="2ffd9-117">La parola chiave volatile può essere applicata solo a campi di una classe o struct.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-117">The volatile keyword can only be applied to fields of a class or struct.</span></span> <span data-ttu-id="2ffd9-118">Le variabili locali non possono essere dichiarate `volatile`.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-118">Local variables cannot be declared `volatile`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ffd9-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="2ffd9-119">Example</span></span>  
 <span data-ttu-id="2ffd9-120">Nell'esempio riportato di seguito viene illustrato come dichiarare `volatile` una variabile di campo pubblico.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-120">The following example shows how to declare a public field variable as `volatile`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="2ffd9-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="2ffd9-121">Example</span></span>  
 <span data-ttu-id="2ffd9-122">Nell'esempio seguente viene illustrato come un thread di lavoro o ausiliario può essere creato e usato per eseguire l'elaborazione in parallelo con quella del thread principale.</span><span class="sxs-lookup"><span data-stu-id="2ffd9-122">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="2ffd9-123">Per informazioni di base sul multithreading, vedere [Managed Threading](../../../standard/threading/index.md) (Threading gestito) e [Threading (C#)](../../programming-guide/concepts/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="2ffd9-123">For background information about multithreading, see [Managed Threading](../../../standard/threading/index.md) and [Threading (C#)](../../programming-guide/concepts/threading/index.md).</span></span>  
  
 [!code-csharp[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="2ffd9-124">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="2ffd9-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2ffd9-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ffd9-125">See Also</span></span>  
 [<span data-ttu-id="2ffd9-126">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="2ffd9-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2ffd9-127">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="2ffd9-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2ffd9-128">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="2ffd9-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="2ffd9-129">Modificatori</span><span class="sxs-lookup"><span data-stu-id="2ffd9-129">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
