---
title: Tipi di dati in Visual Basic
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- data types [Visual Basic], declaring
- typing
- data types [Visual Basic]
- Visual Basic code, data types
- data types [Visual Basic], improving speed with
ms.assetid: 5e1b9aaf-c7ca-4b29-9b22-0e82ed8e85e2
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8b90a5e58d135a3769761ca431fd0c05f79e045f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="data-types-in-visual-basic"></a><span data-ttu-id="c27a3-102">Tipi di dati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c27a3-102">Data Types in Visual Basic</span></span>
<span data-ttu-id="c27a3-103">Il *tipo di dati* di un elemento di programmazione indica la tipologia di dati che può contenere e la modalità di archiviazione di tali dati.</span><span class="sxs-lookup"><span data-stu-id="c27a3-103">The *data type* of a programming element refers to what kind of data it can hold and how it stores that data.</span></span> <span data-ttu-id="c27a3-104">I tipi di dati si applicano a tutti i valori che possono essere archiviati nella memoria del computer o partecipano alla valutazione di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="c27a3-104">Data types apply to all values that can be stored in computer memory or participate in the evaluation of an expression.</span></span> <span data-ttu-id="c27a3-105">Ogni variabile, valore letterale, costante, enumerazione, proprietà, parametro di routine, argomento di routine e valore restituito di routine ha un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="c27a3-105">Every variable, literal, constant, enumeration, property, procedure parameter, procedure argument, and procedure return value has a data type.</span></span>  
  
## <a name="declared-data-types"></a><span data-ttu-id="c27a3-106">Tipi di dati dichiarati</span><span class="sxs-lookup"><span data-stu-id="c27a3-106">Declared Data Types</span></span>  
 <span data-ttu-id="c27a3-107">Un elemento di programmazione viene definito con un'istruzione di dichiarazione e il relativo tipo di dati viene specificato con la clausola `As`.</span><span class="sxs-lookup"><span data-stu-id="c27a3-107">You define a programming element with a declaration statement, and you specify its data type with the `As` clause.</span></span> <span data-ttu-id="c27a3-108">La tabella seguente mostra le istruzioni usate per dichiarare i vari elementi.</span><span class="sxs-lookup"><span data-stu-id="c27a3-108">The following table shows the statements you use to declare various elements.</span></span>  
  
|<span data-ttu-id="c27a3-109">Elemento di programmazione</span><span class="sxs-lookup"><span data-stu-id="c27a3-109">Programming element</span></span>|<span data-ttu-id="c27a3-110">Dichiarazione del tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c27a3-110">Data type declaration</span></span>|  
|-------------------------|---------------------------|  
|<span data-ttu-id="c27a3-111">Variabile</span><span class="sxs-lookup"><span data-stu-id="c27a3-111">Variable</span></span>|<span data-ttu-id="c27a3-112">In un'[istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="c27a3-112">In a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)</span></span><br /><br /> <span data-ttu-id="c27a3-113">`Dim`   `amount As Double`</span><span class="sxs-lookup"><span data-stu-id="c27a3-113">`Dim`   `amount As Double`</span></span><br /><br /> <span data-ttu-id="c27a3-114">`Static`   `yourName As String`</span><span class="sxs-lookup"><span data-stu-id="c27a3-114">`Static`   `yourName As String`</span></span><br /><br /> <span data-ttu-id="c27a3-115">`Public`   `billsPaid As Decimal = 0`</span><span class="sxs-lookup"><span data-stu-id="c27a3-115">`Public`   `billsPaid As Decimal = 0`</span></span>|  
|<span data-ttu-id="c27a3-116">Literal</span><span class="sxs-lookup"><span data-stu-id="c27a3-116">Literal</span></span>|<span data-ttu-id="c27a3-117">Con un carattere di tipo letterale. Vedere "Caratteri di tipo letterale" in [Caratteri tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span><span class="sxs-lookup"><span data-stu-id="c27a3-117">With a literal type character; see "Literal Type Characters" in [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span></span><br /><br /> <span data-ttu-id="c27a3-118">`Dim searchChar As Char = "."`  `C`</span><span class="sxs-lookup"><span data-stu-id="c27a3-118">`Dim searchChar As Char = "."`  `C`</span></span>|  
|<span data-ttu-id="c27a3-119">Costante</span><span class="sxs-lookup"><span data-stu-id="c27a3-119">Constant</span></span>|<span data-ttu-id="c27a3-120">In un'[istruzione Const](../../../../visual-basic/language-reference/statements/const-statement.md)</span><span class="sxs-lookup"><span data-stu-id="c27a3-120">In a [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md)</span></span><br /><br /> <span data-ttu-id="c27a3-121">`Const`   `modulus As Single = 4.17825F`</span><span class="sxs-lookup"><span data-stu-id="c27a3-121">`Const`   `modulus As Single = 4.17825F`</span></span>|  
|<span data-ttu-id="c27a3-122">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="c27a3-122">Enumeration</span></span>|<span data-ttu-id="c27a3-123">In un'[istruzione Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)</span><span class="sxs-lookup"><span data-stu-id="c27a3-123">In an [Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md)</span></span><br /><br /> <span data-ttu-id="c27a3-124">`Public`   `Enum`   `colors`</span><span class="sxs-lookup"><span data-stu-id="c27a3-124">`Public`   `Enum`   `colors`</span></span>|  
|<span data-ttu-id="c27a3-125">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c27a3-125">Property</span></span>|<span data-ttu-id="c27a3-126">In un'[istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md)</span><span class="sxs-lookup"><span data-stu-id="c27a3-126">In a [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)</span></span><br /><br /> <span data-ttu-id="c27a3-127">`Property`   `region() As String`</span><span class="sxs-lookup"><span data-stu-id="c27a3-127">`Property`   `region() As String`</span></span>|  
|<span data-ttu-id="c27a3-128">Parametro di routine</span><span class="sxs-lookup"><span data-stu-id="c27a3-128">Procedure parameter</span></span>|<span data-ttu-id="c27a3-129">In un'[istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md), un'[istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md) o un'[istruzione Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)</span><span class="sxs-lookup"><span data-stu-id="c27a3-129">In a [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md), [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md), or [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)</span></span><br /><br /> <span data-ttu-id="c27a3-130">`Sub addSale(ByVal`   `amount`   `As Double)`</span><span class="sxs-lookup"><span data-stu-id="c27a3-130">`Sub addSale(ByVal`   `amount`   `As Double)`</span></span>|  
|<span data-ttu-id="c27a3-131">Argomento di routine</span><span class="sxs-lookup"><span data-stu-id="c27a3-131">Procedure argument</span></span>|<span data-ttu-id="c27a3-132">Nel codice chiamante; ogni argomento è un elemento di programmazione già dichiarato o un'espressione che contiene elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="c27a3-132">In the calling code; each argument is a programming element that has already been declared, or an expression containing declared elements</span></span><br /><br /> <span data-ttu-id="c27a3-133">`subString = Left(`  `inputString`  `,`   `5`  `)`</span><span class="sxs-lookup"><span data-stu-id="c27a3-133">`subString = Left(`  `inputString`  `,`   `5`  `)`</span></span>|  
|<span data-ttu-id="c27a3-134">Valore restituito di routine</span><span class="sxs-lookup"><span data-stu-id="c27a3-134">Procedure return value</span></span>|<span data-ttu-id="c27a3-135">In un'[istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md) o un'[istruzione Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)</span><span class="sxs-lookup"><span data-stu-id="c27a3-135">In a [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) or [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)</span></span><br /><br /> <span data-ttu-id="c27a3-136">`Function convert(ByVal b As Byte)`   `As String`</span><span class="sxs-lookup"><span data-stu-id="c27a3-136">`Function convert(ByVal b As Byte)`   `As String`</span></span>|  
  
 <span data-ttu-id="c27a3-137">Per un elenco dei tipi di dati di Visual Basic, vedere [Tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span><span class="sxs-lookup"><span data-stu-id="c27a3-137">For a list of Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c27a3-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c27a3-138">See Also</span></span>  
 <span data-ttu-id="c27a3-139">[Caratteri tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span><span class="sxs-lookup"><span data-stu-id="c27a3-139">[Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span></span>  
 <span data-ttu-id="c27a3-140">[Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="c27a3-140">[Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
 <span data-ttu-id="c27a3-141">[Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="c27a3-141">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span></span>  
 <span data-ttu-id="c27a3-142">[Tipi generici in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="c27a3-142">[Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
 <span data-ttu-id="c27a3-143">[Tipi valore e tipi di riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="c27a3-143">[Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
 <span data-ttu-id="c27a3-144">[Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="c27a3-144">[Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
 <span data-ttu-id="c27a3-145">[Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span><span class="sxs-lookup"><span data-stu-id="c27a3-145">[Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span></span>  
 <span data-ttu-id="c27a3-146">[Tuple](tuples.md)   </span><span class="sxs-lookup"><span data-stu-id="c27a3-146">[Tuples](tuples.md)   </span></span>  
 <span data-ttu-id="c27a3-147">[Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="c27a3-147">[Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
 <span data-ttu-id="c27a3-148">[Riepilogo dei tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="c27a3-148">[Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
 [<span data-ttu-id="c27a3-149">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="c27a3-149">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

