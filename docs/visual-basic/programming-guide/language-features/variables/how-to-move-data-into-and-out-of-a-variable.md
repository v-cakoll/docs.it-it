---
title: 'Procedura: Spostare dati da e verso una variabile (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: 9b34173ebb3226fa00610c124c7b680e18d80de9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717944"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a>Procedura: Spostare dati da e verso una variabile (Visual Basic)
Archiviare un valore in una variabile, inserendo il nome della variabile sul lato sinistro di un'istruzione di assegnazione.  
  
## <a name="putting-data-in-a-variable"></a>Inserire dati in una variabile  
  
#### <a name="to-store-a-value-in-a-variable"></a>Per archiviare un valore in una variabile  
  
-   Usare il nome della variabile sul lato sinistro di un'istruzione di assegnazione.  
  
     Nell'esempio seguente imposta il valore della variabile `alpha`.  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     Il valore generato sul lato destro dell'istruzione di assegnazione viene archiviato nella variabile.  
  
## <a name="getting-data-from-a-variable"></a>Recupero di dati da una variabile  
 Per recuperare il valore della variabile, includendo il nome della variabile in un'espressione.  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a>Per recuperare un valore da una variabile  
  
-   Usare il nome della variabile in un'espressione. È possibile usare una variabile in un punto qualsiasi è possibile usare una costante o valore letterale, tranne in un'espressione che definisce il valore di una costante.  
  
     -oppure-  
  
-   Usare il nome della variabile seguendo uguali (`=`) Accedi a un'istruzione di assegnazione.  
  
     Nell'esempio seguente legge il valore della variabile `startValue` e quindi Usa il valore della variabile `counter` in un'espressione.  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     Il valore della variabile fa parte dell'espressione come una costante e quindi viene archiviato nella variabile o proprietà sul lato sinistro dell'istruzione di assegnazione.  
  
## <a name="see-also"></a>Vedere anche
- [Variabili](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
