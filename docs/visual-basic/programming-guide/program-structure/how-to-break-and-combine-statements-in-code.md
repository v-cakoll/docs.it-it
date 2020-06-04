---
title: 'Procedura: Interrompere e combinare istruzioni nel codice'
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
ms.openlocfilehash: c78cbeaa5c2df2d4f2e3cce2b5b3fb8048ff3388
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403252"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="82b37-102">Procedura: Interrompere e combinare istruzioni nel codice (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82b37-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>

<span data-ttu-id="82b37-103">Quando si scrive il codice, è possibile creare a volte istruzioni lunghe che richiedono lo scorrimento orizzontale nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="82b37-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="82b37-104">Sebbene questa operazione non influisca sul modo in cui viene eseguito il codice, è difficile per l'utente o per chiunque legga il codice visualizzato sul monitor.</span><span class="sxs-lookup"><span data-stu-id="82b37-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="82b37-105">In questi casi, è consigliabile suddividere la singola istruzione Long in più righe.</span><span class="sxs-lookup"><span data-stu-id="82b37-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>

## <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="82b37-106">Per suddividere una singola istruzione in più righe</span><span class="sxs-lookup"><span data-stu-id="82b37-106">To break a single statement into multiple lines</span></span>

<span data-ttu-id="82b37-107">Utilizzare il carattere di continuazione di riga, ovvero un carattere di sottolineatura ( `_` ), nel punto in cui si desidera che la riga si interrompa.</span><span class="sxs-lookup"><span data-stu-id="82b37-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="82b37-108">Il carattere di sottolineatura deve essere immediatamente preceduto da uno spazio e seguito da un terminatore di riga (ritorno a capo) o (a partire dalla versione 16,0) di un commento seguito da un ritorno a capo.</span><span class="sxs-lookup"><span data-stu-id="82b37-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return) or (starting with version 16.0) a comment followed by a carriage return.</span></span>

  > [!NOTE]
  > <span data-ttu-id="82b37-109">In alcuni casi, se si omette il carattere di continuazione di riga, il Visual Basic compilatore continuerà in modo implicito l'istruzione alla riga di codice successiva.</span><span class="sxs-lookup"><span data-stu-id="82b37-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="82b37-110">Per un elenco degli elementi della sintassi per i quali è possibile omettere il carattere di continuazione di riga, vedere "continuazione di riga implicita" nelle [istruzioni](../language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="82b37-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../language-features/statements.md).</span></span>

  <span data-ttu-id="82b37-111">Nell'esempio seguente l'istruzione è suddivisa in quattro righe con caratteri di continuazione di riga che terminano tutti tranne l'ultima riga.</span><span class="sxs-lookup"><span data-stu-id="82b37-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>

  [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]

  <span data-ttu-id="82b37-112">L'uso di questa sequenza rende il codice più facile da leggere, sia online che quando viene stampato.</span><span class="sxs-lookup"><span data-stu-id="82b37-112">Using this sequence makes your code easier to read, both online and when printed.</span></span>

  <span data-ttu-id="82b37-113">Il carattere di continuazione di riga deve essere l'ultimo carattere su una riga.</span><span class="sxs-lookup"><span data-stu-id="82b37-113">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="82b37-114">Non è possibile seguire altre operazioni sulla stessa riga.</span><span class="sxs-lookup"><span data-stu-id="82b37-114">You can't follow it with anything else on the same line.</span></span>

  <span data-ttu-id="82b37-115">Esistono alcune limitazioni per la posizione in cui è possibile utilizzare il carattere di continuazione di riga; ad esempio, non è possibile usarlo nel mezzo di un nome di argomento.</span><span class="sxs-lookup"><span data-stu-id="82b37-115">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="82b37-116">È possibile suddividere un elenco di argomenti con il carattere di continuazione di riga, ma i singoli nomi degli argomenti devono rimanere intatti.</span><span class="sxs-lookup"><span data-stu-id="82b37-116">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>

  <span data-ttu-id="82b37-117">Non è possibile continuare un commento usando un carattere di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="82b37-117">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="82b37-118">Il compilatore non esamina i caratteri in un commento per un significato speciale.</span><span class="sxs-lookup"><span data-stu-id="82b37-118">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="82b37-119">Per un commento su più righe, ripetere il simbolo di commento ( `'` ) in ogni riga.</span><span class="sxs-lookup"><span data-stu-id="82b37-119">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>

 <span data-ttu-id="82b37-120">Sebbene ogni istruzione venga posizionata in una riga distinta è il metodo consigliato, Visual Basic consente anche di inserire più istruzioni nella stessa riga.</span><span class="sxs-lookup"><span data-stu-id="82b37-120">Although placing each statement on a separate line is the recommended method, Visual Basic also allows you to place multiple statements on the same line.</span></span>

## <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="82b37-121">Per inserire più istruzioni nella stessa riga</span><span class="sxs-lookup"><span data-stu-id="82b37-121">To place multiple statements on the same line</span></span>

<span data-ttu-id="82b37-122">Separare le istruzioni con i due punti ( `:` ), come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="82b37-122">Separate the statements with a colon (`:`), as in the following example:</span></span>

  [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]

## <a name="see-also"></a><span data-ttu-id="82b37-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82b37-123">See also</span></span>

- [<span data-ttu-id="82b37-124">Struttura del programma e convenzioni del codice</span><span class="sxs-lookup"><span data-stu-id="82b37-124">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="82b37-125">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="82b37-125">Statements</span></span>](../language-features/statements.md)
