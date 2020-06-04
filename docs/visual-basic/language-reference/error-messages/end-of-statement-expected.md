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
# <a name="end-of-statement-expected"></a>Prevista fine dell'istruzione
L'istruzione è sintatticamente completa, ma un elemento di programmazione aggiuntivo segue l'elemento che completa l'istruzione. Alla fine di ogni istruzione è necessario un terminatore di riga.
  
 Un terminatore di riga divide i caratteri di un Visual Basic file di origine in righe. Esempi di caratteri di terminazione di riga sono il carattere di ritorno a capo Unicode (&HD), il carattere di avanzamento riga Unicode (&HA) e il carattere di ritorno a capo Unicode seguito dal carattere di avanzamento riga Unicode. Per ulteriori informazioni sui caratteri di terminazione di riga, vedere la [specifica del linguaggio Visual Basic](~/_vblang/spec/lexical-grammar.md#line-terminators).
  
 **ID errore:** BC30205
  
## <a name="to-correct-this-error"></a>Per correggere l'errore
  
1. Verificare se due istruzioni diverse sono state inavvertitamente posizionate nella stessa riga.
  
2. Inserire un terminatore di riga dopo l'elemento che completa l'istruzione.
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Interrompere e combinare istruzioni nel codice](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [Istruzioni](../../programming-guide/language-features/statements.md)
