---
title: "'As Any' non è supportato nelle istruzioni 'Declare'"
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: bdf339e0d91106a6d6527e085608a06b0439951c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274086"
---
# <a name="as-any-is-not-supported-in-declare-statements"></a><span data-ttu-id="d58c8-102">'As Any' non è supportato nelle istruzioni 'Declare'</span><span class="sxs-lookup"><span data-stu-id="d58c8-102">'As Any' is not supported in 'Declare' statements</span></span>
<span data-ttu-id="d58c8-103">Il `Any` tipo di dati è stato usato con `Declare` istruzioni in Visual Basic 6.0 e versioni precedenti per consentire l'uso di argomenti che può contenere qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="d58c8-103">The `Any` data type was used with `Declare` statements in Visual Basic 6.0 and earlier versions to permit the use of arguments that could contain any type of data.</span></span> <span data-ttu-id="d58c8-104">Visual Basic supporta l'overload, tuttavia e la imposta come in questo caso il `Any` obsoleto del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="d58c8-104">Visual Basic supports overloading, however, and so makes the `Any` data type obsolete.</span></span>  
  
 <span data-ttu-id="d58c8-105">**ID errore:** BC30828</span><span class="sxs-lookup"><span data-stu-id="d58c8-105">**Error ID:** BC30828</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d58c8-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d58c8-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="d58c8-107">Dichiarare i parametri del tipo specifico da usare; Per esempio.</span><span class="sxs-lookup"><span data-stu-id="d58c8-107">Declare parameters of the specific type you want to use; for example.</span></span>  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  <span data-ttu-id="d58c8-108">Usare la <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributo per specificare `As Any` quando `Void*` è previsto per la routine chiamata.</span><span class="sxs-lookup"><span data-stu-id="d58c8-108">Use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify `As Any` when `Void*` is expected by the procedure being called.</span></span>  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d58c8-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d58c8-109">See also</span></span>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="d58c8-110">Procedura dettagliata: Chiamata delle API di Windows</span><span class="sxs-lookup"><span data-stu-id="d58c8-110">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="d58c8-111">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="d58c8-111">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="d58c8-112">Creazione di prototipi nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="d58c8-112">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
