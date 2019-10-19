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
ms.openlocfilehash: ea22af2eb896542bfc329e087101608e08c45107
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581482"
---
# <a name="mid-statement"></a><span data-ttu-id="c520e-102">Istruzione Mid</span><span class="sxs-lookup"><span data-stu-id="c520e-102">Mid Statement</span></span>
<span data-ttu-id="c520e-103">Sostituisce un numero specificato di caratteri in una variabile `String` con caratteri di un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="c520e-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c520e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c520e-104">Syntax</span></span>  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="c520e-105">Parti</span><span class="sxs-lookup"><span data-stu-id="c520e-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="c520e-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c520e-106">Required.</span></span> <span data-ttu-id="c520e-107">Nome della variabile `String` da modificare.</span><span class="sxs-lookup"><span data-stu-id="c520e-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="c520e-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c520e-108">Required.</span></span> <span data-ttu-id="c520e-109">espressione `Integer`.</span><span class="sxs-lookup"><span data-stu-id="c520e-109">`Integer` expression.</span></span> <span data-ttu-id="c520e-110">Posizione del carattere in `Target` in cui inizia la sostituzione del testo.</span><span class="sxs-lookup"><span data-stu-id="c520e-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="c520e-111">`Start` utilizza un indice in base uno.</span><span class="sxs-lookup"><span data-stu-id="c520e-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="c520e-112">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c520e-112">Optional.</span></span> <span data-ttu-id="c520e-113">espressione `Integer`.</span><span class="sxs-lookup"><span data-stu-id="c520e-113">`Integer` expression.</span></span> <span data-ttu-id="c520e-114">Numero di caratteri da sostituire.</span><span class="sxs-lookup"><span data-stu-id="c520e-114">Number of characters to replace.</span></span> <span data-ttu-id="c520e-115">Se omesso, viene utilizzato tutto `String`.</span><span class="sxs-lookup"><span data-stu-id="c520e-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="c520e-116">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c520e-116">Required.</span></span> <span data-ttu-id="c520e-117">espressione `String` che sostituisce parte del `Target`.</span><span class="sxs-lookup"><span data-stu-id="c520e-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="c520e-118">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="c520e-118">Exceptions</span></span>  
  
|<span data-ttu-id="c520e-119">Tipo di eccezione</span><span class="sxs-lookup"><span data-stu-id="c520e-119">Exception type</span></span>|<span data-ttu-id="c520e-120">Condizione</span><span class="sxs-lookup"><span data-stu-id="c520e-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="c520e-121">`Start` < = 0 o `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="c520e-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c520e-122">Note</span><span class="sxs-lookup"><span data-stu-id="c520e-122">Remarks</span></span>  
 <span data-ttu-id="c520e-123">Il numero di caratteri sostituiti è sempre minore o uguale al numero di caratteri in `Target`.</span><span class="sxs-lookup"><span data-stu-id="c520e-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="c520e-124">Visual Basic dispone di una funzione <xref:Microsoft.VisualBasic.Strings.Mid%2A> e di un'istruzione `Mid`.</span><span class="sxs-lookup"><span data-stu-id="c520e-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="c520e-125">Questi elementi operano entrambi su un numero specificato di caratteri in una stringa, ma la funzione `Mid` restituisce i caratteri mentre l'istruzione `Mid` sostituisce i caratteri.</span><span class="sxs-lookup"><span data-stu-id="c520e-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="c520e-126">Per ulteriori informazioni, vedere <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="c520e-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c520e-127">L'istruzione `MidB` delle versioni precedenti di Visual Basic sostituisce una sottostringa in byte, anziché caratteri.</span><span class="sxs-lookup"><span data-stu-id="c520e-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="c520e-128">Viene utilizzato principalmente per la conversione di stringhe in applicazioni DBCS (Double-byte character set).</span><span class="sxs-lookup"><span data-stu-id="c520e-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="c520e-129">Tutte le stringhe di Visual Basic sono in formato Unicode e `MidB` non è più supportata.</span><span class="sxs-lookup"><span data-stu-id="c520e-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c520e-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="c520e-130">Example</span></span>  
 <span data-ttu-id="c520e-131">In questo esempio viene utilizzata l'istruzione `Mid` per sostituire un numero specificato di caratteri in una variabile di stringa con caratteri di un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="c520e-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="c520e-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c520e-132">Requirements</span></span>  
 <span data-ttu-id="c520e-133">**Spazio dei nomi:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="c520e-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="c520e-134">**Modulo:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="c520e-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="c520e-135">**Assembly:** Libreria di runtime Visual Basic (in Microsoft. VisualBasic. dll)</span><span class="sxs-lookup"><span data-stu-id="c520e-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c520e-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c520e-136">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="c520e-137">Stringhe</span><span class="sxs-lookup"><span data-stu-id="c520e-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="c520e-138">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c520e-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
