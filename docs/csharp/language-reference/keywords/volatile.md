---
title: volatile (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- volatile_CSharpKeyword
- volatile
dev_langs:
- CSharp
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
caps.latest.revision: 29
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
ms.openlocfilehash: c8f9fba15991197be885a973435089098a57db87
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="volatile-c-reference"></a><span data-ttu-id="e9a8c-102">volatile (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e9a8c-102">volatile (C# Reference)</span></span>
<span data-ttu-id="e9a8c-103">La parola chiave `volatile` indica che un campo potrebbe essere modificato da più thread eseguiti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="e9a8c-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="e9a8c-104">Un campo dichiarato `volatile` non è soggetto a ottimizzazioni del compilatore che presuppongono l'accesso da parte di un singolo thread.</span><span class="sxs-lookup"><span data-stu-id="e9a8c-104">Fields that are declared `volatile` are not subject to compiler optimizations that assume access by a single thread.</span></span> <span data-ttu-id="e9a8c-105">Ciò garantisce che il valore più aggiornato sia sempre presente nel campo.</span><span class="sxs-lookup"><span data-stu-id="e9a8c-105">This ensures that the most up-to-date value is present in the field at all times.</span></span>  
  
 <span data-ttu-id="e9a8c-106">Il modificatore `volatile` si usa in genere per un campo a cui accedono più thread senza usare l'istruzione [lock](../../../csharp/language-reference/keywords/lock-statement.md) per serializzare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e9a8c-106">The `volatile` modifier is usually used for a field that is accessed by multiple threads without using the [lock](../../../csharp/language-reference/keywords/lock-statement.md) statement to serialize access.</span></span>  
  
 <span data-ttu-id="e9a8c-107">La parola chiave `volatile` può essere applicata ai campi di questi tipi:</span><span class="sxs-lookup"><span data-stu-id="e9a8c-107">The `volatile` keyword can be applied to fields of these types:</span></span>  
  
-   <span data-ttu-id="e9a8c-108">Tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="e9a8c-108">Reference types.</span></span>  
  
-   <span data-ttu-id="e9a8c-109">Tipi di puntatore (in un contesto non sicuro).</span><span class="sxs-lookup"><span data-stu-id="e9a8c-109">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="e9a8c-110">Si noti che sebbene il puntatore in sé possa essere volatile, non può esserlo l'oggetto a cui punta.</span><span class="sxs-lookup"><span data-stu-id="e9a8c-110">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="e9a8c-111">In altre parole, non è possibile dichiarare un "puntatore a volatile".</span><span class="sxs-lookup"><span data-stu-id="e9a8c-111">In other words, you cannot declare a "pointer to volatile."</span></span>  
  
-   <span data-ttu-id="e9a8c-112">Tipi come sbyte, byte, short, ushort, int, uint, char, float e bool.</span><span class="sxs-lookup"><span data-stu-id="e9a8c-112">Types such as sbyte, byte, short, ushort, int, uint, char, float, and bool.</span></span>  
  
-   <span data-ttu-id="e9a8c-113">Un tipo enum con uno dei seguenti tipi di base: byte, sbyte, short, ushort, int o uint.</span><span class="sxs-lookup"><span data-stu-id="e9a8c-113">An enum type with one of the following base types: byte, sbyte, short, ushort, int, or uint.</span></span>  
  
-   <span data-ttu-id="e9a8c-114">Parametri di tipo generico noti come tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="e9a8c-114">Generic type parameters known to be reference types.</span></span>  
  
-   <span data-ttu-id="e9a8c-115"><xref:System.IntPtr> e <xref:System.UIntPtr>.</span><span class="sxs-lookup"><span data-stu-id="e9a8c-115"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>  
  
 <span data-ttu-id="e9a8c-116">La parola chiave volatile può essere applicata solo a campi di una classe o struct.</span><span class="sxs-lookup"><span data-stu-id="e9a8c-116">The volatile keyword can only be applied to fields of a class or struct.</span></span> <span data-ttu-id="e9a8c-117">Le variabili locali non possono essere dichiarate `volatile`.</span><span class="sxs-lookup"><span data-stu-id="e9a8c-117">Local variables cannot be declared `volatile`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9a8c-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="e9a8c-118">Example</span></span>  
 <span data-ttu-id="e9a8c-119">Nell'esempio riportato di seguito viene illustrato come dichiarare `volatile` una variabile di campo pubblico.</span><span class="sxs-lookup"><span data-stu-id="e9a8c-119">The following example shows how to declare a public field variable as `volatile`.</span></span>  
  
 <span data-ttu-id="e9a8c-120">[!code-cs[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e9a8c-120">[!code-cs[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9a8c-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="e9a8c-121">Example</span></span>  
 <span data-ttu-id="e9a8c-122">Nell'esempio seguente viene illustrato come un thread di lavoro o ausiliario può essere creato e usato per eseguire l'elaborazione in parallelo con quella del thread principale.</span><span class="sxs-lookup"><span data-stu-id="e9a8c-122">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="e9a8c-123">Per informazioni di base sul multithreading, vedere [Threading](../../../standard/threading/index.md) and [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span><span class="sxs-lookup"><span data-stu-id="e9a8c-123">For background information about multithreading, see [Threading](../../../standard/threading/index.md) and [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span></span>  
  
 <span data-ttu-id="e9a8c-124">[!code-cs[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e9a8c-124">[!code-cs[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e9a8c-125">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e9a8c-125">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e9a8c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9a8c-126">See Also</span></span>  
 <span data-ttu-id="e9a8c-127">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e9a8c-127">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e9a8c-128">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e9a8c-128">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e9a8c-129">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="e9a8c-129">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="e9a8c-130">Modificatori</span><span class="sxs-lookup"><span data-stu-id="e9a8c-130">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

