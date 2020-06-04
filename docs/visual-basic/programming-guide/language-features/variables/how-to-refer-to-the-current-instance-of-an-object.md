---
title: "Procedura: fare riferimento all'istanza corrente di un oggetto"
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 43bfd54592fb1d26cbf7f268b7e098e01e3745d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410425"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>Procedura: fare riferimento all'istanza corrente di un oggetto (Visual Basic)
L' *istanza corrente* di un oggetto è l'istanza di in cui è attualmente in esecuzione il codice.  
  
 Usare la `Me` parola chiave per fare riferimento all'istanza corrente.  
  
### <a name="to-refer-to-the-current-instance"></a>Per fare riferimento all'istanza corrente  
  
- Usare la `Me` parola chiave in cui in genere si usa il nome di una variabile oggetto.  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Anche se `Me` si comporta come una variabile oggetto, non è possibile dichiararla o assegnarvi alcun elemento. `Me`fa sempre riferimento all'istanza corrente.  
  
## <a name="see-also"></a>Vedere anche

- [Variabili oggetto](object-variables.md)
- [Assegnazione di variabili oggetto](object-variable-assignment.md)
- [Me, My, MyBase e MyClass](../../program-structure/me-my-mybase-and-myclass.md)
