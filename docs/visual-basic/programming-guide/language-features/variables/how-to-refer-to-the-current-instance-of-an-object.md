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
ms.openlocfilehash: 62b22a54904a45380052d3d81d9415517d4f8d3b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346888"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>Procedura: fare riferimento all'istanza corrente di un oggetto (Visual Basic)
L' *istanza corrente* di un oggetto è l'istanza di in cui è attualmente in esecuzione il codice.  
  
 Usare la parola chiave `Me` per fare riferimento all'istanza corrente.  
  
### <a name="to-refer-to-the-current-instance"></a>Per fare riferimento all'istanza corrente  
  
- Usare la parola chiave `Me` dove normalmente si usa il nome di una variabile oggetto.  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Sebbene `Me` si comportano come una variabile oggetto, non è possibile dichiararla o assegnarvi alcun elemento. `Me` fa sempre riferimento all'istanza corrente.  
  
## <a name="see-also"></a>Vedere anche

- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Assegnazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
