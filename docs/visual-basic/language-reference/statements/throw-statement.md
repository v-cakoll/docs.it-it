---
title: Istruzione Throw
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
ms.openlocfilehash: 95572b1739490e90f53da6b6ec283bfb532c46d3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404135"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="781d5-102">Istruzione Throw (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="781d5-102">Throw Statement (Visual Basic)</span></span>

<span data-ttu-id="781d5-103">Genera un'eccezione all'interno di una routine.</span><span class="sxs-lookup"><span data-stu-id="781d5-103">Throws an exception within a procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="781d5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="781d5-104">Syntax</span></span>

```vb
Throw [ expression ]
```

## <a name="part"></a><span data-ttu-id="781d5-105">Parte</span><span class="sxs-lookup"><span data-stu-id="781d5-105">Part</span></span>

`expression`\
<span data-ttu-id="781d5-106">Fornisce informazioni sull'eccezione da generare.</span><span class="sxs-lookup"><span data-stu-id="781d5-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="781d5-107">Facoltativo quando si trova in un' `Catch` istruzione, in caso contrario obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="781d5-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>

## <a name="remarks"></a><span data-ttu-id="781d5-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="781d5-108">Remarks</span></span>

<span data-ttu-id="781d5-109">L' `Throw` istruzione genera un'eccezione che può essere gestita con codice di gestione delle eccezioni strutturato ( `Try` ... `Catch` ...`Finally`) o codice di gestione delle eccezioni non strutturato ( `On Error GoTo` ).</span><span class="sxs-lookup"><span data-stu-id="781d5-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="781d5-110">È possibile usare l' `Throw` istruzione per intercettare gli errori all'interno del codice perché Visual Basic sposta lo stack di chiamate fino a trovare il codice di gestione delle eccezioni appropriato.</span><span class="sxs-lookup"><span data-stu-id="781d5-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>

<span data-ttu-id="781d5-111">Un'istruzione `Throw` senza espressione può essere utilizzata solo in un' `Catch` istruzione, nel qual caso l'istruzione genera nuovamente l'eccezione attualmente gestita dall' `Catch` istruzione.</span><span class="sxs-lookup"><span data-stu-id="781d5-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>

<span data-ttu-id="781d5-112">L' `Throw` istruzione Reimposta lo stack di chiamate per l' `expression` eccezione.</span><span class="sxs-lookup"><span data-stu-id="781d5-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="781d5-113">Se `expression` non viene specificato, lo stack di chiamate viene lasciato invariato.</span><span class="sxs-lookup"><span data-stu-id="781d5-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="781d5-114">È possibile accedere allo stack di chiamate per l'eccezione tramite la <xref:System.Exception.StackTrace%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="781d5-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="781d5-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="781d5-115">Example</span></span>

<span data-ttu-id="781d5-116">Nel codice seguente viene utilizzata l' `Throw` istruzione per generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="781d5-116">The following code uses the `Throw` statement to throw an exception:</span></span>

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a><span data-ttu-id="781d5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="781d5-117">See also</span></span>

- [<span data-ttu-id="781d5-118">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="781d5-118">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="781d5-119">Istruzione On Error</span><span class="sxs-lookup"><span data-stu-id="781d5-119">On Error Statement</span></span>](on-error-statement.md)
