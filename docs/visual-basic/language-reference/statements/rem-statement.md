---
title: Istruzione REM (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d64ce970e3e74437f5e8c63c8a4d578900902192
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="b52d9-102">Istruzione REM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b52d9-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="b52d9-103">Utilizzato per includere note esplicative nel codice sorgente di un programma.</span><span class="sxs-lookup"><span data-stu-id="b52d9-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b52d9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b52d9-104">Syntax</span></span>  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="b52d9-105">Parti</span><span class="sxs-lookup"><span data-stu-id="b52d9-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="b52d9-106">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b52d9-106">Optional.</span></span> <span data-ttu-id="b52d9-107">Il testo di qualsiasi commento da includere.</span><span class="sxs-lookup"><span data-stu-id="b52d9-107">The text of any comment you want to include.</span></span> <span data-ttu-id="b52d9-108">Uno spazio è necessario tra il `REM` (parola chiave) e `comment`.</span><span class="sxs-lookup"><span data-stu-id="b52d9-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b52d9-109">Note</span><span class="sxs-lookup"><span data-stu-id="b52d9-109">Remarks</span></span>  
 <span data-ttu-id="b52d9-110">È possibile inserire un `REM` istruzione da solo su una riga oppure è possibile inserirlo in una riga dopo un'altra istruzione.</span><span class="sxs-lookup"><span data-stu-id="b52d9-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="b52d9-111">Il `REM` istruzione deve essere l'ultima istruzione nella riga.</span><span class="sxs-lookup"><span data-stu-id="b52d9-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="b52d9-112">Se segue un'altra istruzione, il `REM` devono essere separati da tale istruzione da uno spazio.</span><span class="sxs-lookup"><span data-stu-id="b52d9-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="b52d9-113">È possibile utilizzare una virgoletta singola (`'`) anziché `REM`.</span><span class="sxs-lookup"><span data-stu-id="b52d9-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="b52d9-114">Ciò è vero se il commento segue un'altra istruzione sulla stessa riga o si trova da sola in una riga.</span><span class="sxs-lookup"><span data-stu-id="b52d9-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b52d9-115">Non è possibile continuare un `REM` tramite l'utilizzo di una sequenza di continuazione di riga (`_`).</span><span class="sxs-lookup"><span data-stu-id="b52d9-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="b52d9-116">Una volta avviato un commento, il compilatore non esamina i caratteri per un significato speciale.</span><span class="sxs-lookup"><span data-stu-id="b52d9-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="b52d9-117">Per commenti su più righe, utilizzare un altro `REM` istruzione o un simbolo di commento (`'`) per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="b52d9-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b52d9-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="b52d9-118">Example</span></span>  
 <span data-ttu-id="b52d9-119">Nell'esempio seguente viene illustrato il `REM` istruzione, viene utilizzato per includere note esplicative in un programma.</span><span class="sxs-lookup"><span data-stu-id="b52d9-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="b52d9-120">Viene inoltre illustrato l'alternativa di utilizzare il carattere virgoletta singola (`'`) anziché `REM`.</span><span class="sxs-lookup"><span data-stu-id="b52d9-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b52d9-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b52d9-121">See Also</span></span>  
 [<span data-ttu-id="b52d9-122">Commenti nel codice</span><span class="sxs-lookup"><span data-stu-id="b52d9-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 [<span data-ttu-id="b52d9-123">Procedura: Interrompere e combinare istruzioni nel codice</span><span class="sxs-lookup"><span data-stu-id="b52d9-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
