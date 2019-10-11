---
title: Impossibile utilizzare i parametri di tipo come qualificatori
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 3ff4b189539bf119351a94dabadd596c336ac723
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250335"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a>Impossibile utilizzare i parametri di tipo come qualificatori

Un elemento di programmazione è qualificato con una stringa di qualificazione che include un parametro di tipo.

Un parametro di tipo rappresenta un requisito per un tipo che deve essere specificato quando viene costruito il tipo generico. Non rappresenta un tipo definito specifico. Una stringa di qualificazione deve includere solo elementi definiti in fase di compilazione.

Il codice seguente può generare questo errore:

```vb  
Public Function CheckText(Of c As System.Windows.Forms.Control)(
    badText As String) As Boolean
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.
End Function  
```  
  
 **ID errore:** BC32098  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Rimuovere il parametro di tipo dalla stringa di qualificazione o sostituirlo con un tipo definito.  
  
2. Se è necessario usare un tipo costruito per individuare l'elemento di programmazione qualificato, è necessario usare la logica di programma aggiuntiva.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti a elementi dichiarati](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Elenco dei tipi](../statements/type-list.md)
