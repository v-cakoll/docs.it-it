---
title: Variabili di struttura (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef42c44de84caffde909eb2b3e9361016a6abb97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="structure-variables-visual-basic"></a>Variabili di struttura (Visual Basic)
Dopo aver creato una struttura, è possibile dichiarare le variabili a livello di routine sia a livello di modulo come quel tipo. Ad esempio, è possibile creare una struttura che registra le informazioni su un computer. Nell'esempio che segue viene illustrato quanto descritto.  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 È ora possibile dichiarare variabili di quel tipo. Questa condizione è illustrata la dichiarazione seguente.  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  In classi e moduli, le strutture dichiarate utilizzando il [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md) predefinito l'accesso pubblico. Se si intende una struttura per essere private, assicurarsi che dichiara la classe utilizzando il [privata](../../../../visual-basic/language-reference/modifiers/private.md) (parola chiave).  
  
## <a name="access-to-structure-values"></a>Accesso ai valori di struttura  
 Per assegnare e recuperare i valori dagli elementi di una variabile di struttura, utilizzare la stessa sintassi utilizzata per impostare e ottenere le proprietà su un oggetto. Inserire l'operatore di accesso ai membri (`.`) tra il nome di variabile di struttura e il nome dell'elemento. Nell'esempio seguente accede agli elementi delle variabili dichiarate in precedenza come tipo `systemInfo`.  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a>L'assegnazione delle variabili di struttura  
 È inoltre possibile assegnare una variabile a un'altra se sono entrambi dello stesso tipo di struttura. Verranno copiati tutti gli elementi di una struttura per gli elementi corrispondenti in altra. Questa condizione è illustrata la dichiarazione seguente.  
  
```  
yourSystem = mySystem  
```  
  
 Se un elemento di struttura è un tipo riferimento, ad esempio un `String`, `Object`, o matrice, puntatore ai dati viene copiato. Nell'esempio precedente, se `systemInfo` fosse stata inclusa una variabile oggetto, quindi l'esempio precedente avrebbe consentito la copia del puntatore da `mySystem` a `yourSystem`, e una modifica ai dati dell'oggetto tramite una struttura sarebbe attivo quando vi si accede con la struttura.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Tipi valore e tipi riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Procedura: Dichiarare una struttura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Strutture e altri elementi di programmazione](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [Strutture e classi](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [Istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
