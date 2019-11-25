---
title: 'Procedura: etichettare le istruzioni'
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: be116ac8046c43e89e44c2d9127c6131e4dfaa52
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347374"
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="16bd6-102">Procedura: etichettare le istruzioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16bd6-102">How to: Label Statements (Visual Basic)</span></span>

<span data-ttu-id="16bd6-103">Statement blocks are made up of lines of code delimited by colons.</span><span class="sxs-lookup"><span data-stu-id="16bd6-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="16bd6-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span><span class="sxs-lookup"><span data-stu-id="16bd6-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="16bd6-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="16bd6-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>

<span data-ttu-id="16bd6-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span><span class="sxs-lookup"><span data-stu-id="16bd6-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="16bd6-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span><span class="sxs-lookup"><span data-stu-id="16bd6-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>

<span data-ttu-id="16bd6-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span><span class="sxs-lookup"><span data-stu-id="16bd6-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="16bd6-109">If it does not, the compiler assumes it is a label.</span><span class="sxs-lookup"><span data-stu-id="16bd6-109">If it does not, the compiler assumes it is a label.</span></span>

<span data-ttu-id="16bd6-110">Labels have their own declaration space and do not interfere with other identifiers.</span><span class="sxs-lookup"><span data-stu-id="16bd6-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="16bd6-111">A label's scope is the body of the method.</span><span class="sxs-lookup"><span data-stu-id="16bd6-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="16bd6-112">Label declaration takes precedence in any ambiguous situation.</span><span class="sxs-lookup"><span data-stu-id="16bd6-112">Label declaration takes precedence in any ambiguous situation.</span></span>

> [!NOTE]
> <span data-ttu-id="16bd6-113">Labels can be used only on executable statements inside methods.</span><span class="sxs-lookup"><span data-stu-id="16bd6-113">Labels can be used only on executable statements inside methods.</span></span>

## <a name="to-label-a-line-of-code"></a><span data-ttu-id="16bd6-114">To label a line of code</span><span class="sxs-lookup"><span data-stu-id="16bd6-114">To label a line of code</span></span>

<span data-ttu-id="16bd6-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span><span class="sxs-lookup"><span data-stu-id="16bd6-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>

<span data-ttu-id="16bd6-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span><span class="sxs-lookup"><span data-stu-id="16bd6-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>

[!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]

## <a name="see-also"></a><span data-ttu-id="16bd6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16bd6-117">See also</span></span>

- [<span data-ttu-id="16bd6-118">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="16bd6-118">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="16bd6-119">Nomi di elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="16bd6-119">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="16bd6-120">Struttura del programma e convenzioni di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="16bd6-120">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
