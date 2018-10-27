---
title: Prevista fine dell'istruzione
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 8df756009ebe3a0613ec47018d938151829214df
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50039023"
---
# <a name="end-of-statement-expected"></a><span data-ttu-id="65942-102">Prevista fine dell'istruzione</span><span class="sxs-lookup"><span data-stu-id="65942-102">End of statement expected</span></span>
<span data-ttu-id="65942-103">L'istruzione sia sintatticamente completa, ma un elemento di programmazione aggiuntivo segue l'elemento che si completa l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="65942-103">The statement is syntactically complete, but an additional programming element follows the element that completes the statement.</span></span> <span data-ttu-id="65942-104">Un terminatore di riga è necessario alla fine di ogni istruzione.</span><span class="sxs-lookup"><span data-stu-id="65942-104">A line terminator is required at the end of every statement.</span></span>
  
 <span data-ttu-id="65942-105">Un terminatore di riga divide i caratteri di un file di origine Visual Basic in righe.</span><span class="sxs-lookup"><span data-stu-id="65942-105">A line terminator divides the characters of a Visual Basic source file into lines.</span></span> <span data-ttu-id="65942-106">Esempi di caratteri di terminazione di riga sono di Unicode ritorno a capo restituito carattere (& HD), il Unicode avanzamento riga carattere (e a disponibilità elevata), e il ritorno a capo Unicode restituisce caratteri seguita dal carattere di avanzamento di riga Unicode.</span><span class="sxs-lookup"><span data-stu-id="65942-106">Examples of line terminators are the Unicode carriage return character (&HD), the Unicode linefeed character (&HA), and the Unicode carriage return character followed by the Unicode linefeed character.</span></span> <span data-ttu-id="65942-107">Per altre informazioni sui caratteri di terminazione di riga, vedere la [specifiche del linguaggio Visual Basic](~/_vblang/spec/lexical-grammar.md#line-terminators).</span><span class="sxs-lookup"><span data-stu-id="65942-107">For more information about line terminators, see the [Visual Basic Language Specification](~/_vblang/spec/lexical-grammar.md#line-terminators).</span></span>
  
 <span data-ttu-id="65942-108">**ID errore:** BC30205</span><span class="sxs-lookup"><span data-stu-id="65942-108">**Error ID:** BC30205</span></span>
  
## <a name="to-correct-this-error"></a><span data-ttu-id="65942-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="65942-109">To correct this error</span></span>
  
1.  <span data-ttu-id="65942-110">Verificare se due istruzioni diverse inavvertitamente inserite nella stessa riga.</span><span class="sxs-lookup"><span data-stu-id="65942-110">Check to see if two different statements have inadvertently been put on the same line.</span></span>
  
2.  <span data-ttu-id="65942-111">Inserisce un terminatore di riga dopo l'elemento che si completa l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="65942-111">Insert a line terminator after the element that completes the statement.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="65942-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65942-112">See Also</span></span>  
 [<span data-ttu-id="65942-113">Procedura: Interrompere e combinare istruzioni nel codice</span><span class="sxs-lookup"><span data-stu-id="65942-113">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 [<span data-ttu-id="65942-114">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="65942-114">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
