---
title: "Procedura: velocizzare l'accesso a un oggetto con un percorso di qualificazione lungo (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: d52d13feb0f85065c0623b5937f558b841c036dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650199"
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
