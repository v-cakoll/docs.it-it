---
title: Espressione è di tipo &#39; &lt;typename&gt; &#39; che è un tipo con restrizioni e non può essere utilizzato per accedere ai membri ereditati da &#39;oggetto&#39; o &#39;ValueType&#39;
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 2ba2298da77ac31abc0b1b4ad84328be7bc6dbb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587573"
---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a><span data-ttu-id="1b2eb-102">Espressione è di tipo &#39; &lt;typename&gt; &#39; che è un tipo con restrizioni e non può essere utilizzato per accedere ai membri ereditati da &#39;oggetto&#39; o &#39;ValueType&#39;</span><span class="sxs-lookup"><span data-stu-id="1b2eb-102">Expression has the type &#39;&lt;typename&gt;&#39; which is a restricted type and cannot be used to access members inherited from &#39;Object&#39; or &#39;ValueType&#39;</span></span>
<span data-ttu-id="1b2eb-103">Un'espressione restituisce un tipo che non può essere sottoposto a boxing tramite common language runtime (CLR), ma accede a un membro che richiede una conversione boxing.</span><span class="sxs-lookup"><span data-stu-id="1b2eb-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>  
  
 <span data-ttu-id="1b2eb-104">Il termine*boxing* indica il processo di elaborazione necessario per la conversione di un tipo in `Object` o <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="1b2eb-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="1b2eb-105">Common language runtime non supporta il boxing determinati tipi di struttura, ad esempio <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, e <xref:System.TypedReference>.</span><span class="sxs-lookup"><span data-stu-id="1b2eb-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>  
  
 <span data-ttu-id="1b2eb-106">Questa espressione tenta di utilizzare il tipo con restrizioni per chiamare un metodo ereditato da <xref:System.Object> o <xref:System.ValueType>, ad esempio <xref:System.Object.GetHashCode%2A> o <xref:System.Object.ToString%2A>.</span><span class="sxs-lookup"><span data-stu-id="1b2eb-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="1b2eb-107">Per accedere a questo metodo, Visual Basic è tentata una conversione boxing implicita che genera questo errore.</span><span class="sxs-lookup"><span data-stu-id="1b2eb-107">To access this method, Visual Basic has attempted an implicit boxing conversion that causes this error.</span></span>  
  
 <span data-ttu-id="1b2eb-108">**ID errore:** BC31393</span><span class="sxs-lookup"><span data-stu-id="1b2eb-108">**Error ID:** BC31393</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1b2eb-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="1b2eb-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="1b2eb-110">Trovare l'espressione che restituisce il tipo citato.</span><span class="sxs-lookup"><span data-stu-id="1b2eb-110">Locate the expression that evaluates to the cited type.</span></span>  
  
2.  <span data-ttu-id="1b2eb-111">Individuare la parte dell'istruzione che tenta di chiamare il metodo ereditato da <xref:System.Object> o <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="1b2eb-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>  
  
3.  <span data-ttu-id="1b2eb-112">Riscrivere le istruzioni per evitare la chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="1b2eb-112">Rewrite the statement to avoid the method call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b2eb-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b2eb-113">See Also</span></span>  
 [<span data-ttu-id="1b2eb-114">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="1b2eb-114">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
