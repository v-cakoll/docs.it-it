---
title: Istruzione Mid (Visual Basic)
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
ms.openlocfilehash: 212ce1f06a01c39acbce43d8d069dae3526b1b4d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963542"
---
# <a name="mid-statement"></a><span data-ttu-id="58f00-102">Istruzione Mid</span><span class="sxs-lookup"><span data-stu-id="58f00-102">Mid Statement</span></span>
<span data-ttu-id="58f00-103">Sostituisce un numero specificato di caratteri in una `String` variabile con caratteri di un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="58f00-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58f00-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58f00-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="58f00-105">Parti</span><span class="sxs-lookup"><span data-stu-id="58f00-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="58f00-106">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="58f00-106">Required.</span></span> <span data-ttu-id="58f00-107">Nome della `String` variabile da modificare.</span><span class="sxs-lookup"><span data-stu-id="58f00-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="58f00-108">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="58f00-108">Required.</span></span> <span data-ttu-id="58f00-109">`Integer`espressione.</span><span class="sxs-lookup"><span data-stu-id="58f00-109">`Integer` expression.</span></span> <span data-ttu-id="58f00-110">Posizione del carattere `Target` in in cui inizia la sostituzione del testo.</span><span class="sxs-lookup"><span data-stu-id="58f00-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="58f00-111">`Start`Usa un indice in base uno.</span><span class="sxs-lookup"><span data-stu-id="58f00-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="58f00-112">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58f00-112">Optional.</span></span> <span data-ttu-id="58f00-113">`Integer`espressione.</span><span class="sxs-lookup"><span data-stu-id="58f00-113">`Integer` expression.</span></span> <span data-ttu-id="58f00-114">Numero di caratteri da sostituire.</span><span class="sxs-lookup"><span data-stu-id="58f00-114">Number of characters to replace.</span></span> <span data-ttu-id="58f00-115">Se omesso, `String` viene utilizzato tutto.</span><span class="sxs-lookup"><span data-stu-id="58f00-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="58f00-116">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="58f00-116">Required.</span></span> <span data-ttu-id="58f00-117">`String`espressione che sostituisce parte di `Target`.</span><span class="sxs-lookup"><span data-stu-id="58f00-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="58f00-118">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="58f00-118">Exceptions</span></span>  
  
|<span data-ttu-id="58f00-119">Tipo di eccezione</span><span class="sxs-lookup"><span data-stu-id="58f00-119">Exception type</span></span>|<span data-ttu-id="58f00-120">Condizione</span><span class="sxs-lookup"><span data-stu-id="58f00-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="58f00-121">`Start`< = 0 o `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="58f00-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58f00-122">Note</span><span class="sxs-lookup"><span data-stu-id="58f00-122">Remarks</span></span>  
 <span data-ttu-id="58f00-123">Il numero di caratteri sostituiti è sempre minore o uguale al numero di caratteri in `Target`.</span><span class="sxs-lookup"><span data-stu-id="58f00-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="58f00-124">Visual Basic dispone di <xref:Microsoft.VisualBasic.Strings.Mid%2A> una funzione e `Mid` di un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="58f00-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="58f00-125">Questi elementi operano entrambi su un numero specificato di caratteri in una stringa, ma `Mid` la funzione restituisce i caratteri mentre `Mid` l'istruzione sostituisce i caratteri.</span><span class="sxs-lookup"><span data-stu-id="58f00-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="58f00-126">Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="58f00-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="58f00-127">L' `MidB` istruzione di versioni precedenti di Visual Basic sostituisce una sottostringa in byte, anziché caratteri.</span><span class="sxs-lookup"><span data-stu-id="58f00-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="58f00-128">Viene utilizzato principalmente per la conversione di stringhe in applicazioni DBCS (Double-byte character set).</span><span class="sxs-lookup"><span data-stu-id="58f00-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="58f00-129">Tutte le stringhe di Visual Basic sono in formato `MidB` Unicode e non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="58f00-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58f00-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="58f00-130">Example</span></span>  
 <span data-ttu-id="58f00-131">In questo esempio viene `Mid` utilizzata l'istruzione per sostituire un numero specificato di caratteri in una variabile di stringa con caratteri di un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="58f00-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="58f00-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58f00-132">Requirements</span></span>  
 <span data-ttu-id="58f00-133">**Spazio dei nomi:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="58f00-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="58f00-134">**Modulo:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="58f00-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="58f00-135">**Assembly** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="58f00-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58f00-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58f00-136">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="58f00-137">Stringhe</span><span class="sxs-lookup"><span data-stu-id="58f00-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="58f00-138">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="58f00-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
