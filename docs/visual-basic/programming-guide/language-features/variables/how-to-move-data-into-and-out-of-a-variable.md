---
title: 'Procedura: spostare i dati all''interno e all''esterno di una variabile (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fefb1979e35cd7b5fa1917f8f1a57af575e51234
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a>Procedura: spostare i dati all'interno e all'esterno di una variabile (Visual Basic)
Archiviare un valore in una variabile inserendo il nome della variabile sul lato sinistro di un'istruzione di assegnazione.  
  
## <a name="putting-data-in-a-variable"></a>Inserimento di dati in una variabile  
  
#### <a name="to-store-a-value-in-a-variable"></a>Per archiviare un valore in una variabile  
  
-   Utilizzare il nome della variabile sul lato sinistro di un'istruzione di assegnazione.  
  
     Nell'esempio seguente imposta il valore della variabile `alpha`.  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     Il valore generato sul lato destro dell'istruzione di assegnazione è archiviato nella variabile.  
  
## <a name="getting-data-from-a-variable"></a>Recupero di dati da una variabile  
 Per recuperare il valore di una variabile, includendo il nome della variabile in un'espressione.  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a>Per recuperare un valore da una variabile  
  
-   Utilizzare il nome della variabile in un'espressione. È possibile utilizzare una variabile in qualsiasi punto è possibile utilizzare una costante o valore letterale, tranne in un'espressione che definisce il valore di una costante.  
  
     -oppure-  
  
-   Utilizzare il nome della variabile seguente uguali (`=`) eseguire l'accesso in un'istruzione di assegnazione.  
  
     Nell'esempio seguente legge il valore della variabile `startValue` e quindi utilizza il valore della variabile `counter` in un'espressione.  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     Il valore della variabile fa parte dell'espressione come una costante, e quindi viene archiviato nella variabile o proprietà sul lato sinistro dell'istruzione di assegnazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Variabili](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
