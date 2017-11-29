---
title: Limitazioni di Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 97a2e162b9f1a673fbe805a5d2ef1421cd423a4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="visual-basic-limitations"></a>Limitazioni di Visual Basic
Le versioni precedenti di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] applicati limiti nel codice, ad esempio la lunghezza dei nomi di variabile, il numero di variabili consentite nei moduli le dimensioni del modulo. In Visual Basic .NET, queste restrizioni sono stati ridotti, fornendo una maggiore libertà nella scrittura e il codice.  
  
 Limiti fisici sono dipendenti in memoria in fase di esecuzione di più sulle considerazioni relative alla fase di compilazione. Se si utilizzano le procedure di programmazione prudenti e dividono applicazioni di grandi dimensioni in più classi e moduli, quindi è poco probabile che si verifichi un interno di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] limitazione.  
  
 Di seguito sono alcune limitazioni che potrebbero verificarsi in casi estremi.  
  
-   **Lunghezza del nome.** È un numero massimo di caratteri per il nome di ogni elemento di programmazione dichiarato. Questo limite si applica a un'intera stringa di qualificazione se il nome dell'elemento è completo. Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   **Lunghezza della riga.** È un massimo di 65535 caratteri in una riga fisica del codice sorgente. La riga di codice sorgente logico può essere superiore se si utilizzano caratteri di continuazione di riga. Vedere [procedura: interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
-   **Dimensioni della matrice.** È un numero massimo delle dimensioni che è possibile dichiarare una matrice. Questo limita il numero degli indici è possibile utilizzare per specificare un elemento di matrice. Vedere [matrice di dimensioni in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).  
  
-   **Lunghezza della stringa.** È un numero massimo di caratteri Unicode, che è possibile archiviare in una singola stringa. Vedere [tipo di dati stringa](../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
-   **Lunghezza della stringa di ambiente.** È un massimo di 32768 caratteri per qualsiasi stringa di ambiente utilizzato come argomento della riga di comando. Si tratta di una limitazione in tutte le piattaforme.  
  
## <a name="see-also"></a>Vedere anche  
 [Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Convenzioni di denominazione di Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
