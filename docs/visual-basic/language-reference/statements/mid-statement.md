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
ms.openlocfilehash: ff3b908e2805f4d51463a82d90f2305efc9f1608
ms.sourcegitcommit: c4dfe37032c64a1fba2cc3d5947550d79f95e3b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041575"
---
# <a name="mid-statement"></a><span data-ttu-id="00029-102">Istruzione Mid</span><span class="sxs-lookup"><span data-stu-id="00029-102">Mid Statement</span></span>
<span data-ttu-id="00029-103">Sostituisce un numero specificato di caratteri in un `String` variabili con i caratteri da un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="00029-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00029-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00029-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="00029-105">Parti</span><span class="sxs-lookup"><span data-stu-id="00029-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="00029-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="00029-106">Required.</span></span> <span data-ttu-id="00029-107">Nome del `String` variabile da modificare.</span><span class="sxs-lookup"><span data-stu-id="00029-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="00029-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="00029-108">Required.</span></span> <span data-ttu-id="00029-109">`Integer` espressione.</span><span class="sxs-lookup"><span data-stu-id="00029-109">`Integer` expression.</span></span> <span data-ttu-id="00029-110">Posizione del carattere in `Target` dove inizia la sostituzione di testo.</span><span class="sxs-lookup"><span data-stu-id="00029-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="00029-111">`Start` Usa un indice in base uno.</span><span class="sxs-lookup"><span data-stu-id="00029-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="00029-112">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="00029-112">Optional.</span></span> <span data-ttu-id="00029-113">`Integer` espressione.</span><span class="sxs-lookup"><span data-stu-id="00029-113">`Integer` expression.</span></span> <span data-ttu-id="00029-114">Numero di caratteri da sostituire.</span><span class="sxs-lookup"><span data-stu-id="00029-114">Number of characters to replace.</span></span> <span data-ttu-id="00029-115">Se omesso, tutti `String` viene usato.</span><span class="sxs-lookup"><span data-stu-id="00029-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="00029-116">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="00029-116">Required.</span></span> <span data-ttu-id="00029-117">`String` espressione che sostituisce parte di `Target`.</span><span class="sxs-lookup"><span data-stu-id="00029-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="00029-118">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="00029-118">Exceptions</span></span>  
  
|<span data-ttu-id="00029-119">Tipo di eccezione</span><span class="sxs-lookup"><span data-stu-id="00029-119">Exception type</span></span>|<span data-ttu-id="00029-120">Condizione</span><span class="sxs-lookup"><span data-stu-id="00029-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="00029-121">`Start` < = 0 o `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="00029-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00029-122">Note</span><span class="sxs-lookup"><span data-stu-id="00029-122">Remarks</span></span>  
 <span data-ttu-id="00029-123">Il numero di caratteri sostituiti è sempre minore o uguale al numero di caratteri in `Target`.</span><span class="sxs-lookup"><span data-stu-id="00029-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="00029-124">Visual Basic ha un <xref:Microsoft.VisualBasic.Strings.Mid%2A> funzione e un `Mid` istruzione.</span><span class="sxs-lookup"><span data-stu-id="00029-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="00029-125">Questi elementi funzionano entrambi in un numero specificato di caratteri in una stringa, ma il `Mid` funzione restituisce i caratteri, mentre il `Mid` istruzione sostituisce i caratteri.</span><span class="sxs-lookup"><span data-stu-id="00029-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="00029-126">Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="00029-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00029-127">Il `MidB` istruzione delle versioni precedenti di Visual Basic sostituisce una sottostringa in byte, anziché in caratteri.</span><span class="sxs-lookup"><span data-stu-id="00029-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="00029-128">Viene utilizzato principalmente per la conversione di stringhe nelle applicazioni di double byte character set (DBCS).</span><span class="sxs-lookup"><span data-stu-id="00029-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="00029-129">Tutte le stringhe di Visual Basic sono in formato Unicode, e `MidB` non è più supportata.</span><span class="sxs-lookup"><span data-stu-id="00029-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00029-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="00029-130">Example</span></span>  
 <span data-ttu-id="00029-131">Questo esempio viene usato il `Mid` istruzione per sostituire un numero specificato di caratteri in una variabile di stringa con caratteri da un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="00029-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="00029-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="00029-132">Requirements</span></span>  
 <span data-ttu-id="00029-133">**Spazio dei nomi:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="00029-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="00029-134">**Modulo:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="00029-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="00029-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="00029-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00029-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00029-136">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="00029-137">Stringhe</span><span class="sxs-lookup"><span data-stu-id="00029-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="00029-138">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="00029-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
