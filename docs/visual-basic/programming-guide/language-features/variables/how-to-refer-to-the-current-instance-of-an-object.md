---
title: "Procedura: Fare riferimento all'istanza corrente di un oggetto (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 3c44748798d5ed554fc9fbded9c3a4d981a66d2f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58823363"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>Procedura: Fare riferimento all'istanza corrente di un oggetto (Visual Basic)
Il *istanza corrente* di un oggetto è l'istanza in cui è attualmente in esecuzione il codice.  
  
 Si utilizza il `Me` (parola chiave) per fare riferimento all'istanza corrente.  
  
### <a name="to-refer-to-the-current-instance"></a>Per fare riferimento all'istanza corrente  
  
-   Usare il `Me` parola chiave in cui in genere si utilizzerà il nome di una variabile oggetto.  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Sebbene `Me` si comporta come un oggetto variabile, non è possibile dichiararla o qualsiasi elemento assegnare ad esso. `Me` fa sempre riferimento all'istanza corrente.  
  
## <a name="see-also"></a>Vedere anche

- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Assegnazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
