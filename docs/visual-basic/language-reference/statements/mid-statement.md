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
ms.openlocfilehash: df83fd527612af1a6a4b8131ffa2643ef0d1d7dd
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818566"
---
# <a name="mid-statement"></a><span data-ttu-id="0c149-102">Istruzione Mid</span><span class="sxs-lookup"><span data-stu-id="0c149-102">Mid Statement</span></span>
<span data-ttu-id="0c149-103">Sostituisce un numero specificato di caratteri in un `String` variabili con i caratteri da un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="0c149-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c149-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c149-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="0c149-105">Parti</span><span class="sxs-lookup"><span data-stu-id="0c149-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="0c149-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0c149-106">Required.</span></span> <span data-ttu-id="0c149-107">Nome del `String` variabile da modificare.</span><span class="sxs-lookup"><span data-stu-id="0c149-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="0c149-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0c149-108">Required.</span></span> <span data-ttu-id="0c149-109">`Integer` espressione.</span><span class="sxs-lookup"><span data-stu-id="0c149-109">`Integer` expression.</span></span> <span data-ttu-id="0c149-110">Posizione del carattere in `Target` dove inizia la sostituzione di testo.</span><span class="sxs-lookup"><span data-stu-id="0c149-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="0c149-111">`Start` Usa un indice in base uno.</span><span class="sxs-lookup"><span data-stu-id="0c149-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="0c149-112">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0c149-112">Optional.</span></span> <span data-ttu-id="0c149-113">`Integer` espressione.</span><span class="sxs-lookup"><span data-stu-id="0c149-113">`Integer` expression.</span></span> <span data-ttu-id="0c149-114">Numero di caratteri da sostituire.</span><span class="sxs-lookup"><span data-stu-id="0c149-114">Number of characters to replace.</span></span> <span data-ttu-id="0c149-115">Se omesso, tutti `String` viene usato.</span><span class="sxs-lookup"><span data-stu-id="0c149-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="0c149-116">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0c149-116">Required.</span></span> <span data-ttu-id="0c149-117">`String` espressione che sostituisce parte di `Target`.</span><span class="sxs-lookup"><span data-stu-id="0c149-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="0c149-118">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="0c149-118">Exceptions</span></span>  
  
|<span data-ttu-id="0c149-119">Tipo di eccezione</span><span class="sxs-lookup"><span data-stu-id="0c149-119">Exception type</span></span>|<span data-ttu-id="0c149-120">Condizione</span><span class="sxs-lookup"><span data-stu-id="0c149-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="0c149-121">`Start` < = 0 o `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="0c149-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c149-122">Note</span><span class="sxs-lookup"><span data-stu-id="0c149-122">Remarks</span></span>  
 <span data-ttu-id="0c149-123">Il numero di caratteri sostituiti è sempre minore o uguale al numero di caratteri in `Target`.</span><span class="sxs-lookup"><span data-stu-id="0c149-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="0c149-124">Visual Basic ha un <xref:Microsoft.VisualBasic.Strings.Mid%2A> funzione e un `Mid` istruzione.</span><span class="sxs-lookup"><span data-stu-id="0c149-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="0c149-125">Questi elementi funzionano entrambi in un numero specificato di caratteri in una stringa, ma il `Mid` funzione restituisce i caratteri, mentre il `Mid` istruzione sostituisce i caratteri.</span><span class="sxs-lookup"><span data-stu-id="0c149-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="0c149-126">Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="0c149-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c149-127">Il `MidB` istruzione delle versioni precedenti di Visual Basic sostituisce una sottostringa in byte, anziché in caratteri.</span><span class="sxs-lookup"><span data-stu-id="0c149-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="0c149-128">Viene utilizzato principalmente per la conversione di stringhe nelle applicazioni di double byte character set (DBCS).</span><span class="sxs-lookup"><span data-stu-id="0c149-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="0c149-129">Tutte le stringhe di Visual Basic sono in formato Unicode, e `MidB` non è più supportata.</span><span class="sxs-lookup"><span data-stu-id="0c149-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c149-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="0c149-130">Example</span></span>  
 <span data-ttu-id="0c149-131">Questo esempio viene usato il `Mid` istruzione per sostituire un numero specificato di caratteri in una variabile di stringa con caratteri da un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="0c149-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="0c149-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c149-132">Requirements</span></span>  
 <span data-ttu-id="0c149-133">**Spazio dei nomi:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="0c149-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="0c149-134">**Modulo:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="0c149-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="0c149-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c149-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c149-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c149-136">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="0c149-137">Stringhe</span><span class="sxs-lookup"><span data-stu-id="0c149-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="0c149-138">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0c149-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
