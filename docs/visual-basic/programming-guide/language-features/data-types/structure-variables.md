---
title: Variabili di struttura (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 9a6e542e297a17f44d929235530ae6058cf13a36
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816330"
---
# <a name="structure-variables-visual-basic"></a>Variabili di struttura (Visual Basic)
Dopo aver creato una struttura, è possibile dichiarare le variabili a livello di routine e a livello di modulo di quel tipo. Ad esempio, è possibile creare una struttura di registrare le informazioni sul sistema. Nell'esempio che segue viene illustrato quanto descritto.  
  
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
>  Nelle classi e moduli, strutture dichiarate utilizzando il [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) predefinito per l'accesso pubblico. Se si intende una struttura a essere private, assicurarsi di dichiarare usando il [privato](../../../../visual-basic/language-reference/modifiers/private.md) (parola chiave).  
  
## <a name="access-to-structure-values"></a>Accesso ai valori di struttura  
 Per assegnare e recuperare i valori dagli elementi di una variabile di struttura, utilizzare la stessa sintassi utilizzata per impostare e ottenere le proprietà su un oggetto. Si inserisce l'operatore di accesso ai membri (`.`) tra il nome di variabile di struttura e il nome dell'elemento. Nell'esempio seguente accede agli elementi delle variabili dichiarate in precedenza come tipo `systemInfo`.  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a>Assegnazione di variabili di struttura  
 È anche possibile assegnare una variabile a un altro se entrambi sono dello stesso tipo struttura. Questa copia tutti gli elementi di una struttura per gli elementi corrispondenti in altra. Questa condizione è illustrata la dichiarazione seguente.  
  
```  
yourSystem = mySystem  
```  
  
 Se un elemento di struttura è un tipo riferimento, ad esempio un `String`, `Object`, o matrice, il puntatore ai dati viene copiato. Nell'esempio precedente, se `systemInfo` fosse stata inclusa una variabile oggetto, quindi l'esempio precedente sarebbe stato copiato il puntatore dal `mySystem` a `yourSystem`, e una modifica ai dati dell'oggetto tramite una sola struttura sarebbe attivo quando si accede tramite la struttura.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Procedura: Dichiarare una struttura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Strutture e altri elementi di programmazione](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [Strutture e classi](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
