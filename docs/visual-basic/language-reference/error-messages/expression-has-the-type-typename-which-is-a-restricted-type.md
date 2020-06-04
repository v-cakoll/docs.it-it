---
title: L'espressione è di tipo '<typename>' che corrisponde a un tipo limitato e non può essere utilizzato per accedere ai membri ereditati da 'Object' o 'ValueType'
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 0eb30488312cc7519f39a6b819aea15489f2f70a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409520"
---
# <a name="expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a><span data-ttu-id="24d40-102">L'espressione è di tipo '\<typename>' che corrisponde a un tipo limitato e non può essere utilizzato per accedere ai membri ereditati da 'Object' o 'ValueType'</span><span class="sxs-lookup"><span data-stu-id="24d40-102">Expression has the type '\<typename>' which is a restricted type and cannot be used to access members inherited from 'Object' or 'ValueType'</span></span>
<span data-ttu-id="24d40-103">Un'espressione restituisce un tipo che non può essere boxed dal Common Language Runtime (CLR) ma accede a un membro che richiede la conversione boxing.</span><span class="sxs-lookup"><span data-stu-id="24d40-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>  
  
 <span data-ttu-id="24d40-104">Il termine*boxing* indica il processo di elaborazione necessario per la conversione di un tipo in `Object` o <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="24d40-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="24d40-105">Il Common Language Runtime non può eseguire il box di determinati tipi di struttura, ad esempio, <xref:System.ArgIterator> <xref:System.RuntimeArgumentHandle> e <xref:System.TypedReference> .</span><span class="sxs-lookup"><span data-stu-id="24d40-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>  
  
 <span data-ttu-id="24d40-106">Questa espressione tenta di usare il tipo con restrizioni per chiamare un metodo ereditato da <xref:System.Object> o <xref:System.ValueType> , ad esempio <xref:System.Object.GetHashCode%2A> o <xref:System.Object.ToString%2A> .</span><span class="sxs-lookup"><span data-stu-id="24d40-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="24d40-107">Per accedere a questo metodo, Visual Basic ha tentato di eseguire una conversione boxing implicita che genera questo errore.</span><span class="sxs-lookup"><span data-stu-id="24d40-107">To access this method, Visual Basic has attempted an implicit boxing conversion that causes this error.</span></span>  
  
 <span data-ttu-id="24d40-108">**ID errore:** BC31393</span><span class="sxs-lookup"><span data-stu-id="24d40-108">**Error ID:** BC31393</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="24d40-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="24d40-109">To correct this error</span></span>  
  
1. <span data-ttu-id="24d40-110">Trovare l'espressione che restituisce il tipo citato.</span><span class="sxs-lookup"><span data-stu-id="24d40-110">Locate the expression that evaluates to the cited type.</span></span>  
  
2. <span data-ttu-id="24d40-111">Individuare la parte dell'istruzione che tenta di chiamare il metodo ereditato da <xref:System.Object> o <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="24d40-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>  
  
3. <span data-ttu-id="24d40-112">Riscrivere l'istruzione per evitare la chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="24d40-112">Rewrite the statement to avoid the method call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24d40-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24d40-113">See also</span></span>

- [<span data-ttu-id="24d40-114">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="24d40-114">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
