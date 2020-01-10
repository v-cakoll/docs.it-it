---
title: Codice non gestito e puntatori - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
ms.openlocfilehash: 013af4e55c8fc396bbc92058d7fb454484f3263e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711831"
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a><span data-ttu-id="d0fa2-102">Codice non gestito e puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="d0fa2-102">Unsafe code and pointers (C# Programming Guide)</span></span>

<span data-ttu-id="d0fa2-103">Per mantenere l'indipendenza dai tipi e la sicurezza, C# non supporta il puntatore aritmetico per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d0fa2-103">To maintain type safety and security, C# does not support pointer arithmetic, by default.</span></span> <span data-ttu-id="d0fa2-104">Tuttavia, se si usa la parola chiave [unsafe](../../language-reference/keywords/unsafe.md), è possibile definire un contesto non sicuro in cui si possono usare i puntatori.</span><span class="sxs-lookup"><span data-stu-id="d0fa2-104">However, by using the [unsafe](../../language-reference/keywords/unsafe.md) keyword, you can define an unsafe context in which pointers can be used.</span></span> <span data-ttu-id="d0fa2-105">Per altre informazioni sui puntatori, vedere [Tipi puntatore](pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="d0fa2-105">For more information about pointers, see [Pointer types](pointer-types.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d0fa2-106">Nel supporto Common Language Runtime (CLR) il codice di tipo unsafe è detto codice non verificabile.</span><span class="sxs-lookup"><span data-stu-id="d0fa2-106">In the common language runtime (CLR), unsafe code is referred to as unverifiable code.</span></span> <span data-ttu-id="d0fa2-107">Il codice unsafe in C# non è necessariamente pericoloso, è solo codice di cui il supporto CLR non può verificare la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d0fa2-107">Unsafe code in C# is not necessarily dangerous; it is just code whose safety cannot be verified by the CLR.</span></span> <span data-ttu-id="d0fa2-108">CLR pertanto eseguirà il codice unsafe solo se si trova in un assembly completamente attendibile.</span><span class="sxs-lookup"><span data-stu-id="d0fa2-108">The CLR will therefore only execute unsafe code if it is in a fully trusted assembly.</span></span> <span data-ttu-id="d0fa2-109">Se si usa codice unsafe, è responsabilità dell'utente verificare che il codice non introduca rischi per la sicurezza o errori dei puntatori.</span><span class="sxs-lookup"><span data-stu-id="d0fa2-109">If you use unsafe code, it is your responsibility to ensure that your code does not introduce security risks or pointer errors.</span></span>  
  
## <a name="unsafe-code-overview"></a><span data-ttu-id="d0fa2-110">Panoramica del codice non gestito</span><span class="sxs-lookup"><span data-stu-id="d0fa2-110">Unsafe code overview</span></span>

<span data-ttu-id="d0fa2-111">Il codice unsafe presenta le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0fa2-111">Unsafe code has the following properties:</span></span>

- <span data-ttu-id="d0fa2-112">Metodi, tipi e blocchi di codice possono essere definiti come unsafe.</span><span class="sxs-lookup"><span data-stu-id="d0fa2-112">Methods, types, and code blocks can be defined as unsafe.</span></span>

- <span data-ttu-id="d0fa2-113">In alcuni casi il codice unsafe può migliorare le prestazioni di un'applicazione poiché vengono rimosse le verifiche dei limiti di matrice.</span><span class="sxs-lookup"><span data-stu-id="d0fa2-113">In some cases, unsafe code may increase an application's performance by removing array bounds checks.</span></span>

- <span data-ttu-id="d0fa2-114">Il codice unsafe è necessario quando si chiamano funzioni native che richiedono i puntatori.</span><span class="sxs-lookup"><span data-stu-id="d0fa2-114">Unsafe code is required when you call native functions that require pointers.</span></span>

- <span data-ttu-id="d0fa2-115">L'uso del codice unsafe implica rischi per la sicurezza e la stabilità.</span><span class="sxs-lookup"><span data-stu-id="d0fa2-115">Using unsafe code introduces security and stability risks.</span></span>

- <span data-ttu-id="d0fa2-116">Il codice che contiene blocchi non gestiti deve essere compilato con l'opzione [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) del compilatore.</span><span class="sxs-lookup"><span data-stu-id="d0fa2-116">The code that contains unsafe blocks must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="d0fa2-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="d0fa2-117">Related sections</span></span>

<span data-ttu-id="d0fa2-118">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="d0fa2-118">For more information, see:</span></span>

- [<span data-ttu-id="d0fa2-119">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="d0fa2-119">Pointer types</span></span>](pointer-types.md)

- [<span data-ttu-id="d0fa2-120">Buffer a dimensione fissa</span><span class="sxs-lookup"><span data-stu-id="d0fa2-120">Fixed size buffers</span></span>](fixed-size-buffers.md)

## <a name="c-language-specification"></a><span data-ttu-id="d0fa2-121">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d0fa2-121">C# language specification</span></span>

<span data-ttu-id="d0fa2-122">Per altre informazioni, vedere l'argomento [Codice di tipo unsafe](~/_csharplang/spec/unsafe-code.md) nella [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="d0fa2-122">For more information, see the [Unsafe code](~/_csharplang/spec/unsafe-code.md) topic of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d0fa2-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0fa2-123">See also</span></span>

- [<span data-ttu-id="d0fa2-124">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d0fa2-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d0fa2-125">unsafe</span><span class="sxs-lookup"><span data-stu-id="d0fa2-125">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
