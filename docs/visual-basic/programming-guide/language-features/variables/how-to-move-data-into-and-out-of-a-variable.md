---
title: "Procedura: spostare i dati all'interno e all'esterno di una variabile"
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: bc5a7377a5e2e4c7ebe7291fd5f0093c4d6e996d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346896"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a>Procedura: spostare i dati all'interno e all'esterno di una variabile (Visual Basic)

Per archiviare un valore in una variabile, inserire il nome della variabile sul lato sinistro di un'istruzione di assegnazione.

## <a name="putting-data-in-a-variable"></a>Inserimento di dati in una variabile

#### <a name="to-store-a-value-in-a-variable"></a>Per archiviare un valore in una variabile

- Usare il nome della variabile sul lato sinistro di un'istruzione di assegnazione.

    Nell'esempio seguente viene impostato il valore della variabile `alpha`.

    ```vb
    alpha = (beta * 6.27) / (gamma + 2.1)
    ```

    Il valore generato sul lato destro dell'istruzione di assegnazione viene archiviato nella variabile.

## <a name="getting-data-from-a-variable"></a>Recupero di dati da una variabile

Per recuperare il valore di una variabile, è necessario includere il nome della variabile in un'espressione.

#### <a name="to-retrieve-a-value-from-a-variable"></a>Per recuperare un valore da una variabile

- Usare il nome della variabile in un'espressione. È possibile usare una variabile ovunque sia possibile usare una costante o un valore letterale, tranne che in un'espressione che definisce il valore di una costante.

  \-oppure-

- Usare il nome della variabile che segue il segno di uguale (`=`) in un'istruzione di assegnazione.

  Nell'esempio seguente viene letto il valore della variabile `startValue`, quindi viene utilizzato il valore della variabile `counter` in un'espressione.

  ```vb
  counter = startValue
  cellValue = (counter + 5) ^ 2
  ```

  Il valore della variabile partecipa all'espressione come una costante e quindi viene archiviato nella variabile o nella proprietà sul lato sinistro dell'istruzione di assegnazione.

## <a name="see-also"></a>Vedere anche

- [Variabili](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
