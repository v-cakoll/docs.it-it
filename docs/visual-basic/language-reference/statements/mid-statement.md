---
title: Istruzione Mid | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.MidB
- vb.Mid
dev_langs:
- VB
helpviewer_keywords:
- substrings, Mid statement
- strings [Visual Basic], substrings
- Mid statement
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e94500c8bd7f2c6351c91ba028c1ad6d8d3dd4c3
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="mid-statement"></a><span data-ttu-id="08c18-102">Istruzione Mid</span><span class="sxs-lookup"><span data-stu-id="08c18-102">Mid Statement</span></span>
<span data-ttu-id="08c18-103">Sostituisce un numero specificato di caratteri in un `String` variabili con i caratteri da un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="08c18-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08c18-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08c18-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="08c18-105">Parti</span><span class="sxs-lookup"><span data-stu-id="08c18-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="08c18-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="08c18-106">Required.</span></span> <span data-ttu-id="08c18-107">Nome di `String` variabile da modificare.</span><span class="sxs-lookup"><span data-stu-id="08c18-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="08c18-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="08c18-108">Required.</span></span> <span data-ttu-id="08c18-109">`Integer`espressione.</span><span class="sxs-lookup"><span data-stu-id="08c18-109">`Integer` expression.</span></span> <span data-ttu-id="08c18-110">Posizione del carattere in `Target` dove inizia la sostituzione di testo.</span><span class="sxs-lookup"><span data-stu-id="08c18-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="08c18-111">`Start`utilizza un indice in base uno.</span><span class="sxs-lookup"><span data-stu-id="08c18-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="08c18-112">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="08c18-112">Optional.</span></span> <span data-ttu-id="08c18-113">`Integer`espressione.</span><span class="sxs-lookup"><span data-stu-id="08c18-113">`Integer` expression.</span></span> <span data-ttu-id="08c18-114">Numero di caratteri da sostituire.</span><span class="sxs-lookup"><span data-stu-id="08c18-114">Number of characters to replace.</span></span> <span data-ttu-id="08c18-115">Se omesso, tutti i `String` viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="08c18-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="08c18-116">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="08c18-116">Required.</span></span> <span data-ttu-id="08c18-117">`String`espressione che sostituisce una parte di `Target`.</span><span class="sxs-lookup"><span data-stu-id="08c18-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="08c18-118">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="08c18-118">Exceptions</span></span>  
  
|<span data-ttu-id="08c18-119">Tipo di eccezione</span><span class="sxs-lookup"><span data-stu-id="08c18-119">Exception type</span></span>|<span data-ttu-id="08c18-120">Condizione</span><span class="sxs-lookup"><span data-stu-id="08c18-120">Condition</span></span>|  
|--------------------|---------------|  
|<span data-ttu-id="08c18-121"><xref:System.ArgumentException></xref:System.ArgumentException></span><span class="sxs-lookup"><span data-stu-id="08c18-121"><xref:System.ArgumentException></span></span>|<span data-ttu-id="08c18-122">`Start`<= 0="" or=""></=>`Length`< 0.></ 0.></span><span class="sxs-lookup"><span data-stu-id="08c18-122">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08c18-123">Note</span><span class="sxs-lookup"><span data-stu-id="08c18-123">Remarks</span></span>  
 <span data-ttu-id="08c18-124">Il numero di caratteri sostituiti è sempre minore o uguale al numero di caratteri in `Target`.</span><span class="sxs-lookup"><span data-stu-id="08c18-124">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="08c18-125">Visual Basic è un <xref:Microsoft.VisualBasic.Strings.Mid%2A>(funzione) e un `Mid` istruzione.</xref:Microsoft.VisualBasic.Strings.Mid%2A></span><span class="sxs-lookup"><span data-stu-id="08c18-125">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="08c18-126">Questi elementi entrambi operano su un numero specificato di caratteri in una stringa, ma il `Mid` funzione restituisce i caratteri, mentre il `Mid` istruzione sostituisce i caratteri.</span><span class="sxs-lookup"><span data-stu-id="08c18-126">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="08c18-127">Per ulteriori informazioni, vedere <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</xref:Microsoft.VisualBasic.Strings.Mid%2A></span><span class="sxs-lookup"><span data-stu-id="08c18-127">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08c18-128">Il `MidB` istruzione delle versioni precedenti di Visual Basic sostituisce una sottostringa in byte, anziché in caratteri.</span><span class="sxs-lookup"><span data-stu-id="08c18-128">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="08c18-129">Viene utilizzato principalmente per la conversione di stringhe nelle applicazioni di double byte character set (DBCS).</span><span class="sxs-lookup"><span data-stu-id="08c18-129">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="08c18-130">Tutte le stringhe di Visual Basic sono in formato Unicode, e `MidB` non è più supportata.</span><span class="sxs-lookup"><span data-stu-id="08c18-130">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08c18-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="08c18-131">Example</span></span>  
 <span data-ttu-id="08c18-132">Questo esempio viene utilizzato il `Mid` istruzione per sostituire un numero specificato di caratteri in una variabile di stringa con caratteri da un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="08c18-132">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 <span data-ttu-id="08c18-133">[!code-vb[VbVbalrStrings n.&5;](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="08c18-133">[!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08c18-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="08c18-134">Requirements</span></span>  
 <span data-ttu-id="08c18-135">**Namespace:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="08c18-135">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="08c18-136">**Modulo:**`Strings`</span><span class="sxs-lookup"><span data-stu-id="08c18-136">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="08c18-137">**Assembly:**[!INCLUDE[vbprvbruntime](../../../visual-basic/language-reference/objects/includes/vbprvbruntime_md.md)]</span><span class="sxs-lookup"><span data-stu-id="08c18-137">**Assembly:** [!INCLUDE[vbprvbruntime](../../../visual-basic/language-reference/objects/includes/vbprvbruntime_md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08c18-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08c18-138">See Also</span></span>  
 <span data-ttu-id="08c18-139"><xref:Microsoft.VisualBasic.Strings.Mid%2A></xref:Microsoft.VisualBasic.Strings.Mid%2A></span><span class="sxs-lookup"><span data-stu-id="08c18-139"><xref:Microsoft.VisualBasic.Strings.Mid%2A></span></span>   
<span data-ttu-id="08c18-140"> [Stringhe](../../../visual-basic/programming-guide/language-features/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="08c18-140"> [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md) </span></span>  
<span data-ttu-id="08c18-141"> [Introduzione alle stringhe in Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)</span><span class="sxs-lookup"><span data-stu-id="08c18-141"> [Introduction to Strings in Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)</span></span>
