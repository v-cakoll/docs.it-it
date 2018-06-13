---
title: Istruzione REM (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
ms.openlocfilehash: 3bd526b08e1ba3be856e1e823cf8ef49ea9b6c97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604276"
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="f81dd-102">Istruzione REM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f81dd-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="f81dd-103">Utilizzato per includere note esplicative nel codice sorgente di un programma.</span><span class="sxs-lookup"><span data-stu-id="f81dd-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f81dd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f81dd-104">Syntax</span></span>  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="f81dd-105">Parti</span><span class="sxs-lookup"><span data-stu-id="f81dd-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="f81dd-106">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f81dd-106">Optional.</span></span> <span data-ttu-id="f81dd-107">Il testo di qualsiasi commento da includere.</span><span class="sxs-lookup"><span data-stu-id="f81dd-107">The text of any comment you want to include.</span></span> <span data-ttu-id="f81dd-108">Uno spazio è necessario tra il `REM` (parola chiave) e `comment`.</span><span class="sxs-lookup"><span data-stu-id="f81dd-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f81dd-109">Note</span><span class="sxs-lookup"><span data-stu-id="f81dd-109">Remarks</span></span>  
 <span data-ttu-id="f81dd-110">È possibile inserire un `REM` istruzione da solo su una riga oppure è possibile inserirlo in una riga dopo un'altra istruzione.</span><span class="sxs-lookup"><span data-stu-id="f81dd-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="f81dd-111">Il `REM` istruzione deve essere l'ultima istruzione nella riga.</span><span class="sxs-lookup"><span data-stu-id="f81dd-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="f81dd-112">Se segue un'altra istruzione, il `REM` devono essere separati da tale istruzione da uno spazio.</span><span class="sxs-lookup"><span data-stu-id="f81dd-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="f81dd-113">È possibile utilizzare una virgoletta singola (`'`) anziché `REM`.</span><span class="sxs-lookup"><span data-stu-id="f81dd-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="f81dd-114">Ciò è vero se il commento segue un'altra istruzione sulla stessa riga o si trova da sola in una riga.</span><span class="sxs-lookup"><span data-stu-id="f81dd-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f81dd-115">Non è possibile continuare un `REM` tramite l'utilizzo di una sequenza di continuazione di riga (`_`).</span><span class="sxs-lookup"><span data-stu-id="f81dd-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="f81dd-116">Una volta avviato un commento, il compilatore non esamina i caratteri per un significato speciale.</span><span class="sxs-lookup"><span data-stu-id="f81dd-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="f81dd-117">Per commenti su più righe, utilizzare un altro `REM` istruzione o un simbolo di commento (`'`) per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="f81dd-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f81dd-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="f81dd-118">Example</span></span>  
 <span data-ttu-id="f81dd-119">Nell'esempio seguente viene illustrato il `REM` istruzione, viene utilizzato per includere note esplicative in un programma.</span><span class="sxs-lookup"><span data-stu-id="f81dd-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="f81dd-120">Viene inoltre illustrato l'alternativa di utilizzare il carattere virgoletta singola (`'`) anziché `REM`.</span><span class="sxs-lookup"><span data-stu-id="f81dd-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f81dd-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f81dd-121">See Also</span></span>  
 [<span data-ttu-id="f81dd-122">Commenti nel codice</span><span class="sxs-lookup"><span data-stu-id="f81dd-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 [<span data-ttu-id="f81dd-123">Procedura: Interrompere e combinare istruzioni nel codice</span><span class="sxs-lookup"><span data-stu-id="f81dd-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
