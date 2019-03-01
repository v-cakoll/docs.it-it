---
title: Istruzione Throw (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: c17adc6df0f8cf94f06547b48a32b2ffb8f303ca
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973483"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="1c79f-102">Istruzione Throw (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c79f-102">Throw Statement (Visual Basic)</span></span>
<span data-ttu-id="1c79f-103">Genera un'eccezione all'interno di una routine.</span><span class="sxs-lookup"><span data-stu-id="1c79f-103">Throws an exception within a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c79f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c79f-104">Syntax</span></span>  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a><span data-ttu-id="1c79f-105">Parte</span><span class="sxs-lookup"><span data-stu-id="1c79f-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="1c79f-106">Vengono fornite informazioni sull'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="1c79f-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="1c79f-107">Facoltativo quando che risiedono un `Catch` istruzione, in caso contrario, è necessario.</span><span class="sxs-lookup"><span data-stu-id="1c79f-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c79f-108">Note</span><span class="sxs-lookup"><span data-stu-id="1c79f-108">Remarks</span></span>  
 <span data-ttu-id="1c79f-109">Il `Throw` istruzione genera un'eccezione che è possibile gestire con un codice di gestione delle eccezioni strutturata (`Try`... `Catch`... `Finally`) o il codice di gestione delle eccezioni non strutturato (`On Error GoTo`).</span><span class="sxs-lookup"><span data-stu-id="1c79f-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="1c79f-110">È possibile usare il `Throw` istruzione per intercettare gli errori all'interno del codice perché Visual Basic sposta verso l'alto nello stack di chiamate fino a individuare il codice di gestione delle eccezioni appropriato.</span><span class="sxs-lookup"><span data-stu-id="1c79f-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>  
  
 <span data-ttu-id="1c79f-111">Oggetto `Throw` istruzione senza un'espressione può essere usata solo un `Catch` istruzione, in cui l'istruzione case genera nuovamente l'eccezione attualmente gestita dal `Catch` istruzione.</span><span class="sxs-lookup"><span data-stu-id="1c79f-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>  
  
 <span data-ttu-id="1c79f-112">Il `Throw` istruzione Reimposta lo stack di chiamate per il `expression` eccezione.</span><span class="sxs-lookup"><span data-stu-id="1c79f-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="1c79f-113">Se `expression` non viene specificato, lo stack di chiamate viene lasciata invariata.</span><span class="sxs-lookup"><span data-stu-id="1c79f-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="1c79f-114">È possibile accedere lo stack di chiamate dell'eccezione mediante il <xref:System.Exception.StackTrace%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="1c79f-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c79f-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c79f-115">Example</span></span>  
 <span data-ttu-id="1c79f-116">Il codice seguente usa il `Throw` istruzione per generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="1c79f-116">The following code uses the `Throw` statement to throw an exception:</span></span>  
  
 [!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]  
  
## <a name="requirements"></a><span data-ttu-id="1c79f-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c79f-117">Requirements</span></span>  
 <span data-ttu-id="1c79f-118">**Spazio dei nomi:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="1c79f-118">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="1c79f-119">**Modulo:** `Interaction`</span><span class="sxs-lookup"><span data-stu-id="1c79f-119">**Module:** `Interaction`</span></span>  
  
 <span data-ttu-id="1c79f-120">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="1c79f-120">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c79f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c79f-121">See also</span></span>
- [<span data-ttu-id="1c79f-122">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="1c79f-122">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="1c79f-123">Istruzione On Error</span><span class="sxs-lookup"><span data-stu-id="1c79f-123">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
