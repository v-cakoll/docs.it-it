---
title: "Procedura: Velocizzare l'accesso a un oggetto con un percorso di qualificazione lungo (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: 94c838a69aab9fcae9dc0c79b6038ee90e2369e7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59299137"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a>Procedura: Velocizzare l'accesso a un oggetto con un percorso di qualificazione lungo (Visual Basic)
Se si accede di frequente un oggetto che richiede un percorso di qualificazione dei diversi metodi e proprietà, è possibile velocizzare il codice non ripetendo il percorso di qualificazione.  
  
 Esistono due modi, è possibile evitare di ripetere il percorso di qualificazione. È possibile assegnare l'oggetto a una variabile, oppure è possibile usarlo in un `With`... `End With` blocco.  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a>Per velocizzare l'accesso tramite l'assegnazione a una variabile a un oggetto di qualificazione  
  
1. Dichiarare una variabile del tipo di oggetto cui si accede di frequente. Specificare il percorso di qualificazione nella parte di inizializzazione della dichiarazione.  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2. Usare la variabile per accedere ai membri dell'oggetto.  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a>Per velocizzare l'accesso a un oggetto qualificazione usando una clausola With... Blocco End With  
  
1. Inserire il percorso di qualificazione in un `With` istruzione.  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2. Accedere ai membri dell'oggetto all'interno di `With` blocca, in precedenza il `End With` istruzione.  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Istruzione With...End With](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
