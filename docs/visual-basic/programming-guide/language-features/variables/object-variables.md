---
title: Variabili oggetto in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44689d649a381618e5d6c934deb2b7b9bea463ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="object-variables-in-visual-basic"></a>Variabili oggetto in Visual Basic
Oltre ad archiviare i valori direttamente, una variabile può fare riferimento a un oggetto. Si assegna un oggetto a una variabile per gli stessi motivi che si assegna un valore a una variabile:  
  
-   Un nome di variabile è spesso più brevi e facili da ricordare rispetto al percorso completo di metodi e proprietà necessarie per accedere all'oggetto stesso.  
  
-   Utilizzo di una variabile che fa riferimento a un oggetto è più efficiente dell'accesso più volte l'oggetto stesso tramite i metodi necessari o proprietà.  
  
-   È possibile modificare una variabile per fare riferimento ad altri oggetti durante l'esecuzione di codice.  
  
## <a name="making-code-shorter"></a>Abbreviazione del codice  
 È possibile utilizzare variabili oggetto per abbreviare il codice da digitare. Nell'esempio seguente viene utilizzato il percorso completo di metodi e proprietà per accedere a un <xref:System.Windows.Forms.Control> oggetto.  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 È possibile abbreviare il codice e velocizzare l'esecuzione, se si utilizza una variabile oggetto per il controllo. È necessario dichiarare la variabile oggetto con la classe specifica che si desidera assegnare a esso (`Control` in questo caso). Quando si assegna un oggetto alla variabile, è possibile considerarlo esattamente lo stesso usato per l'oggetto a cui viene fatto riferimento. È possibile impostare o recuperare le proprietà dell'oggetto o utilizzare uno qualsiasi dei relativi metodi. Nell'esempio seguente viene utilizzata una variabile oggetto per semplificare il codice nell'esempio precedente.  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Procedura: Velocizzare l'accesso a un oggetto con un percorso di qualificazione lungo](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)  
 [Dichiarazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Assegnazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Valori di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
