---
title: Prevista fine dell'istruzione
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 1ce5c793a09df34ac17e70e3253e98108bf76fb8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321477"
---
# <a name="end-of-statement-expected"></a><span data-ttu-id="fe7cb-102">Prevista fine dell'istruzione</span><span class="sxs-lookup"><span data-stu-id="fe7cb-102">End of statement expected</span></span>
<span data-ttu-id="fe7cb-103">L'istruzione sia sintatticamente completa, ma un elemento di programmazione aggiuntivo segue l'elemento che si completa l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="fe7cb-103">The statement is syntactically complete, but an additional programming element follows the element that completes the statement.</span></span> <span data-ttu-id="fe7cb-104">Un terminatore di riga è necessario alla fine di ogni istruzione.</span><span class="sxs-lookup"><span data-stu-id="fe7cb-104">A line terminator is required at the end of every statement.</span></span>
  
 <span data-ttu-id="fe7cb-105">Un terminatore di riga divide i caratteri di un file di origine Visual Basic in righe.</span><span class="sxs-lookup"><span data-stu-id="fe7cb-105">A line terminator divides the characters of a Visual Basic source file into lines.</span></span> <span data-ttu-id="fe7cb-106">Esempi di caratteri di terminazione di riga sono di Unicode ritorno a capo restituito carattere (& HD), il Unicode avanzamento riga carattere (e a disponibilità elevata), e il ritorno a capo Unicode restituisce caratteri seguita dal carattere di avanzamento di riga Unicode.</span><span class="sxs-lookup"><span data-stu-id="fe7cb-106">Examples of line terminators are the Unicode carriage return character (&HD), the Unicode linefeed character (&HA), and the Unicode carriage return character followed by the Unicode linefeed character.</span></span> <span data-ttu-id="fe7cb-107">Per altre informazioni sui caratteri di terminazione di riga, vedere la [specifiche del linguaggio Visual Basic](~/_vblang/spec/lexical-grammar.md#line-terminators).</span><span class="sxs-lookup"><span data-stu-id="fe7cb-107">For more information about line terminators, see the [Visual Basic Language Specification](~/_vblang/spec/lexical-grammar.md#line-terminators).</span></span>
  
 <span data-ttu-id="fe7cb-108">**ID errore:** BC30205</span><span class="sxs-lookup"><span data-stu-id="fe7cb-108">**Error ID:** BC30205</span></span>
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fe7cb-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="fe7cb-109">To correct this error</span></span>
  
1. <span data-ttu-id="fe7cb-110">Verificare se due istruzioni diverse inavvertitamente inserite nella stessa riga.</span><span class="sxs-lookup"><span data-stu-id="fe7cb-110">Check to see if two different statements have inadvertently been put on the same line.</span></span>
  
2. <span data-ttu-id="fe7cb-111">Inserisce un terminatore di riga dopo l'elemento che si completa l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="fe7cb-111">Insert a line terminator after the element that completes the statement.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fe7cb-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe7cb-112">See also</span></span>

- [<span data-ttu-id="fe7cb-113">Procedura: Interrompere e combinare istruzioni nel codice</span><span class="sxs-lookup"><span data-stu-id="fe7cb-113">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [<span data-ttu-id="fe7cb-114">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="fe7cb-114">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
