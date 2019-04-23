---
title: 'Procedura: Creare una nuova variabile (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: ee1e93b4e9819992f17738eb024004a4d66210d1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59332586"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="65ae1-102">Procedura: Creare una nuova variabile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65ae1-102">How to: Create a New Variable (Visual Basic)</span></span>
<span data-ttu-id="65ae1-103">Creare una variabile con un [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="65ae1-103">You create a variable with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
### <a name="to-create-a-new-variable"></a><span data-ttu-id="65ae1-104">Per creare una nuova variabile</span><span class="sxs-lookup"><span data-stu-id="65ae1-104">To create a new variable</span></span>  
  
1. <span data-ttu-id="65ae1-105">Dichiarare la variabile in un `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="65ae1-105">Declare the variable in a `Dim` statement.</span></span>  
  
    ```  
    Dim newCustomer  
    ```  
  
2. <span data-ttu-id="65ae1-106">Includono informazioni specifiche per le caratteristiche della variabile, ad esempio [privati](../../../../visual-basic/language-reference/modifiers/private.md), [statici](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), oppure [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="65ae1-106">Include specifications for the variable's characteristics, such as [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), or [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="65ae1-107">Per altre informazioni, vedere [caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="65ae1-107">For more information, see [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
     <span data-ttu-id="65ae1-108">Non è necessario il `Dim` parola chiave se si usano altre parole chiave nella dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="65ae1-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>  
  
3. <span data-ttu-id="65ae1-109">Seguire le specifiche con il nome della variabile, che deve seguire le convenzioni e regole di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="65ae1-109">Follow the specifications with the variable's name, which must follow Visual Basic rules and conventions.</span></span> <span data-ttu-id="65ae1-110">Per altre informazioni, vedere [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="65ae1-110">For more information, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
4. <span data-ttu-id="65ae1-111">Seguire il nome con il [come](../../../../visual-basic/language-reference/statements/as-clause.md) clausola per specificare il tipo di dati della variabile.</span><span class="sxs-lookup"><span data-stu-id="65ae1-111">Follow the name with the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     <span data-ttu-id="65ae1-112">Se non si specifica il tipo di dati, viene usato il valore predefinito: `Object`.</span><span class="sxs-lookup"><span data-stu-id="65ae1-112">If you do not specify the data type, it uses the default: `Object`.</span></span>  
  
5. <span data-ttu-id="65ae1-113">Seguire le `As` clausola con un segno di uguale (`=`) e seguire il segno di uguale con valore iniziale della variabile.</span><span class="sxs-lookup"><span data-stu-id="65ae1-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>  
  
     <span data-ttu-id="65ae1-114">Visual Basic assegna il valore specificato per la variabile ogni volta che viene eseguito il `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="65ae1-114">Visual Basic assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="65ae1-115">Se non si specifica un valore iniziale, Visual Basic viene assegnato il valore iniziale predefinito per il tipo di dati della variabile quando si accede alla prima di tutto il codice che contiene il `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="65ae1-115">If you do not specify an initial value, Visual Basic assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>  
  
     <span data-ttu-id="65ae1-116">Se la variabile è un tipo riferimento, è possibile creare un'istanza della relativa classe includendo il [nuovo operatore](../../../../visual-basic/language-reference/operators/new-operator.md) parola chiave nel `As` clausola.</span><span class="sxs-lookup"><span data-stu-id="65ae1-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="65ae1-117">Se non si usa `New`, il valore iniziale della variabile è [Nothing](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="65ae1-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="65ae1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65ae1-118">See also</span></span>

- [<span data-ttu-id="65ae1-119">Variabili</span><span class="sxs-lookup"><span data-stu-id="65ae1-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="65ae1-120">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="65ae1-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="65ae1-121">Nomi di elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="65ae1-121">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="65ae1-122">Caratteristiche di elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="65ae1-122">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="65ae1-123">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="65ae1-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="65ae1-124">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="65ae1-124">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="65ae1-125">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="65ae1-125">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="65ae1-126">Istruzione Option Infer</span><span class="sxs-lookup"><span data-stu-id="65ae1-126">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
