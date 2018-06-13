---
title: Istruzione Mid
ms.date: 07/20/2015
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
ms.openlocfilehash: 90b805df902dcdfebe85421583dd54e9af04bec9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602265"
---
# <a name="mid-statement"></a><span data-ttu-id="8d346-102">Istruzione Mid</span><span class="sxs-lookup"><span data-stu-id="8d346-102">Mid Statement</span></span>
<span data-ttu-id="8d346-103">Sostituisce un numero specificato di caratteri in un `String` variabili con i caratteri da un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="8d346-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d346-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8d346-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="8d346-105">Parti</span><span class="sxs-lookup"><span data-stu-id="8d346-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="8d346-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8d346-106">Required.</span></span> <span data-ttu-id="8d346-107">Nome di `String` variabile da modificare.</span><span class="sxs-lookup"><span data-stu-id="8d346-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="8d346-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8d346-108">Required.</span></span> <span data-ttu-id="8d346-109">`Integer` Espressione.</span><span class="sxs-lookup"><span data-stu-id="8d346-109">`Integer` expression.</span></span> <span data-ttu-id="8d346-110">Posizione del carattere in `Target` in cui inizia la sostituzione di testo.</span><span class="sxs-lookup"><span data-stu-id="8d346-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="8d346-111">`Start` viene utilizzato un indice in base uno.</span><span class="sxs-lookup"><span data-stu-id="8d346-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="8d346-112">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8d346-112">Optional.</span></span> <span data-ttu-id="8d346-113">`Integer` Espressione.</span><span class="sxs-lookup"><span data-stu-id="8d346-113">`Integer` expression.</span></span> <span data-ttu-id="8d346-114">Numero di caratteri da sostituire.</span><span class="sxs-lookup"><span data-stu-id="8d346-114">Number of characters to replace.</span></span> <span data-ttu-id="8d346-115">Se omesso, tutti i `String` viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="8d346-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="8d346-116">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8d346-116">Required.</span></span> <span data-ttu-id="8d346-117">`String` espressione che sostituisce parte di `Target`.</span><span class="sxs-lookup"><span data-stu-id="8d346-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="8d346-118">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="8d346-118">Exceptions</span></span>  
  
|<span data-ttu-id="8d346-119">Tipo di eccezione</span><span class="sxs-lookup"><span data-stu-id="8d346-119">Exception type</span></span>|<span data-ttu-id="8d346-120">Condizione</span><span class="sxs-lookup"><span data-stu-id="8d346-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="8d346-121">`Start` < = 0 o `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="8d346-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d346-122">Note</span><span class="sxs-lookup"><span data-stu-id="8d346-122">Remarks</span></span>  
 <span data-ttu-id="8d346-123">Il numero di caratteri sostituiti è sempre minore o uguale al numero di caratteri in `Target`.</span><span class="sxs-lookup"><span data-stu-id="8d346-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="8d346-124">Visual Basic è disponibile un <xref:Microsoft.VisualBasic.Strings.Mid%2A> (funzione) e un `Mid` istruzione.</span><span class="sxs-lookup"><span data-stu-id="8d346-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="8d346-125">Questi elementi entrambi funzionano su un numero specificato di caratteri in una stringa, ma la `Mid` funzione restituisce i caratteri, mentre il `Mid` istruzione sostituisce i caratteri.</span><span class="sxs-lookup"><span data-stu-id="8d346-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="8d346-126">Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="8d346-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d346-127">Il `MidB` istruzione delle versioni precedenti di Visual Basic sostituisce una sottostringa in byte, anziché come caratteri.</span><span class="sxs-lookup"><span data-stu-id="8d346-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="8d346-128">Viene utilizzato principalmente per la conversione di stringhe nelle applicazioni di double byte character set (DBCS).</span><span class="sxs-lookup"><span data-stu-id="8d346-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="8d346-129">Tutte le stringhe di Visual Basic sono in formato Unicode, e `MidB` non è più supportata.</span><span class="sxs-lookup"><span data-stu-id="8d346-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d346-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="8d346-130">Example</span></span>  
 <span data-ttu-id="8d346-131">Questo esempio viene utilizzato il `Mid` istruzione per sostituire un numero specificato di caratteri in una variabile di stringa con caratteri di un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="8d346-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="8d346-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8d346-132">Requirements</span></span>  
 <span data-ttu-id="8d346-133">**Namespace:** [VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="8d346-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="8d346-134">**Modulo:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="8d346-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="8d346-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d346-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d346-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d346-136">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 [<span data-ttu-id="8d346-137">Stringhe</span><span class="sxs-lookup"><span data-stu-id="8d346-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="8d346-138">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8d346-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
