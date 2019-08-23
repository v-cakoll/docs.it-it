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
ms.openlocfilehash: 16149ce42e3476cf07a62298f83734fee9ec7253
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957764"
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="0e9b7-102">Istruzione REM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e9b7-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="0e9b7-103">Utilizzato per includere osservazioni esplicative nel codice sorgente di un programma.</span><span class="sxs-lookup"><span data-stu-id="0e9b7-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e9b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e9b7-104">Syntax</span></span>  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="0e9b7-105">Parti</span><span class="sxs-lookup"><span data-stu-id="0e9b7-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="0e9b7-106">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0e9b7-106">Optional.</span></span> <span data-ttu-id="0e9b7-107">Testo di qualsiasi commento che si desidera includere.</span><span class="sxs-lookup"><span data-stu-id="0e9b7-107">The text of any comment you want to include.</span></span> <span data-ttu-id="0e9b7-108">È necessario uno spazio tra la `REM` parola chiave `comment`e.</span><span class="sxs-lookup"><span data-stu-id="0e9b7-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e9b7-109">Note</span><span class="sxs-lookup"><span data-stu-id="0e9b7-109">Remarks</span></span>  
 <span data-ttu-id="0e9b7-110">È possibile inserire un' `REM` istruzione da solo su una riga oppure è possibile inserirla in una riga che segue un'altra istruzione.</span><span class="sxs-lookup"><span data-stu-id="0e9b7-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="0e9b7-111">L' `REM` istruzione deve essere l'ultima istruzione della riga.</span><span class="sxs-lookup"><span data-stu-id="0e9b7-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="0e9b7-112">Se segue un'altra istruzione, l' `REM` oggetto deve essere separato dall'istruzione da uno spazio.</span><span class="sxs-lookup"><span data-stu-id="0e9b7-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="0e9b7-113">È possibile utilizzare le`'` `REM`virgolette singole () anziché.</span><span class="sxs-lookup"><span data-stu-id="0e9b7-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="0e9b7-114">Questo vale se il commento segue un'altra istruzione sulla stessa riga o si trova da solo su una riga.</span><span class="sxs-lookup"><span data-stu-id="0e9b7-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0e9b7-115">Non è possibile continuare `REM` un'istruzione utilizzando una sequenza di continuazione di`_`riga ().</span><span class="sxs-lookup"><span data-stu-id="0e9b7-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="0e9b7-116">Una volta che viene avviato un commento, il compilatore non esamina i caratteri per un significato speciale.</span><span class="sxs-lookup"><span data-stu-id="0e9b7-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="0e9b7-117">Per un commento su più righe, usare un' `REM` altra istruzione o un simbolo di`'`commento () in ogni riga.</span><span class="sxs-lookup"><span data-stu-id="0e9b7-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e9b7-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="0e9b7-118">Example</span></span>  
 <span data-ttu-id="0e9b7-119">Nell'esempio seguente viene illustrata `REM` l'istruzione, che viene utilizzata per includere osservazioni esplicative in un programma.</span><span class="sxs-lookup"><span data-stu-id="0e9b7-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="0e9b7-120">Viene inoltre illustrata l'alternativa di utilizzare il carattere virgoletta singola (`'`) `REM`anziché.</span><span class="sxs-lookup"><span data-stu-id="0e9b7-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="0e9b7-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e9b7-121">See also</span></span>

- [<span data-ttu-id="0e9b7-122">Commenti nel codice</span><span class="sxs-lookup"><span data-stu-id="0e9b7-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [<span data-ttu-id="0e9b7-123">Procedura: Interrompere e combinare istruzioni nel codice</span><span class="sxs-lookup"><span data-stu-id="0e9b7-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
