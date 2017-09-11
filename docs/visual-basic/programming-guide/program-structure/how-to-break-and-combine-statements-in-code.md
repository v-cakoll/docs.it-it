---
title: 'Procedura: interrompere e combinare istruzioni nel codice (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb._
dev_langs:
- VB
helpviewer_keywords:
- colons (:)
- line continuation
- _ line-continuation character
- ': line separator character'
- Visual Basic code, line breaks in
- Visual Basic code, line breaks
- Visual Basic code, line continuation
- long lines of code
- line terminator
- line-continuation sequence
- underscores, in code
- statements [Visual Basic], line continuation in
- line breaks, in code
- line-continuation character
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2ca281035a0bd81a9b52cdd60f2bc59724852709
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="a6574-102">Procedura: Interrompere e combinare istruzioni nel codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6574-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>
<span data-ttu-id="a6574-103">Quando si scrive codice, è possibile creare in alcuni casi istruzioni molto lunghe che richiedono lo scorrimento orizzontale nell'Editor di codice.</span><span class="sxs-lookup"><span data-stu-id="a6574-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="a6574-104">Anche se ciò non influiscono sulla modalità di esecuzione del codice, rende difficile a te o ad altri utenti di leggere il codice visualizzato sul monitor.</span><span class="sxs-lookup"><span data-stu-id="a6574-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="a6574-105">In questi casi, è opportuno suddividere una lunga istruzione in più righe.</span><span class="sxs-lookup"><span data-stu-id="a6574-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="a6574-106">Per suddividere una singola istruzione in più righe</span><span class="sxs-lookup"><span data-stu-id="a6574-106">To break a single statement into multiple lines</span></span>  
  
-   <span data-ttu-id="a6574-107">Utilizzare il carattere di continuazione di riga, ovvero un carattere di sottolineatura (`_`), nel punto in cui si desidera inserire l'interruzione di riga.</span><span class="sxs-lookup"><span data-stu-id="a6574-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="a6574-108">Il carattere di continuazione di riga deve essere preceduto da uno spazio e seguito da un terminatore di riga (ritorno a capo).</span><span class="sxs-lookup"><span data-stu-id="a6574-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a6574-109">In alcuni casi, se si omette il carattere di continuazione di riga, il compilatore Visual Basic in modo implicito continuerà l'istruzione nella riga successiva del codice.</span><span class="sxs-lookup"><span data-stu-id="a6574-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="a6574-110">Per un elenco di elementi della sintassi per il quale è possibile omettere il carattere di continuazione di riga, vedere "Continuazione di riga implicita" in [istruzioni](../../../visual-basic/programming-guide/language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="a6574-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
     <span data-ttu-id="a6574-111">Nell'esempio seguente, l'istruzione viene suddivisa in quattro righe con caratteri di continuazione di riga che terminano tutte tranne l'ultima riga.</span><span class="sxs-lookup"><span data-stu-id="a6574-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>  
  
     <span data-ttu-id="a6574-112">[!code-vb[VbVbcnConventions&#20;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a6574-112">[!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]</span></span>  
  
     <span data-ttu-id="a6574-113">Utilizzo di questa sequenza semplifica il codice leggere, sia online e quando stampata.</span><span class="sxs-lookup"><span data-stu-id="a6574-113">Using this sequence makes your code easier to read, both online and when printed.</span></span>  
  
     <span data-ttu-id="a6574-114">Il carattere di continuazione di riga deve essere l'ultimo carattere su una riga.</span><span class="sxs-lookup"><span data-stu-id="a6574-114">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="a6574-115">È possibile seguire con altri elementi nella stessa riga.</span><span class="sxs-lookup"><span data-stu-id="a6574-115">You can't follow it with anything else on the same line.</span></span>  
  
     <span data-ttu-id="a6574-116">Esistono alcune limitazioni riguardo in cui è possibile utilizzare il carattere di continuazione di riga; ad esempio, è possibile utilizzare all'interno di un nome dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="a6574-116">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="a6574-117">È possibile interrompere un elenco di argomenti con il carattere di continuazione di riga, ma i singoli nomi degli argomenti devono rimanere invariati.</span><span class="sxs-lookup"><span data-stu-id="a6574-117">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>  
  
     <span data-ttu-id="a6574-118">È possibile continuare un commento con un carattere di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="a6574-118">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="a6574-119">Il compilatore non esamina i caratteri in un commento per un significato speciale.</span><span class="sxs-lookup"><span data-stu-id="a6574-119">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="a6574-120">Per commenti su più righe, ripetere il simbolo di commento (`'`) in ogni riga.</span><span class="sxs-lookup"><span data-stu-id="a6574-120">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>  
  
 <span data-ttu-id="a6574-121">Sebbene il metodo consigliato consiste nell'inserire ogni istruzione su una riga separata [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] consente inoltre di inserire più istruzioni sulla stessa riga.</span><span class="sxs-lookup"><span data-stu-id="a6574-121">Although placing each statement on a separate line is the recommended method, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] also allows you to place multiple statements on the same line.</span></span>  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="a6574-122">Per inserire più istruzioni sulla stessa riga</span><span class="sxs-lookup"><span data-stu-id="a6574-122">To place multiple statements on the same line</span></span>  
  
-   <span data-ttu-id="a6574-123">Separare le istruzioni con due punti (`:`), come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a6574-123">Separate the statements with a colon (`:`), as in the following example.</span></span>  
  
     <span data-ttu-id="a6574-124">[!code-vb[VbVbcnConventions&#10;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a6574-124">[!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6574-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6574-125">See Also</span></span>  
 <span data-ttu-id="a6574-126">[Struttura del programma e convenzioni del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="a6574-126">[Program Structure and Code Conventions](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span></span>  
<span data-ttu-id="a6574-127"> [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)</span><span class="sxs-lookup"><span data-stu-id="a6574-127"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md)</span></span>
