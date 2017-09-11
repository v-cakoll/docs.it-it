---
title: '&quot;As Any&quot; non supportato nelle istruzioni &quot;Declare&quot; | Documenti di Microsoft'
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30828
- vbc30828
dev_langs:
- VB
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
caps.latest.revision: 11
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
ms.openlocfilehash: bed9beb0c34c1a918029cc7fac4f8c97950eee23
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a><span data-ttu-id="feffd-102">'As Any' non supportato nelle istruzioni 'Declare'</span><span class="sxs-lookup"><span data-stu-id="feffd-102">&#39;As Any&#39; is not supported in &#39;Declare&#39; statements</span></span>
<span data-ttu-id="feffd-103">Il `Any` tipo di dati è stato utilizzato con `Declare` istruzioni in Visual Basic 6.0 e versioni precedenti per consentire l'utilizzo di argomenti che può contenere qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="feffd-103">The `Any` data type was used with `Declare` statements in Visual Basic 6.0 and earlier versions to permit the use of arguments that could contain any type of data.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="feffd-104">supporta l'overload, tuttavia e consente pertanto di `Any` obsoleto del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="feffd-104"> supports overloading, however, and so makes the `Any` data type obsolete.</span></span>  
  
 <span data-ttu-id="feffd-105">**ID errore:** BC30828</span><span class="sxs-lookup"><span data-stu-id="feffd-105">**Error ID:** BC30828</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="feffd-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="feffd-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="feffd-107">Dichiarare i parametri del tipo specifico di cui che si desidera utilizzare. Per esempio.</span><span class="sxs-lookup"><span data-stu-id="feffd-107">Declare parameters of the specific type you want to use; for example.</span></span>  
  
     <span data-ttu-id="feffd-108">[!code-vb[&#95; VbVbalrStatements](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="feffd-108">[!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]</span></span>  
  
2.  <span data-ttu-id="feffd-109">Utilizzare il <xref:System.Runtime.InteropServices.MarshalAsAttribute>attributo per specificare `As Any` quando `Void*` prevede la routine chiamata.</xref:System.Runtime.InteropServices.MarshalAsAttribute></span><span class="sxs-lookup"><span data-stu-id="feffd-109">Use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify `As Any` when `Void*` is expected by the procedure being called.</span></span>  
  
     <span data-ttu-id="feffd-110">[!code-vb[&#96; VbVbalrStatements](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="feffd-110">[!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feffd-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="feffd-111">See Also</span></span>  
 <span data-ttu-id="feffd-112"><xref:System.Runtime.InteropServices.MarshalAsAttribute></xref:System.Runtime.InteropServices.MarshalAsAttribute></span><span class="sxs-lookup"><span data-stu-id="feffd-112"><xref:System.Runtime.InteropServices.MarshalAsAttribute></span></span>   
<span data-ttu-id="feffd-113"> [Procedura dettagliata: Chiamata delle API di Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md) </span><span class="sxs-lookup"><span data-stu-id="feffd-113"> [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md) </span></span>  
<span data-ttu-id="feffd-114"> [Declare (istruzione)](../../../visual-basic/language-reference/statements/declare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="feffd-114"> [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) </span></span>  
<span data-ttu-id="feffd-115"> [Creazione di prototipi nel codice gestito](http://msdn.microsoft.com/library/ecdcf25d-cae3-4f07-a2b6-8397ac6dc42d)</span><span class="sxs-lookup"><span data-stu-id="feffd-115"> [Creating Prototypes in Managed Code](http://msdn.microsoft.com/library/ecdcf25d-cae3-4f07-a2b6-8397ac6dc42d)</span></span>
