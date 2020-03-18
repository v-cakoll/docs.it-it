---
title: volatile - Riferimenti per C#
ms.date: 10/24/2018
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: c7a6c442c33ac2b41f652805837f455a957819de
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712845"
---
# <a name="volatile-c-reference"></a><span data-ttu-id="5f77d-102">volatile (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="5f77d-102">volatile (C# Reference)</span></span>

<span data-ttu-id="5f77d-103">La parola chiave `volatile` indica che un campo potrebbe essere modificato da più thread eseguiti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="5f77d-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="5f77d-104">Il compilatore, il sistema di runtime e anche l'hardware possono riordinare le letture e le scritture in posizioni di memoria per motivi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="5f77d-104">The compiler, the runtime system, and even hardware may rearrange reads and writes to memory locations for performance reasons.</span></span> <span data-ttu-id="5f77d-105">I campi dichiarati `volatile` non sono soggetti a queste ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="5f77d-105">Fields that are declared `volatile` are not subject to these optimizations.</span></span> <span data-ttu-id="5f77d-106">L'aggiunta del modificatore `volatile` garantisce che tutti thread osserveranno le scritture volatili eseguite da qualsiasi altro thread nell'ordine in cui sono state eseguite.</span><span class="sxs-lookup"><span data-stu-id="5f77d-106">Adding the `volatile` modifier ensures that all threads will observe volatile writes performed by any other thread in the order in which they were performed.</span></span> <span data-ttu-id="5f77d-107">Non c'è garanzia di un singolo ordinamento totale delle scritture volatili come osservato da tutti i thread di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5f77d-107">There is no guarantee of a single total ordering of volatile writes as seen from all threads of execution.</span></span>

<span data-ttu-id="5f77d-108">La parola chiave `volatile` può essere applicata ai campi di questi tipi:</span><span class="sxs-lookup"><span data-stu-id="5f77d-108">The `volatile` keyword can be applied to fields of these types:</span></span>

- <span data-ttu-id="5f77d-109">Tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="5f77d-109">Reference types.</span></span>
- <span data-ttu-id="5f77d-110">Tipi di puntatore (in un contesto non sicuro).</span><span class="sxs-lookup"><span data-stu-id="5f77d-110">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="5f77d-111">Si noti che sebbene il puntatore in sé possa essere volatile, non può esserlo l'oggetto a cui punta.</span><span class="sxs-lookup"><span data-stu-id="5f77d-111">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="5f77d-112">In altre parole, non è possibile dichiarare un "puntatore a volatile".</span><span class="sxs-lookup"><span data-stu-id="5f77d-112">In other words, you cannot declare a "pointer to volatile."</span></span>
- <span data-ttu-id="5f77d-113">Tipi semplici come `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `char`, `float` e `bool`.</span><span class="sxs-lookup"><span data-stu-id="5f77d-113">Simple types such as `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `char`, `float`, and `bool`.</span></span>
- <span data-ttu-id="5f77d-114">Tipo `enum` con uno di questi tipi di base: `byte`, `sbyte`, `short`, `ushort`, `int` o `uint`.</span><span class="sxs-lookup"><span data-stu-id="5f77d-114">An `enum` type with one of the following base types: `byte`, `sbyte`, `short`, `ushort`, `int`, or `uint`.</span></span>
- <span data-ttu-id="5f77d-115">Parametri di tipo generico noti come tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="5f77d-115">Generic type parameters known to be reference types.</span></span>
- <span data-ttu-id="5f77d-116"><xref:System.IntPtr> e <xref:System.UIntPtr>.</span><span class="sxs-lookup"><span data-stu-id="5f77d-116"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>

<span data-ttu-id="5f77d-117">Altri tipi, inclusi `double` e `long`, non possono essere contrassegnati come `volatile`, perché non è possibile garantire che le letture e le scritture in campi di questi tipi siano atomiche.</span><span class="sxs-lookup"><span data-stu-id="5f77d-117">Other types, including `double` and `long`, cannot be marked `volatile` because reads and writes to fields of those types cannot be guaranteed to be atomic.</span></span> <span data-ttu-id="5f77d-118">Per proteggere l'accesso multithread a tali <xref:System.Threading.Interlocked> tipi di campi, [`lock`](lock-statement.md) utilizzare i membri della classe o proteggere l'accesso tramite l'istruzione .</span><span class="sxs-lookup"><span data-stu-id="5f77d-118">To protect multi-threaded access to those types of fields, use the <xref:System.Threading.Interlocked> class members or protect access using the [`lock`](lock-statement.md) statement.</span></span>

<span data-ttu-id="5f77d-119">La parola chiave `volatile` può essere applicata solo a campi di un oggetto `class` o `struct`.</span><span class="sxs-lookup"><span data-stu-id="5f77d-119">The `volatile` keyword can only be applied to fields of a `class` or `struct`.</span></span> <span data-ttu-id="5f77d-120">Le variabili locali non possono essere dichiarate `volatile`.</span><span class="sxs-lookup"><span data-stu-id="5f77d-120">Local variables cannot be declared `volatile`.</span></span>

## <a name="example"></a><span data-ttu-id="5f77d-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="5f77d-121">Example</span></span>

<span data-ttu-id="5f77d-122">Nell'esempio riportato di seguito viene illustrato come dichiarare `volatile` una variabile di campo pubblico.</span><span class="sxs-lookup"><span data-stu-id="5f77d-122">The following example shows how to declare a public field variable as `volatile`.</span></span>

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Declaration)]

<span data-ttu-id="5f77d-123">Nell'esempio seguente viene illustrato come un thread di lavoro o ausiliario può essere creato e usato per eseguire l'elaborazione in parallelo con quella del thread principale.</span><span class="sxs-lookup"><span data-stu-id="5f77d-123">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="5f77d-124">Per altre informazioni sul multithreading, vedere [Threading gestito](../../../standard/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="5f77d-124">For more information about multithreading, see [Managed Threading](../../../standard/threading/index.md).</span></span>

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Volatile)]

<span data-ttu-id="5f77d-125">Dopo aver aggiunto il modificatore `volatile` alla dichiarazione di `_shouldStop`, si otterranno sempre gli stessi risultati, analogamente all'estratto mostrato nel codice precedente.</span><span class="sxs-lookup"><span data-stu-id="5f77d-125">With the `volatile` modifier added to the declaration of `_shouldStop` in place, you'll always get the same results (similar to the excerpt shown in the preceding code).</span></span> <span data-ttu-id="5f77d-126">Tuttavia, senza il modificatore nel membro `_shouldStop`, il comportamento è imprevedibile.</span><span class="sxs-lookup"><span data-stu-id="5f77d-126">However, without that modifier on the `_shouldStop` member, the behavior is unpredictable.</span></span> <span data-ttu-id="5f77d-127">Il metodo `DoWork` può ottimizzare l'accesso ai membri, causando la lettura dei dati non aggiornati.</span><span class="sxs-lookup"><span data-stu-id="5f77d-127">The `DoWork` method may optimize the member access, resulting in reading stale data.</span></span> <span data-ttu-id="5f77d-128">A causa della natura della programmazione multithread, il numero di letture non aggiornate è imprevedibile.</span><span class="sxs-lookup"><span data-stu-id="5f77d-128">Because of the nature of multi-threaded programming, the number of stale reads is unpredictable.</span></span> <span data-ttu-id="5f77d-129">Esecuzioni diverse del programma produrranno risultati leggermente diversi.</span><span class="sxs-lookup"><span data-stu-id="5f77d-129">Different runs of the program will produce somewhat different results.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5f77d-130">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="5f77d-130">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5f77d-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f77d-131">See also</span></span>

- [<span data-ttu-id="5f77d-132">Specifica del linguaggio C#: parola chiave volatile</span><span class="sxs-lookup"><span data-stu-id="5f77d-132">C# language specification: volatile keyword</span></span>](../../../../_csharplang/spec/classes.md#volatile-fields)
- [<span data-ttu-id="5f77d-133">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="5f77d-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5f77d-134">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="5f77d-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5f77d-135">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="5f77d-135">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="5f77d-136">Modificatori</span><span class="sxs-lookup"><span data-stu-id="5f77d-136">Modifiers</span></span>](index.md)
- [<span data-ttu-id="5f77d-137">lock (istruzione)</span><span class="sxs-lookup"><span data-stu-id="5f77d-137">lock statement</span></span>](lock-statement.md)
- <xref:System.Threading.Interlocked>
