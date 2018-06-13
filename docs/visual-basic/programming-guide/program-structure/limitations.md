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
ms.openlocfilehash: 57378c3aa18a5cc108c10e8654e55803f3cf9052
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649929"
---
# <a name="visual-basic-limitations"></a>Limitazioni di Visual Basic
Le versioni precedenti di Visual Basic applicati limiti nel codice, ad esempio la lunghezza di nomi di variabili, il numero di variabili consentite nei moduli e le dimensioni del modulo. In Visual Basic .NET, queste restrizioni sono stati ridotti, fornendo una maggiore libertà nella scrittura e il codice.  
  
 Limiti fisici sono dipendenti in memoria in fase di esecuzione di più sulle considerazioni relative alla fase di compilazione. Se si utilizzano le procedure di programmazione prudenti e dividono applicazioni di grandi dimensioni in più classi e moduli, è poche probabilità di che si verifichi un limite interno di Visual Basic.  
  
 Di seguito sono alcune limitazioni che potrebbero verificarsi in casi estremi.  
  
-   **Lunghezza del nome.** È un numero massimo di caratteri per il nome di ogni elemento di programmazione dichiarato. Questo limite si applica a un'intera stringa di qualificazione se il nome dell'elemento è completo. Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   **Lunghezza della riga.** È un massimo di 65535 caratteri in una riga fisica del codice sorgente. La riga di codice sorgente logico può essere superiore se si utilizzano caratteri di continuazione di riga. Vedere [procedura: interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
-   **Dimensioni della matrice.** È un numero massimo delle dimensioni che è possibile dichiarare una matrice. Questo limita il numero degli indici è possibile utilizzare per specificare un elemento di matrice. Vedere [matrice di dimensioni in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).  
  
-   **Lunghezza della stringa.** È un numero massimo di caratteri Unicode, che è possibile archiviare in una singola stringa. Vedere [tipo di dati stringa](../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
-   **Lunghezza della stringa di ambiente.** È un massimo di 32768 caratteri per qualsiasi stringa di ambiente utilizzato come argomento della riga di comando. Si tratta di una limitazione in tutte le piattaforme.  
  
## <a name="see-also"></a>Vedere anche  
 [Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Convenzioni di denominazione di Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
