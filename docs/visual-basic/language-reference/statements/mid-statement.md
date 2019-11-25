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
ms.openlocfilehash: eeef4c13743b75a3d5e61ac46afb94d9ea105b7a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348031"
---
# <a name="mid-statement"></a><span data-ttu-id="6eb99-102">Istruzione Mid</span><span class="sxs-lookup"><span data-stu-id="6eb99-102">Mid Statement</span></span>
<span data-ttu-id="6eb99-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span><span class="sxs-lookup"><span data-stu-id="6eb99-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eb99-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6eb99-104">Syntax</span></span>  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="6eb99-105">Parti</span><span class="sxs-lookup"><span data-stu-id="6eb99-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="6eb99-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6eb99-106">Required.</span></span> <span data-ttu-id="6eb99-107">Name of the `String` variable to modify.</span><span class="sxs-lookup"><span data-stu-id="6eb99-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="6eb99-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6eb99-108">Required.</span></span> <span data-ttu-id="6eb99-109">`Integer` expression.</span><span class="sxs-lookup"><span data-stu-id="6eb99-109">`Integer` expression.</span></span> <span data-ttu-id="6eb99-110">Character position in `Target` where the replacement of text begins.</span><span class="sxs-lookup"><span data-stu-id="6eb99-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="6eb99-111">`Start` uses a one-based index.</span><span class="sxs-lookup"><span data-stu-id="6eb99-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="6eb99-112">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6eb99-112">Optional.</span></span> <span data-ttu-id="6eb99-113">`Integer` expression.</span><span class="sxs-lookup"><span data-stu-id="6eb99-113">`Integer` expression.</span></span> <span data-ttu-id="6eb99-114">Number of characters to replace.</span><span class="sxs-lookup"><span data-stu-id="6eb99-114">Number of characters to replace.</span></span> <span data-ttu-id="6eb99-115">If omitted, all of `String` is used.</span><span class="sxs-lookup"><span data-stu-id="6eb99-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="6eb99-116">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6eb99-116">Required.</span></span> <span data-ttu-id="6eb99-117">`String` expression that replaces part of `Target`.</span><span class="sxs-lookup"><span data-stu-id="6eb99-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="6eb99-118">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="6eb99-118">Exceptions</span></span>  
  
|<span data-ttu-id="6eb99-119">Tipo di eccezione</span><span class="sxs-lookup"><span data-stu-id="6eb99-119">Exception type</span></span>|<span data-ttu-id="6eb99-120">Condizione</span><span class="sxs-lookup"><span data-stu-id="6eb99-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="6eb99-121">`Start` <= 0 or `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="6eb99-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6eb99-122">Note</span><span class="sxs-lookup"><span data-stu-id="6eb99-122">Remarks</span></span>  
 <span data-ttu-id="6eb99-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span><span class="sxs-lookup"><span data-stu-id="6eb99-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="6eb99-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span><span class="sxs-lookup"><span data-stu-id="6eb99-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="6eb99-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span><span class="sxs-lookup"><span data-stu-id="6eb99-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="6eb99-126">Per ulteriori informazioni, vedere <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="6eb99-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6eb99-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span><span class="sxs-lookup"><span data-stu-id="6eb99-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="6eb99-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span><span class="sxs-lookup"><span data-stu-id="6eb99-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="6eb99-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span><span class="sxs-lookup"><span data-stu-id="6eb99-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6eb99-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="6eb99-130">Example</span></span>  
 <span data-ttu-id="6eb99-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span><span class="sxs-lookup"><span data-stu-id="6eb99-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="6eb99-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6eb99-132">Requirements</span></span>  
 <span data-ttu-id="6eb99-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="6eb99-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="6eb99-134">**Module:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="6eb99-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="6eb99-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="6eb99-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eb99-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6eb99-136">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="6eb99-137">Stringhe</span><span class="sxs-lookup"><span data-stu-id="6eb99-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="6eb99-138">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6eb99-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
