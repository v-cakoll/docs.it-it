---
title: 'Procedura: fare riferimento all''istanza corrente di un oggetto (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 33ea612253b00e12f47258189da4ac7d8d98ade5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>Procedura: fare riferimento all'istanza corrente di un oggetto (Visual Basic)
Il *istanza corrente* di un oggetto è l'istanza in cui il codice attualmente in esecuzione.  
  
 Utilizzare il `Me` (parola chiave) per fare riferimento all'istanza corrente.  
  
### <a name="to-refer-to-the-current-instance"></a>Per fare riferimento all'istanza corrente  
  
-   Utilizzare il `Me` (parola chiave) in cui normalmente si utilizzerebbe il nome di una variabile oggetto.  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Sebbene `Me` si comporta come un oggetto variabile, non è possibile dichiararla o assegnarvi alcun valore. `Me`fa sempre riferimento all'istanza corrente.  
  
## <a name="see-also"></a>Vedere anche  
 [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Assegnazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
