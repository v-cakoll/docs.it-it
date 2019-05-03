---
title: Limitazioni di Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: 10f67c02d25ec275d1c3e98197d51c25aa250c19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955506"
---
# <a name="visual-basic-limitations"></a>Limitazioni di Visual Basic
Le versioni precedenti di Visual Basic applicati limiti nel codice, ad esempio la lunghezza dei nomi di variabili, il numero di variabili nei moduli e le dimensioni del modulo è consentita. In Visual Basic .NET, queste restrizioni sono stati ridotti, fornendo una maggiore libertà nella scrittura e il codice.  
  
 Limiti fisici sono dipendenti più memoria di runtime rispetto a su considerazioni relative alla fase di compilazione. Se si utilizzano le procedure di programmazione prudenti e dividono applicazioni di grandi dimensioni in più classi e moduli, quindi è molto poco probabile che si verifichi una limitazione di Visual Basic interna di.  
  
 Di seguito sono alcune limitazioni che possono verificarsi in casi estremi.  
  
- **Lunghezza del nome.** È presente un numero massimo di caratteri per il nome di ogni elemento di programmazione dichiarato. Questo limite si applica a un'intera stringa di qualificazione se il nome dell'elemento è qualificato. Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
- **Lunghezza riga.** È presente un massimo di 65535 caratteri in una riga fisica del codice sorgente. La riga del codice sorgente logico può essere più lunga se si usano caratteri di continuazione di riga. Vedere [How to: Interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
- **Dimensioni della matrice.** È presente un numero massimo delle dimensioni che è possibile dichiarare una matrice. Questo limita il numero degli indici è possibile usare per specificare un elemento della matrice. Visualizzare [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).  
  
- **Lunghezza della stringa.** È presente un numero massimo di caratteri Unicode, che è possibile archiviare in una singola stringa. Visualizzare [tipo di dati stringa](../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
- **Lunghezza della stringa di ambiente.** È presente un massimo di 32768 caratteri per qualsiasi stringa di ambiente usato come argomento della riga di comando. Si tratta di una limitazione in tutte le piattaforme.  
  
## <a name="see-also"></a>Vedere anche

- [Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Convenzioni di denominazione di Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
