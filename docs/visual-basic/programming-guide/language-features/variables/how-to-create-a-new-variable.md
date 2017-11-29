---
title: 'Procedura: creare una nuova variabile (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6806dcbe9e00cbae77181b79d74ddb9a1e1493f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="f3876-102">Procedura: creare una nuova variabile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3876-102">How to: Create a New Variable (Visual Basic)</span></span>
<span data-ttu-id="f3876-103">Creare una variabile con un [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f3876-103">You create a variable with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
### <a name="to-create-a-new-variable"></a><span data-ttu-id="f3876-104">Per creare una nuova variabile</span><span class="sxs-lookup"><span data-stu-id="f3876-104">To create a new variable</span></span>  
  
1.  <span data-ttu-id="f3876-105">Dichiarare la variabile in un `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f3876-105">Declare the variable in a `Dim` statement.</span></span>  
  
    ```  
    Dim newCustomer  
    ```  
  
2.  <span data-ttu-id="f3876-106">Includere specifiche per le caratteristiche della variabile, ad esempio [privata](../../../../visual-basic/language-reference/modifiers/private.md), [statico](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), o [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="f3876-106">Include specifications for the variable's characteristics, such as [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), or [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="f3876-107">Per ulteriori informazioni, vedere [caratteristiche di elemento dichiarato](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="f3876-107">For more information, see [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
     <span data-ttu-id="f3876-108">Non è necessario il `Dim` (parola chiave), se si utilizzano altre parole chiave nella dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="f3876-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>  
  
3.  <span data-ttu-id="f3876-109">Seguire le specifiche con il nome della variabile, che devono seguire [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] regole e convenzioni.</span><span class="sxs-lookup"><span data-stu-id="f3876-109">Follow the specifications with the variable's name, which must follow [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] rules and conventions.</span></span> <span data-ttu-id="f3876-110">Per ulteriori informazioni, vedere [nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="f3876-110">For more information, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  <span data-ttu-id="f3876-111">Dopo il nome con il [come](../../../../visual-basic/language-reference/statements/as-clause.md) clausola per specificare il tipo di dati della variabile.</span><span class="sxs-lookup"><span data-stu-id="f3876-111">Follow the name with the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     <span data-ttu-id="f3876-112">Se non si specifica il tipo di dati, viene utilizzato il valore predefinito: `Object`.</span><span class="sxs-lookup"><span data-stu-id="f3876-112">If you do not specify the data type, it uses the default: `Object`.</span></span>  
  
5.  <span data-ttu-id="f3876-113">Seguire il `As` clausola con un segno di uguale (`=`) e seguire il segno di uguale con valore iniziale della variabile.</span><span class="sxs-lookup"><span data-stu-id="f3876-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>  
  
     [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="f3876-114">Assegna il valore specificato per la variabile ogni volta che viene eseguito il `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f3876-114"> assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="f3876-115">Se non si specifica un valore iniziale, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] assegna il valore iniziale predefinito per il tipo di dati della variabile, la prima volta inserisce il codice che contiene il `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f3876-115">If you do not specify an initial value, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>  
  
     <span data-ttu-id="f3876-116">Se la variabile è un tipo riferimento, è possibile creare un'istanza della relativa classe includendo il [nuovo operatore](../../../../visual-basic/language-reference/operators/new-operator.md) parola chiave nel `As` clausola.</span><span class="sxs-lookup"><span data-stu-id="f3876-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="f3876-117">Se non si utilizza `New`, il valore iniziale della variabile è [nulla](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="f3876-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f3876-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3876-118">See Also</span></span>  
 [<span data-ttu-id="f3876-119">Variabili</span><span class="sxs-lookup"><span data-stu-id="f3876-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [<span data-ttu-id="f3876-120">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="f3876-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="f3876-121">Nomi di elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="f3876-121">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="f3876-122">Caratteristiche di elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="f3876-122">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [<span data-ttu-id="f3876-123">Tipi valore e tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="f3876-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="f3876-124">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="f3876-124">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)  
 [<span data-ttu-id="f3876-125">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="f3876-125">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="f3876-126">Istruzione Option Infer</span><span class="sxs-lookup"><span data-stu-id="f3876-126">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
