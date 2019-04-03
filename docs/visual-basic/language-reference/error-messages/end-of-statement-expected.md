---
title: Prevista fine dell'istruzione
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: ab6a4a0e6736e2af9c1fa0dd170b6aa4c42d9e4a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817154"
---
# <a name="end-of-statement-expected"></a>Prevista fine dell'istruzione
L'istruzione sia sintatticamente completa, ma un elemento di programmazione aggiuntivo segue l'elemento che si completa l'istruzione. Un terminatore di riga è necessario alla fine di ogni istruzione.
  
 Un terminatore di riga divide i caratteri di un file di origine Visual Basic in righe. Esempi di caratteri di terminazione di riga sono di Unicode ritorno a capo restituito carattere (& HD), il Unicode avanzamento riga carattere (e a disponibilità elevata), e il ritorno a capo Unicode restituisce caratteri seguita dal carattere di avanzamento di riga Unicode. Per altre informazioni sui caratteri di terminazione di riga, vedere la [specifiche del linguaggio Visual Basic](~/_vblang/spec/lexical-grammar.md#line-terminators).
  
 **ID errore:** BC30205
  
## <a name="to-correct-this-error"></a>Per correggere l'errore
  
1.  Verificare se due istruzioni diverse inavvertitamente inserite nella stessa riga.
  
2.  Inserisce un terminatore di riga dopo l'elemento che si completa l'istruzione.
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
