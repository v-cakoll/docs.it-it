---
title: 'Procedura: forzare il passaggio di un argomento per valore'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
ms.openlocfilehash: 48f7d7afebd76916cba11459532d89d71871c79b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387967"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="15424-102">Procedura: forzare il passaggio di un argomento per valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15424-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="15424-103">La dichiarazione di routine determina il meccanismo di passaggio.</span><span class="sxs-lookup"><span data-stu-id="15424-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="15424-104">Se un parametro è dichiarato [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic prevede di passare l'argomento corrispondente per riferimento.</span><span class="sxs-lookup"><span data-stu-id="15424-104">If a parameter is declared [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="15424-105">Ciò consente alla routine di modificare il valore dell'elemento di programmazione sottostante l'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="15424-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="15424-106">Se si desidera proteggere l'elemento sottostante da tale modifica, è possibile eseguire l'override del `ByRef` meccanismo di passaggio nella chiamata di procedura racchiudendo tra parentesi il nome dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="15424-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="15424-107">Queste parentesi si aggiungono alle parentesi che racchiudono l'elenco di argomenti nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="15424-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="15424-108">Il codice chiamante non può eseguire l'override di un meccanismo [ByVal](../../../language-reference/modifiers/byval.md) .</span><span class="sxs-lookup"><span data-stu-id="15424-108">The calling code cannot override a [ByVal](../../../language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="15424-109">Per forzare il passaggio di un argomento per valore</span><span class="sxs-lookup"><span data-stu-id="15424-109">To force an argument to be passed by value</span></span>  
  
- <span data-ttu-id="15424-110">Se il parametro corrispondente viene dichiarato `ByVal` nella procedura, non è necessario eseguire ulteriori passaggi.</span><span class="sxs-lookup"><span data-stu-id="15424-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> <span data-ttu-id="15424-111">Visual Basic prevede di passare l'argomento per valore.</span><span class="sxs-lookup"><span data-stu-id="15424-111">Visual Basic already expects to pass the argument by value.</span></span>  
  
- <span data-ttu-id="15424-112">Se il parametro corrispondente viene dichiarato `ByRef` nella procedura, racchiudere l'argomento tra parentesi nella chiamata di procedura.</span><span class="sxs-lookup"><span data-stu-id="15424-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15424-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="15424-113">Example</span></span>  
 <span data-ttu-id="15424-114">Nell'esempio seguente viene eseguito l'override di una `ByRef` dichiarazione di parametro.</span><span class="sxs-lookup"><span data-stu-id="15424-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="15424-115">Nella chiamata che forza `ByVal` , prendere nota dei due livelli di parentesi.</span><span class="sxs-lookup"><span data-stu-id="15424-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 <span data-ttu-id="15424-116">Quando `str` è racchiuso tra parentesi aggiuntive all'interno dell'elenco di argomenti, la `setNewString` procedura non può modificare il valore nel codice chiamante e `MsgBox` Visualizza "non può essere sostituito se passato ByVal".</span><span class="sxs-lookup"><span data-stu-id="15424-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="15424-117">Quando `str` non è racchiuso tra parentesi aggiuntive, la procedura può modificarla e `MsgBox` Visualizza "questo è un nuovo valore per l'argomento inString".</span><span class="sxs-lookup"><span data-stu-id="15424-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="15424-118">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="15424-118">Compile the code</span></span>  
 <span data-ttu-id="15424-119">Quando si passa una variabile in base al riferimento, è necessario usare la `ByRef` parola chiave per specificare questo meccanismo.</span><span class="sxs-lookup"><span data-stu-id="15424-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="15424-120">Il valore predefinito in Visual Basic consiste nel passare gli argomenti per valore.</span><span class="sxs-lookup"><span data-stu-id="15424-120">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="15424-121">Tuttavia, è consigliabile includere la parola chiave [ByVal](../../../language-reference/modifiers/byval.md) o [ByRef](../../../language-reference/modifiers/byref.md) con tutti i parametri dichiarati.</span><span class="sxs-lookup"><span data-stu-id="15424-121">However, it is good programming practice to include either the [ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="15424-122">Questo rende il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="15424-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="15424-123">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="15424-123">Robust Programming</span></span>  
 <span data-ttu-id="15424-124">Se una routine dichiara un parametro [ByRef](../../../language-reference/modifiers/byref.md), l'esecuzione corretta del codice potrebbe dipendere dalla possibilità di modificare l'elemento sottostante nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="15424-124">If a procedure declares a parameter [ByRef](../../../language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="15424-125">Se il codice chiamante esegue l'override di questo meccanismo chiamante racchiudendo l'argomento tra parentesi o se passa un argomento non modificabile, la procedura non può modificare l'elemento sottostante.</span><span class="sxs-lookup"><span data-stu-id="15424-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="15424-126">Questo potrebbe produrre risultati imprevisti nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="15424-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="15424-127">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="15424-127">.NET Framework Security</span></span>  
 <span data-ttu-id="15424-128">Esiste sempre un potenziale rischio nel consentire a una procedura di modificare il valore sottostante un argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="15424-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="15424-129">Verificare che questo valore sia stato modificato e che sia stato preparato per verificarne la validità prima di usarlo.</span><span class="sxs-lookup"><span data-stu-id="15424-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15424-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15424-130">See also</span></span>

- [<span data-ttu-id="15424-131">Procedure</span><span class="sxs-lookup"><span data-stu-id="15424-131">Procedures</span></span>](./index.md)
- [<span data-ttu-id="15424-132">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="15424-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="15424-133">Procedura: passare argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="15424-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="15424-134">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="15424-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="15424-135">Differenze tra argomenti modificabili e non modificabili</span><span class="sxs-lookup"><span data-stu-id="15424-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="15424-136">Differenze tra il passaggio di un argomento per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="15424-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="15424-137">Procedura: cambiare il valore di un argomento di routine</span><span class="sxs-lookup"><span data-stu-id="15424-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="15424-138">Procedura: impedire la modifica del valore di un argomento di una routine</span><span class="sxs-lookup"><span data-stu-id="15424-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="15424-139">Passaggio di argomenti in base alla posizione e al nome</span><span class="sxs-lookup"><span data-stu-id="15424-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="15424-140">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="15424-140">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
