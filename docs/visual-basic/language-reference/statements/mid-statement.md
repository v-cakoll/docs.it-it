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
ms.openlocfilehash: 90408fd8a8cfc9b74c8422d0571d61f8534403f3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404452"
---
# <a name="mid-statement"></a><span data-ttu-id="6a641-102">Istruzione Mid</span><span class="sxs-lookup"><span data-stu-id="6a641-102">Mid Statement</span></span>
<span data-ttu-id="6a641-103">Sostituisce un numero specificato di caratteri in una `String` variabile con caratteri di un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="6a641-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a641-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a641-104">Syntax</span></span>  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="6a641-105">Parti</span><span class="sxs-lookup"><span data-stu-id="6a641-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="6a641-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6a641-106">Required.</span></span> <span data-ttu-id="6a641-107">Nome della `String` variabile da modificare.</span><span class="sxs-lookup"><span data-stu-id="6a641-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="6a641-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6a641-108">Required.</span></span> <span data-ttu-id="6a641-109">Espressione `Integer`.</span><span class="sxs-lookup"><span data-stu-id="6a641-109">`Integer` expression.</span></span> <span data-ttu-id="6a641-110">Posizione del carattere in in `Target` cui inizia la sostituzione del testo.</span><span class="sxs-lookup"><span data-stu-id="6a641-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="6a641-111">`Start`Usa un indice in base uno.</span><span class="sxs-lookup"><span data-stu-id="6a641-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="6a641-112">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="6a641-112">Optional.</span></span> <span data-ttu-id="6a641-113">Espressione `Integer`.</span><span class="sxs-lookup"><span data-stu-id="6a641-113">`Integer` expression.</span></span> <span data-ttu-id="6a641-114">Numero di caratteri da sostituire.</span><span class="sxs-lookup"><span data-stu-id="6a641-114">Number of characters to replace.</span></span> <span data-ttu-id="6a641-115">Se omesso, `String` viene utilizzato tutto.</span><span class="sxs-lookup"><span data-stu-id="6a641-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="6a641-116">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6a641-116">Required.</span></span> <span data-ttu-id="6a641-117">`String`espressione che sostituisce parte di `Target` .</span><span class="sxs-lookup"><span data-stu-id="6a641-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="6a641-118">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="6a641-118">Exceptions</span></span>  
  
|<span data-ttu-id="6a641-119">Tipo di eccezione</span><span class="sxs-lookup"><span data-stu-id="6a641-119">Exception type</span></span>|<span data-ttu-id="6a641-120">Condizione</span><span class="sxs-lookup"><span data-stu-id="6a641-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="6a641-121">`Start`<= 0 o `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="6a641-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a641-122">Commenti</span><span class="sxs-lookup"><span data-stu-id="6a641-122">Remarks</span></span>  
 <span data-ttu-id="6a641-123">Il numero di caratteri sostituiti è sempre minore o uguale al numero di caratteri in `Target` .</span><span class="sxs-lookup"><span data-stu-id="6a641-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="6a641-124">Visual Basic dispone di una <xref:Microsoft.VisualBasic.Strings.Mid%2A> funzione e di un' `Mid` istruzione.</span><span class="sxs-lookup"><span data-stu-id="6a641-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="6a641-125">Questi elementi operano entrambi su un numero specificato di caratteri in una stringa, ma la `Mid` funzione restituisce i caratteri mentre l' `Mid` istruzione sostituisce i caratteri.</span><span class="sxs-lookup"><span data-stu-id="6a641-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="6a641-126">Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="6a641-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a641-127">L' `MidB` istruzione di versioni precedenti di Visual Basic sostituisce una sottostringa in byte, anziché caratteri.</span><span class="sxs-lookup"><span data-stu-id="6a641-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="6a641-128">Viene utilizzato principalmente per la conversione di stringhe in applicazioni DBCS (Double-byte character set).</span><span class="sxs-lookup"><span data-stu-id="6a641-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="6a641-129">Tutte le stringhe di Visual Basic sono in formato Unicode e `MidB` non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="6a641-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a641-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="6a641-130">Example</span></span>  
 <span data-ttu-id="6a641-131">In questo esempio viene utilizzata l' `Mid` istruzione per sostituire un numero specificato di caratteri in una variabile di stringa con caratteri di un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="6a641-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="6a641-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6a641-132">Requirements</span></span>  
 <span data-ttu-id="6a641-133">**Spazio dei nomi:** [Microsoft. VisualBasic](../runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="6a641-133">**Namespace:** [Microsoft.VisualBasic](../runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="6a641-134">**Modulo:**`Strings`</span><span class="sxs-lookup"><span data-stu-id="6a641-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="6a641-135">**Assembly:** Libreria di runtime Visual Basic (in Microsoft. VisualBasic. dll)</span><span class="sxs-lookup"><span data-stu-id="6a641-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a641-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a641-136">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="6a641-137">Stringhe</span><span class="sxs-lookup"><span data-stu-id="6a641-137">Strings</span></span>](../../programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="6a641-138">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a641-138">Introduction to Strings in Visual Basic</span></span>](../../programming-guide/language-features/strings/introduction-to-strings.md)
