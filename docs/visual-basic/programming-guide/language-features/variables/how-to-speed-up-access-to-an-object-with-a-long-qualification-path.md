---
title: 'Procedura: velocizzare l''accesso a un oggetto con un percorso di qualificazione lungo (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5d91eeaeb034a4c8b4fefcffdf2fdebe72127d66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a>Procedura: velocizzare l'accesso a un oggetto con un percorso di qualificazione lungo (Visual Basic)
Se un oggetto che richiede un percorso di qualificazione di numerosi metodi e proprietà si accede di frequente, è possibile velocizzare il codice ripetendo non il percorso di qualificazione.  
  
 Esistono due modi per evitare di ripetere il percorso di qualificazione. È possibile assegnare l'oggetto a una variabile, oppure è possibile utilizzarlo in un `With`... `End With` blocco.  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a>Per velocizzare l'accesso tramite l'assegnazione a una variabile a un oggetto di qualificazione  
  
1.  Dichiarare una variabile del tipo di oggetto che si accede di frequente. Specificare il percorso di qualificazione nella parte di inizializzazione della dichiarazione.  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  Utilizzare la variabile per accedere ai membri dell'oggetto.  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a>Per velocizzare l'accesso a un oggetto qualificazione utilizzando un With... Blocco End With  
  
1.  Inserire il percorso di qualificazione in un `With` istruzione.  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  Accedere ai membri dell'oggetto all'interno di `With` blocco, prima di `End With` istruzione.  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Istruzione With...End With](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
