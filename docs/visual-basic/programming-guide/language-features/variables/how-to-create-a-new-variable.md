---
title: 'Procedura: creare una nuova variabile (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Dim statement
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: 29
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 3b5aa4e5e0b84f41ac3df73bc70d8402d10b21a2
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017

---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="85482-102">Procedura: creare una nuova variabile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85482-102">How to: Create a New Variable (Visual Basic)</span></span>
<span data-ttu-id="85482-103">Creare una variabile con un [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="85482-103">You create a variable with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
### <a name="to-create-a-new-variable"></a><span data-ttu-id="85482-104">Per creare una nuova variabile</span><span class="sxs-lookup"><span data-stu-id="85482-104">To create a new variable</span></span>  
  
1.  <span data-ttu-id="85482-105">Dichiarare la variabile in un `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="85482-105">Declare the variable in a `Dim` statement.</span></span>  
  
    ```  
    Dim newCustomer  
    ```  
  
2.  <span data-ttu-id="85482-106">Includere specifiche per le caratteristiche della variabile, ad esempio [privata](../../../../visual-basic/language-reference/modifiers/private.md), [statico](../../../../visual-basic/language-reference/modifiers/static.md), [ombreggiature](../../../../visual-basic/language-reference/modifiers/shadows.md), o [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="85482-106">Include specifications for the variable's characteristics, such as [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), or [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="85482-107">Per ulteriori informazioni, vedere [caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="85482-107">For more information, see [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
     <span data-ttu-id="85482-108">Non è necessario il `Dim` (parola chiave) se si utilizzano altre parole chiave nella dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="85482-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>  
  
3.  <span data-ttu-id="85482-109">Seguire le specifiche con il nome della variabile, che devono seguire [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] regole e convenzioni.</span><span class="sxs-lookup"><span data-stu-id="85482-109">Follow the specifications with the variable's name, which must follow [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] rules and conventions.</span></span> <span data-ttu-id="85482-110">Per ulteriori informazioni, vedere [nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="85482-110">For more information, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  <span data-ttu-id="85482-111">Dopo il nome con il [come](../../../../visual-basic/language-reference/statements/as-clause.md) clausola per specificare il tipo di dati della variabile.</span><span class="sxs-lookup"><span data-stu-id="85482-111">Follow the name with the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     <span data-ttu-id="85482-112">Se non si specifica il tipo di dati, viene utilizzato il valore predefinito: `Object`.</span><span class="sxs-lookup"><span data-stu-id="85482-112">If you do not specify the data type, it uses the default: `Object`.</span></span>  
  
5.  <span data-ttu-id="85482-113">Seguire il `As` clausola con un segno di uguale (`=`) e seguire il segno di uguale valore iniziale della variabile.</span><span class="sxs-lookup"><span data-stu-id="85482-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>  
  
     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="85482-114">Assegna il valore specificato per la variabile ogni volta che viene eseguito il `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="85482-114"> assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="85482-115">Se non si specifica un valore iniziale, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] assegna il valore iniziale predefinito per il tipo di dati della variabile quando la prima volta inserisce il codice che contiene il `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="85482-115">If you do not specify an initial value, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>  
  
     <span data-ttu-id="85482-116">Se la variabile è un tipo di riferimento, è possibile creare un'istanza della classe, includendo il [nuovo operatore](../../../../visual-basic/language-reference/operators/new-operator.md) (parola chiave) nei `As` clausola.</span><span class="sxs-lookup"><span data-stu-id="85482-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="85482-117">Se non si utilizza `New`, il valore iniziale della variabile è [nulla](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="85482-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="85482-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85482-118">See Also</span></span>  
 <span data-ttu-id="85482-119">[Variabili](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span><span class="sxs-lookup"><span data-stu-id="85482-119">[Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span></span>  
<span data-ttu-id="85482-120"> [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="85482-120"> [Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="85482-121"> [Nomi elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="85482-121"> [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="85482-122"> [Caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="85482-122"> [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span></span>  
<span data-ttu-id="85482-123"> [Tipi di valore e tipi di riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="85482-123"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="85482-124"> [Istruzioni](../../../../visual-basic/language-reference/statements/index.md) </span><span class="sxs-lookup"><span data-stu-id="85482-124"> [Statements](../../../../visual-basic/language-reference/statements/index.md) </span></span>  
<span data-ttu-id="85482-125"> [Inferenza del tipo locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="85482-125"> [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="85482-126"> [Istruzione Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)</span><span class="sxs-lookup"><span data-stu-id="85482-126"> [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)</span></span>

