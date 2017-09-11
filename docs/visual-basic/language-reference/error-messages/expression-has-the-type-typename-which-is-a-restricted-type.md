---
title: "Espressione è di tipo &quot;&lt;typename&gt;&quot; che corrisponde a un tipo limitato e non può essere utilizzato per accedere ai membri ereditati da &quot;Object&quot; o &quot;ValueType&quot; | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc31393
- vbc31393
dev_langs:
- VB
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b89f7e83bf596c52296a090563d0dd0403ace548
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a><span data-ttu-id="325a2-102">Espressione è di tipo '&lt;typename&gt;' che corrisponde a un tipo limitato e non può essere utilizzato per accedere ai membri ereditati da 'Object' o 'ValueType'</span><span class="sxs-lookup"><span data-stu-id="325a2-102">Expression has the type &#39;&lt;typename&gt;&#39; which is a restricted type and cannot be used to access members inherited from &#39;Object&#39; or &#39;ValueType&#39;</span></span>
<span data-ttu-id="325a2-103">Un'espressione restituisce un tipo che non può essere sottoposto a boxing da common language runtime (CLR), ma accede a un membro che richiede il boxing.</span><span class="sxs-lookup"><span data-stu-id="325a2-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>  
  
 <span data-ttu-id="325a2-104">*Conversione boxing* si intende l'elaborazione necessaria convertire un tipo di `Object` o, in alcuni casi, per <xref:System.ValueType>.</xref:System.ValueType></span><span class="sxs-lookup"><span data-stu-id="325a2-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="325a2-105">Common language runtime non supporta il boxing determinati tipi di struttura, ad esempio <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>e <xref:System.TypedReference>.</xref:System.TypedReference> </xref:System.RuntimeArgumentHandle> </xref:System.ArgIterator></span><span class="sxs-lookup"><span data-stu-id="325a2-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>  
  
 <span data-ttu-id="325a2-106">Questa espressione tenta di utilizzare il tipo con restrizioni per chiamare un metodo ereditato da <xref:System.Object>o <xref:System.ValueType>, ad esempio <xref:System.Object.GetHashCode%2A>o <xref:System.Object.ToString%2A>.</xref:System.Object.ToString%2A> </xref:System.Object.GetHashCode%2A> </xref:System.ValueType> </xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="325a2-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="325a2-107">Per accedere a questo metodo, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ha tentato una conversione boxing implicita che causa questo errore.</span><span class="sxs-lookup"><span data-stu-id="325a2-107">To access this method, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] has attempted an implicit boxing conversion that causes this error.</span></span>  
  
 <span data-ttu-id="325a2-108">**ID errore:** BC31393</span><span class="sxs-lookup"><span data-stu-id="325a2-108">**Error ID:** BC31393</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="325a2-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="325a2-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="325a2-110">Trovare l'espressione che restituisce il tipo citato.</span><span class="sxs-lookup"><span data-stu-id="325a2-110">Locate the expression that evaluates to the cited type.</span></span>  
  
2.  <span data-ttu-id="325a2-111">Individuare la parte dell'istruzione che tenta di chiamare il metodo ereditato da <xref:System.Object>o <xref:System.ValueType>.</xref:System.ValueType> </xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="325a2-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>  
  
3.  <span data-ttu-id="325a2-112">Riscrivere l'istruzione per evitare la chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="325a2-112">Rewrite the statement to avoid the method call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="325a2-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="325a2-113">See Also</span></span>  
 [<span data-ttu-id="325a2-114">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="325a2-114">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
