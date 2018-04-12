---
title: Istruzione Throw (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 50ada551c32b8296f0dad2ae929ca9c81a14a711
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="b89c6-102">Istruzione Throw (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b89c6-102">Throw Statement (Visual Basic)</span></span>
<span data-ttu-id="b89c6-103">Genera un'eccezione all'interno di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="b89c6-103">Throws an exception within a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b89c6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b89c6-104">Syntax</span></span>  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a><span data-ttu-id="b89c6-105">Parte</span><span class="sxs-lookup"><span data-stu-id="b89c6-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="b89c6-106">Vengono fornite informazioni sull'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="b89c6-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="b89c6-107">Facoltativo quando risiede in un `Catch` istruzione, è necessario in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="b89c6-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b89c6-108">Note</span><span class="sxs-lookup"><span data-stu-id="b89c6-108">Remarks</span></span>  
 <span data-ttu-id="b89c6-109">Il `Throw` istruzione genera un'eccezione che è possibile gestire con un codice di gestione delle eccezioni strutturata (`Try`... `Catch`... `Finally`) o il codice di gestione delle eccezioni non strutturato (`On Error GoTo`).</span><span class="sxs-lookup"><span data-stu-id="b89c6-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="b89c6-110">È possibile utilizzare il `Throw` istruzione per intercettare gli errori all'interno del codice perché Visual Basic sposta verso l'alto lo stack di chiamate fino a individuare il codice di gestione delle eccezioni appropriato.</span><span class="sxs-lookup"><span data-stu-id="b89c6-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>  
  
 <span data-ttu-id="b89c6-111">Oggetto `Throw` istruzione senza un'espressione può essere utilizzata solo un `Catch` istruzione, in cui l'istruzione case, viene rigenerata l'eccezione attualmente gestita dal `Catch` istruzione.</span><span class="sxs-lookup"><span data-stu-id="b89c6-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>  
  
 <span data-ttu-id="b89c6-112">Il `Throw` istruzione Reimposta lo stack di chiamate per il `expression` eccezione.</span><span class="sxs-lookup"><span data-stu-id="b89c6-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="b89c6-113">Se `expression` non viene specificato, lo stack di chiamate resta invariato.</span><span class="sxs-lookup"><span data-stu-id="b89c6-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="b89c6-114">È possibile accedere lo stack di chiamate dell'eccezione tramite la <xref:System.Exception.StackTrace%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b89c6-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b89c6-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="b89c6-115">Example</span></span>  
 <span data-ttu-id="b89c6-116">Il codice seguente usa il `Throw` istruzione per generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="b89c6-116">The following code uses the `Throw` statement to throw an exception:</span></span>  
  
 [!code-vb[VbVbalrStatements#84](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/throw-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="b89c6-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b89c6-117">Requirements</span></span>  
 <span data-ttu-id="b89c6-118">**Namespace:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="b89c6-118">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="b89c6-119">**Modulo:**`Interaction`</span><span class="sxs-lookup"><span data-stu-id="b89c6-119">**Module:** `Interaction`</span></span>  
  
 <span data-ttu-id="b89c6-120">**Assembly:** libreria di Runtime di Visual Basic (in Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="b89c6-120">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b89c6-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b89c6-121">See Also</span></span>  
 [<span data-ttu-id="b89c6-122">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="b89c6-122">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="b89c6-123">Istruzione On Error</span><span class="sxs-lookup"><span data-stu-id="b89c6-123">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
