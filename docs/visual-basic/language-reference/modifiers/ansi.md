---
title: Ansi
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: 0c38c2b81af7b4cb8fd1723853a09c5413f805af
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344746"
---
# <a name="ansi-visual-basic"></a>Ansi (Visual Basic)
Specifica che Visual Basic deve effettuare il marshalling di tutte le stringhe in valori di American National Standards Institute (ANSI) indipendentemente dal nome della procedura esterna dichiarata.  
  
 Quando si chiama una routine definita all'esterno del progetto, il compilatore Visual Basic non ha accesso alle informazioni necessarie per chiamare correttamente la stored procedure. Queste informazioni includono la posizione in cui si trova la stored procedure, la modalità di identificazione, la sequenza chiamante e il tipo restituito e il set di caratteri stringa utilizzato. L' [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md) crea un riferimento a una procedura esterna e fornisce le informazioni necessarie.  
  
 La `charsetmodifier` parte nell'istruzione `Declare` fornisce le informazioni sul set di caratteri per il marshalling delle stringhe durante una chiamata alla procedura esterna. Influiscono inoltre sul modo in cui Visual Basic Cerca nel file esterno il nome della procedura esterna. Il modificatore `Ansi` specifica che Visual Basic deve effettuare il marshalling di tutte le stringhe in valori ANSI ed esaminare la procedura senza modificarne il nome durante la ricerca.  
  
 Se non viene specificato alcun modificatore del set di caratteri, `Ansi` è il valore predefinito.  
  
## <a name="remarks"></a>Osservazioni  
 Il modificatore `Ansi` può essere usato in questo contesto:  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Note per gli sviluppatori di Smart Device  
 Questa parola chiave non è supportata.  
  
## <a name="see-also"></a>Vedere anche

- [Auto](../../../visual-basic/language-reference/modifiers/auto.md)
- [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
