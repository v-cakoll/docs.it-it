---
title: Codice unsafe e puntatori (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 75e11b34f0749270650e0e5b5a2a191a1b9e9f9a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a><span data-ttu-id="a72a7-102">Codice unsafe e puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="a72a7-102">Unsafe Code and Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="a72a7-103">Per mantenere l'indipendenza dai tipi e la sicurezza, C# non supporta il puntatore aritmetico per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a72a7-103">To maintain type safety and security, C# does not support pointer arithmetic, by default.</span></span> <span data-ttu-id="a72a7-104">Tuttavia, se si usa la parola chiave [unsafe](../../../csharp/language-reference/keywords/unsafe.md), è possibile definire un contesto non sicuro in cui si possono usare i puntatori.</span><span class="sxs-lookup"><span data-stu-id="a72a7-104">However, by using the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, you can define an unsafe context in which pointers can be used.</span></span> <span data-ttu-id="a72a7-105">Per altre informazioni sui puntatori, vedere l'argomento [Tipi di puntatori](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="a72a7-105">For more information about pointers, see the topic [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a72a7-106">Nel supporto Common Language Runtime (CLR) il codice di tipo unsafe è detto codice non verificabile.</span><span class="sxs-lookup"><span data-stu-id="a72a7-106">In the common language runtime (CLR), unsafe code is referred to as unverifiable code.</span></span> <span data-ttu-id="a72a7-107">Il codice unsafe in C# non è necessariamente pericoloso, è solo codice di cui il supporto CLR non può verificare la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a72a7-107">Unsafe code in C# is not necessarily dangerous; it is just code whose safety cannot be verified by the CLR.</span></span> <span data-ttu-id="a72a7-108">CLR pertanto eseguirà il codice unsafe solo se si trova in un assembly completamente attendibile.</span><span class="sxs-lookup"><span data-stu-id="a72a7-108">The CLR will therefore only execute unsafe code if it is in a fully trusted assembly.</span></span> <span data-ttu-id="a72a7-109">Se si usa codice unsafe, è responsabilità dell'utente verificare che il codice non introduca rischi per la sicurezza o errori dei puntatori.</span><span class="sxs-lookup"><span data-stu-id="a72a7-109">If you use unsafe code, it is your responsibility to ensure that your code does not introduce security risks or pointer errors.</span></span>  
  
## <a name="unsafe-code-overview"></a><span data-ttu-id="a72a7-110">Panoramica del codice unsafe</span><span class="sxs-lookup"><span data-stu-id="a72a7-110">Unsafe Code Overview</span></span>  
 <span data-ttu-id="a72a7-111">Il codice unsafe presenta le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="a72a7-111">Unsafe code has the following properties:</span></span>  
  
-   <span data-ttu-id="a72a7-112">Metodi, tipi e blocchi di codice possono essere definiti come unsafe.</span><span class="sxs-lookup"><span data-stu-id="a72a7-112">Methods, types, and code blocks can be defined as unsafe.</span></span>  
  
-   <span data-ttu-id="a72a7-113">In alcuni casi il codice unsafe può migliorare le prestazioni di un'applicazione poiché vengono rimosse le verifiche dei limiti di matrice.</span><span class="sxs-lookup"><span data-stu-id="a72a7-113">In some cases, unsafe code may increase an application's performance by removing array bounds checks.</span></span>  
  
-   <span data-ttu-id="a72a7-114">Il codice unsafe è necessario quando si chiamano funzioni native che richiedono i puntatori.</span><span class="sxs-lookup"><span data-stu-id="a72a7-114">Unsafe code is required when you call native functions that require pointers.</span></span>  
  
-   <span data-ttu-id="a72a7-115">L'uso del codice unsafe implica rischi per la sicurezza e la stabilità.</span><span class="sxs-lookup"><span data-stu-id="a72a7-115">Using unsafe code introduces security and stability risks.</span></span>  
  
-   <span data-ttu-id="a72a7-116">Affinché C# compili il codice unsafe, l'applicazione deve essere compilata con [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a72a7-116">In order for C# to compile unsafe code, the application must be compiled with [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a72a7-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="a72a7-117">Related Sections</span></span>  
 <span data-ttu-id="a72a7-118">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="a72a7-118">For more information, see:</span></span>  
  
-   [<span data-ttu-id="a72a7-119">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="a72a7-119">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
-   [<span data-ttu-id="a72a7-120">Buffer a dimensione fissa</span><span class="sxs-lookup"><span data-stu-id="a72a7-120">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)  
  
-   [<span data-ttu-id="a72a7-121">Procedura: Usare i puntatori per copiare una matrice di byte</span><span class="sxs-lookup"><span data-stu-id="a72a7-121">How to: Use Pointers to Copy an Array of Bytes</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-use-pointers-to-copy-an-array-of-bytes.md)  
  
-   [<span data-ttu-id="a72a7-122">unsafe</span><span class="sxs-lookup"><span data-stu-id="a72a7-122">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="a72a7-123">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="a72a7-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a72a7-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a72a7-124">See Also</span></span>  
 [<span data-ttu-id="a72a7-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a72a7-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

