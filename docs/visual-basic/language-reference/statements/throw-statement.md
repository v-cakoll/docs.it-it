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
ms.openlocfilehash: 9680700267f17c8e316de351fead61f1dc4aded0
ms.sourcegitcommit: 9ee6cd851b6e176a5811ea28ed0d5935c71950f9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/09/2019
ms.locfileid: "68869014"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="0e6ab-102">Istruzione Throw (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e6ab-102">Throw Statement (Visual Basic)</span></span>

<span data-ttu-id="0e6ab-103">Genera un'eccezione all'interno di una routine.</span><span class="sxs-lookup"><span data-stu-id="0e6ab-103">Throws an exception within a procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="0e6ab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e6ab-104">Syntax</span></span>

```vb
Throw [ expression ]
```

## <a name="part"></a><span data-ttu-id="0e6ab-105">Parte</span><span class="sxs-lookup"><span data-stu-id="0e6ab-105">Part</span></span>

`expression`\
<span data-ttu-id="0e6ab-106">Fornisce informazioni sull'eccezione da generare.</span><span class="sxs-lookup"><span data-stu-id="0e6ab-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="0e6ab-107">Facoltativo quando si trova in un' `Catch` istruzione, in caso contrario obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0e6ab-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>

## <a name="remarks"></a><span data-ttu-id="0e6ab-108">Note</span><span class="sxs-lookup"><span data-stu-id="0e6ab-108">Remarks</span></span>

<span data-ttu-id="0e6ab-109">L' `Throw` istruzione genera un'eccezione che può essere gestita con codice di gestione delle eccezioni strutturato (`Try`... `Catch`... ) o codice di gestione delle eccezioni non strutturato`On Error GoTo`(). `Finally`</span><span class="sxs-lookup"><span data-stu-id="0e6ab-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="0e6ab-110">È possibile usare l' `Throw` istruzione per intercettare gli errori all'interno del codice perché Visual Basic sposta lo stack di chiamate fino a trovare il codice di gestione delle eccezioni appropriato.</span><span class="sxs-lookup"><span data-stu-id="0e6ab-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>

<span data-ttu-id="0e6ab-111">Un' `Throw` istruzione senza espressione può essere utilizzata solo in un' `Catch` istruzione, nel qual caso l'istruzione genera nuovamente l'eccezione `Catch` attualmente gestita dall'istruzione.</span><span class="sxs-lookup"><span data-stu-id="0e6ab-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>

<span data-ttu-id="0e6ab-112">L' `Throw` istruzione Reimposta lo stack di chiamate per l' `expression` eccezione.</span><span class="sxs-lookup"><span data-stu-id="0e6ab-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="0e6ab-113">Se `expression` non viene specificato, lo stack di chiamate viene lasciato invariato.</span><span class="sxs-lookup"><span data-stu-id="0e6ab-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="0e6ab-114">È possibile accedere allo stack di chiamate per l'eccezione tramite <xref:System.Exception.StackTrace%2A> la proprietà.</span><span class="sxs-lookup"><span data-stu-id="0e6ab-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="0e6ab-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="0e6ab-115">Example</span></span>

<span data-ttu-id="0e6ab-116">Nel codice seguente viene utilizzata `Throw` l'istruzione per generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="0e6ab-116">The following code uses the `Throw` statement to throw an exception:</span></span>

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a><span data-ttu-id="0e6ab-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e6ab-117">See also</span></span>

- [<span data-ttu-id="0e6ab-118">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="0e6ab-118">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="0e6ab-119">Istruzione On Error</span><span class="sxs-lookup"><span data-stu-id="0e6ab-119">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
