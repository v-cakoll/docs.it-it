---
title: Prevista fine dell'istruzione
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 169f01b02df377ba6cc21ffad53c36f5d4537140
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409647"
---
# <a name="end-of-statement-expected"></a><span data-ttu-id="94c29-102">Prevista fine dell'istruzione</span><span class="sxs-lookup"><span data-stu-id="94c29-102">End of statement expected</span></span>
<span data-ttu-id="94c29-103">L'istruzione è sintatticamente completa, ma un elemento di programmazione aggiuntivo segue l'elemento che completa l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="94c29-103">The statement is syntactically complete, but an additional programming element follows the element that completes the statement.</span></span> <span data-ttu-id="94c29-104">Alla fine di ogni istruzione è necessario un terminatore di riga.</span><span class="sxs-lookup"><span data-stu-id="94c29-104">A line terminator is required at the end of every statement.</span></span>
  
 <span data-ttu-id="94c29-105">Un terminatore di riga divide i caratteri di un Visual Basic file di origine in righe.</span><span class="sxs-lookup"><span data-stu-id="94c29-105">A line terminator divides the characters of a Visual Basic source file into lines.</span></span> <span data-ttu-id="94c29-106">Esempi di caratteri di terminazione di riga sono il carattere di ritorno a capo Unicode (&HD), il carattere di avanzamento riga Unicode (&HA) e il carattere di ritorno a capo Unicode seguito dal carattere di avanzamento riga Unicode.</span><span class="sxs-lookup"><span data-stu-id="94c29-106">Examples of line terminators are the Unicode carriage return character (&HD), the Unicode linefeed character (&HA), and the Unicode carriage return character followed by the Unicode linefeed character.</span></span> <span data-ttu-id="94c29-107">Per ulteriori informazioni sui caratteri di terminazione di riga, vedere la [specifica del linguaggio Visual Basic](~/_vblang/spec/lexical-grammar.md#line-terminators).</span><span class="sxs-lookup"><span data-stu-id="94c29-107">For more information about line terminators, see the [Visual Basic Language Specification](~/_vblang/spec/lexical-grammar.md#line-terminators).</span></span>
  
 <span data-ttu-id="94c29-108">**ID errore:** BC30205</span><span class="sxs-lookup"><span data-stu-id="94c29-108">**Error ID:** BC30205</span></span>
  
## <a name="to-correct-this-error"></a><span data-ttu-id="94c29-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="94c29-109">To correct this error</span></span>
  
1. <span data-ttu-id="94c29-110">Verificare se due istruzioni diverse sono state inavvertitamente posizionate nella stessa riga.</span><span class="sxs-lookup"><span data-stu-id="94c29-110">Check to see if two different statements have inadvertently been put on the same line.</span></span>
  
2. <span data-ttu-id="94c29-111">Inserire un terminatore di riga dopo l'elemento che completa l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="94c29-111">Insert a line terminator after the element that completes the statement.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="94c29-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94c29-112">See also</span></span>

- [<span data-ttu-id="94c29-113">Procedura: Interrompere e combinare istruzioni nel codice</span><span class="sxs-lookup"><span data-stu-id="94c29-113">How to: Break and Combine Statements in Code</span></span>](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [<span data-ttu-id="94c29-114">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="94c29-114">Statements</span></span>](../../programming-guide/language-features/statements.md)
