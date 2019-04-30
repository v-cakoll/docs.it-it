---
title: 'Procedura: Interrompere e combinare istruzioni nel codice (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb._
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
- underscores [Visual Basic], in code
- statements [Visual Basic], line continuation in
- line breaks [Visual Basic], in code
- line-continuation character [Visual Basic]
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
ms.openlocfilehash: 680084c39b90d4f664f48559fa21388ce192d999
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955623"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="a399f-102">Procedura: Interrompere e combinare istruzioni nel codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a399f-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>
<span data-ttu-id="a399f-103">Quando si scrive codice, è possibile creare in alcuni casi le istruzioni di lunga durate che richiedono uno scorrimento orizzontale nell'Editor del codice.</span><span class="sxs-lookup"><span data-stu-id="a399f-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="a399f-104">Anche se ciò non influiscono sulla modalità di esecuzione del codice, rende difficile per te o per altri utenti a leggere il codice visualizzato sul monitor.</span><span class="sxs-lookup"><span data-stu-id="a399f-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="a399f-105">In questi casi, è necessario considerare suddividendo la singola istruzione lunga in più righe.</span><span class="sxs-lookup"><span data-stu-id="a399f-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="a399f-106">Per suddividere una singola istruzione in più righe</span><span class="sxs-lookup"><span data-stu-id="a399f-106">To break a single statement into multiple lines</span></span>  
  
- <span data-ttu-id="a399f-107">Usare il carattere di continuazione di riga, ovvero un carattere di sottolineatura (`_`), nel punto in cui si desidera interrompere la riga.</span><span class="sxs-lookup"><span data-stu-id="a399f-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="a399f-108">Il carattere di continuazione di riga deve essere preceduto da uno spazio e seguito da un terminatore di riga (ritorno a capo).</span><span class="sxs-lookup"><span data-stu-id="a399f-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a399f-109">In alcuni casi, se si omette il carattere di continuazione di riga, il compilatore Visual Basic in modo implicito continuerà l'istruzione nella riga successiva del codice.</span><span class="sxs-lookup"><span data-stu-id="a399f-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="a399f-110">Per un elenco di elementi della sintassi per il quale è possibile omettere il carattere di continuazione di riga, vedere "Continuazione di riga implicita" nella [istruzioni](../../../visual-basic/programming-guide/language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="a399f-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
     <span data-ttu-id="a399f-111">Nell'esempio seguente, l'istruzione viene suddivisa in quattro righe con terminazione di tutti i caratteri di continuazione di riga, ma l'ultima riga.</span><span class="sxs-lookup"><span data-stu-id="a399f-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>  
  
     [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]  
  
     <span data-ttu-id="a399f-112">Utilizzo di questa sequenza rende il codice più leggibile, stampati sia online e quando.</span><span class="sxs-lookup"><span data-stu-id="a399f-112">Using this sequence makes your code easier to read, both online and when printed.</span></span>  
  
     <span data-ttu-id="a399f-113">Il carattere di continuazione di riga deve essere l'ultimo carattere in una riga.</span><span class="sxs-lookup"><span data-stu-id="a399f-113">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="a399f-114">È non è possibile seguirla con altre operazioni sulla stessa riga.</span><span class="sxs-lookup"><span data-stu-id="a399f-114">You can't follow it with anything else on the same line.</span></span>  
  
     <span data-ttu-id="a399f-115">Esistono alcune limitazioni riguardo in cui è possibile usare il carattere di continuazione di riga. è ad esempio, non è possibile usarlo all'interno di un nome di argomento.</span><span class="sxs-lookup"><span data-stu-id="a399f-115">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="a399f-116">È possibile interrompere un elenco di argomenti con il carattere di continuazione di riga, ma i singoli tipi degli argomenti devono rimanere invariati.</span><span class="sxs-lookup"><span data-stu-id="a399f-116">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>  
  
     <span data-ttu-id="a399f-117">È possibile proseguire un commento con un carattere di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="a399f-117">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="a399f-118">Il compilatore non esamina i caratteri in un commento per un significato speciale.</span><span class="sxs-lookup"><span data-stu-id="a399f-118">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="a399f-119">Per commenti su più righe, ripetere il simbolo di commento (`'`) per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="a399f-119">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>  
  
 <span data-ttu-id="a399f-120">Anche se il metodo consigliato consiste nell'inserire ogni istruzione in una riga distinta, Visual Basic consente inoltre di inserire istruzioni di più sulla stessa riga.</span><span class="sxs-lookup"><span data-stu-id="a399f-120">Although placing each statement on a separate line is the recommended method, Visual Basic also allows you to place multiple statements on the same line.</span></span>  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="a399f-121">Per inserire più istruzioni sulla stessa riga</span><span class="sxs-lookup"><span data-stu-id="a399f-121">To place multiple statements on the same line</span></span>  
  
- <span data-ttu-id="a399f-122">Separare le istruzioni con un carattere due punti (`:`), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a399f-122">Separate the statements with a colon (`:`), as in the following example.</span></span>  
  
     [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="a399f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a399f-123">See also</span></span>

- [<span data-ttu-id="a399f-124">Struttura del programma e convenzioni di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="a399f-124">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="a399f-125">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="a399f-125">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
