---
title: '&#39;Come qualsiasi&#39; non è supportato in &#39;Declare&#39; istruzioni'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d8146e339ac5cb005b99c9a1e02f1cd248c4558b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a><span data-ttu-id="d7a46-102">&#39;Come qualsiasi&#39; non è supportato in &#39;Declare&#39; istruzioni</span><span class="sxs-lookup"><span data-stu-id="d7a46-102">&#39;As Any&#39; is not supported in &#39;Declare&#39; statements</span></span>
<span data-ttu-id="d7a46-103">Il `Any` tipo di dati è stato utilizzato con `Declare` istruzioni in Visual Basic 6.0 e versioni precedenti per consentire l'utilizzo di argomenti che può contenere qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="d7a46-103">The `Any` data type was used with `Declare` statements in Visual Basic 6.0 and earlier versions to permit the use of arguments that could contain any type of data.</span></span> <span data-ttu-id="d7a46-104">Visual Basic supporta l'overload, tuttavia e la imposta come in questo caso il `Any` del tipo di dati obsoleta.</span><span class="sxs-lookup"><span data-stu-id="d7a46-104">Visual Basic supports overloading, however, and so makes the `Any` data type obsolete.</span></span>  
  
 <span data-ttu-id="d7a46-105">**ID errore:** BC30828</span><span class="sxs-lookup"><span data-stu-id="d7a46-105">**Error ID:** BC30828</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d7a46-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d7a46-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="d7a46-107">Dichiarare i parametri del tipo specifico che si desidera utilizzare. Per esempio.</span><span class="sxs-lookup"><span data-stu-id="d7a46-107">Declare parameters of the specific type you want to use; for example.</span></span>  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  <span data-ttu-id="d7a46-108">Utilizzare il <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributo per specificare `As Any` quando `Void*` è prevista dalla routine chiamata.</span><span class="sxs-lookup"><span data-stu-id="d7a46-108">Use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify `As Any` when `Void*` is expected by the procedure being called.</span></span>  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d7a46-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7a46-109">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="d7a46-110">Procedura dettagliata: Chiamata delle API di Windows</span><span class="sxs-lookup"><span data-stu-id="d7a46-110">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [<span data-ttu-id="d7a46-111">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="d7a46-111">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="d7a46-112">Creazione di prototipi nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="d7a46-112">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
