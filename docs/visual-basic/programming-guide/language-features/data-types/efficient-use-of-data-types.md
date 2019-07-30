---
title: Utilizzo efficiente dei tipi di dati (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
ms.openlocfilehash: 68371a9f8d4dcc5d0a2b67955d5e88943a83b085
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631113"
---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="6736d-102">Utilizzo efficiente dei tipi di dati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6736d-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="6736d-103">Alle variabili e alle variabili non dichiarate dichiarate senza `Object` un tipo di dati viene assegnato il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="6736d-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="6736d-104">In questo modo è facile scrivere rapidamente i programmi, ma è possibile che vengano eseguiti più lentamente.</span><span class="sxs-lookup"><span data-stu-id="6736d-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>

## <a name="strong-typing"></a><span data-ttu-id="6736d-105">Tipizzazione forte</span><span class="sxs-lookup"><span data-stu-id="6736d-105">Strong Typing</span></span>
 <span data-ttu-id="6736d-106">Specificare i tipi di dati per tutte le variabili è noto come tipizzazione *forte*.</span><span class="sxs-lookup"><span data-stu-id="6736d-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="6736d-107">L'uso di tipizzazione forte presenta diversi vantaggi:</span><span class="sxs-lookup"><span data-stu-id="6736d-107">Using strong typing has several advantages:</span></span>

- <span data-ttu-id="6736d-108">Abilita il supporto IntelliSense per le variabili.</span><span class="sxs-lookup"><span data-stu-id="6736d-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="6736d-109">In questo modo è possibile visualizzare le relative proprietà e altri membri durante la digitazione nel codice.</span><span class="sxs-lookup"><span data-stu-id="6736d-109">This allows you to see their properties and other members as you type in the code.</span></span>

- <span data-ttu-id="6736d-110">Sfrutta i vantaggi del controllo dei tipi del compilatore.</span><span class="sxs-lookup"><span data-stu-id="6736d-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="6736d-111">Questa operazione intercetta le istruzioni che possono avere esito negativo in fase di esecuzione a causa di errori come l'overflow.</span><span class="sxs-lookup"><span data-stu-id="6736d-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="6736d-112">Rileva inoltre le chiamate ai metodi su oggetti che non li supportano.</span><span class="sxs-lookup"><span data-stu-id="6736d-112">It also catches calls to methods on objects that do not support them.</span></span>

- <span data-ttu-id="6736d-113">Questo comporta un'esecuzione più rapida del codice.</span><span class="sxs-lookup"><span data-stu-id="6736d-113">It results in faster execution of your code.</span></span>

## <a name="most-efficient-data-types"></a><span data-ttu-id="6736d-114">Tipi di dati più efficienti</span><span class="sxs-lookup"><span data-stu-id="6736d-114">Most Efficient Data Types</span></span>
 <span data-ttu-id="6736d-115">Per le variabili che non contengono mai frazioni, i tipi di dati integrali sono più efficienti dei tipi non integrali.</span><span class="sxs-lookup"><span data-stu-id="6736d-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="6736d-116">In Visual Basic `Integer` e `UInteger` sono i tipi numerici più efficienti.</span><span class="sxs-lookup"><span data-stu-id="6736d-116">In Visual Basic, `Integer` and `UInteger` are the most efficient numeric types.</span></span>

 <span data-ttu-id="6736d-117">Per i numeri frazionari, `Double` è il tipo di dati più efficiente, perché i processori sulle piattaforme correnti eseguono operazioni a virgola mobile con precisione doppia.</span><span class="sxs-lookup"><span data-stu-id="6736d-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="6736d-118">Tuttavia, le operazioni `Double` con non sono altrettanto veloci dei tipi integrali, `Integer`ad esempio.</span><span class="sxs-lookup"><span data-stu-id="6736d-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>

## <a name="specifying-data-type"></a><span data-ttu-id="6736d-119">Specifica del tipo di dati</span><span class="sxs-lookup"><span data-stu-id="6736d-119">Specifying Data Type</span></span>
 <span data-ttu-id="6736d-120">Utilizzare l' [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) per dichiarare una variabile di un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="6736d-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="6736d-121">È possibile specificare contemporaneamente il relativo livello di accesso tramite la parola chiave [public](../../../../visual-basic/language-reference/modifiers/public.md), [protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)o [private](../../../../visual-basic/language-reference/modifiers/private.md) , come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6736d-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>

```vb
Private x As Double
Protected s As String
```

## <a name="character-conversion"></a><span data-ttu-id="6736d-122">Conversione di caratteri</span><span class="sxs-lookup"><span data-stu-id="6736d-122">Character Conversion</span></span>
 <span data-ttu-id="6736d-123">Le `AscW` funzioni `ChrW` e operano in Unicode.</span><span class="sxs-lookup"><span data-stu-id="6736d-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="6736d-124">È consigliabile usarli in modo preferenziale `Chr`per e, che devono essere `Asc` convertiti all'interno e all'esterno di Unicode.</span><span class="sxs-lookup"><span data-stu-id="6736d-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>

## <a name="see-also"></a><span data-ttu-id="6736d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6736d-125">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="6736d-126">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="6736d-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="6736d-127">Tipi di dati numerici</span><span class="sxs-lookup"><span data-stu-id="6736d-127">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [<span data-ttu-id="6736d-128">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="6736d-128">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="6736d-129">Utilizzo di IntelliSense</span><span class="sxs-lookup"><span data-stu-id="6736d-129">Using IntelliSense</span></span>](/visualstudio/ide/using-intellisense)
