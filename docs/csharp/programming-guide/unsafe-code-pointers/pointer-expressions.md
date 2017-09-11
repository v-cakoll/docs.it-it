---
title: Espressioni puntatore (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- expressions [C#], pointer types
- pointer expressions [C#]
ms.assetid: 3e7d9db3-20e9-4493-9c99-53c3214d19e5
caps.latest.revision: 10
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
ms.openlocfilehash: a566881a65770fa99a97cc2ef3cceefad46d1be6
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="pointer-expressions-c-programming-guide"></a><span data-ttu-id="6b54c-102">Espressioni puntatore (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="6b54c-102">Pointer Expressions (C# Programming Guide)</span></span>
<span data-ttu-id="6b54c-103">In questa sezione vengono illustrate le seguenti espressioni puntatore:</span><span class="sxs-lookup"><span data-stu-id="6b54c-103">In this section, the following pointer expressions are discussed:</span></span>  
  
 [<span data-ttu-id="6b54c-104">Acquisizione del valore di una variabile</span><span class="sxs-lookup"><span data-stu-id="6b54c-104">Obtaining the Value of a Variable</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md)  
  
 [<span data-ttu-id="6b54c-105">Acquisizione dell'indirizzo di una variabile</span><span class="sxs-lookup"><span data-stu-id="6b54c-105">Obtaining the Address of a Variable</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md)  
  
 [<span data-ttu-id="6b54c-106">Procedura: Accedere a un membro con un puntatore</span><span class="sxs-lookup"><span data-stu-id="6b54c-106">How to: Access a Member with a Pointer</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md)  
  
 [<span data-ttu-id="6b54c-107">Procedura: Accedere a un elemento di matrice con un puntatore</span><span class="sxs-lookup"><span data-stu-id="6b54c-107">How to: Access an Array Element with a Pointer</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md)  
  
 [<span data-ttu-id="6b54c-108">Modifica dei puntatori</span><span class="sxs-lookup"><span data-stu-id="6b54c-108">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
  
## <a name="see-also"></a><span data-ttu-id="6b54c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b54c-109">See Also</span></span>  
 <span data-ttu-id="6b54c-110">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6b54c-110">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6b54c-111">[Conversioni puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="6b54c-111">[Pointer Conversions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md) </span></span>  
 <span data-ttu-id="6b54c-112">[Tipi di puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="6b54c-112">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="6b54c-113">[Tipi](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="6b54c-113">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="6b54c-114">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="6b54c-114">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="6b54c-115">[Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="6b54c-115">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="6b54c-116">stackalloc</span><span class="sxs-lookup"><span data-stu-id="6b54c-116">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

