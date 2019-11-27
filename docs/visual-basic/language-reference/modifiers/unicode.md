---
title: Unicode
ms.date: 07/20/2015
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
ms.openlocfilehash: c4286ed9e9d5fd768ae29b7050b3d1505ccca9dd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344214"
---
# <a name="unicode-visual-basic"></a>Unicode (Visual Basic)
Specifica che Visual Basic deve effettuare il marshalling di tutte le stringhe in valori Unicode indipendentemente dal nome della procedura esterna dichiarata.  
  
 Quando si chiama una routine definita all'esterno del progetto, il compilatore Visual Basic non ha accesso alle informazioni necessarie per chiamare correttamente la stored procedure. Queste informazioni includono la posizione in cui si trova la stored procedure, la modalità di identificazione, la sequenza chiamante e il tipo restituito e il set di caratteri stringa utilizzato. L' [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md) crea un riferimento a una procedura esterna e fornisce le informazioni necessarie.  
  
 La `charsetmodifier` parte nell'istruzione `Declare` fornisce le informazioni sul set di caratteri per eseguire il marshalling delle stringhe durante una chiamata alla procedura esterna. Influiscono inoltre sul modo in cui Visual Basic Cerca nel file esterno il nome della procedura esterna. Il modificatore `Unicode` specifica che Visual Basic deve effettuare il marshalling di tutte le stringhe in valori Unicode e deve cercare la routine senza modificarne il nome durante la ricerca.  
  
 Se non viene specificato alcun modificatore del set di caratteri, `Ansi` è il valore predefinito.  
  
## <a name="remarks"></a>Osservazioni  
 Il modificatore `Unicode` può essere usato in questo contesto:  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Note per gli sviluppatori di Smart Device  
 Questa parola chiave non è supportata.  
  
## <a name="see-also"></a>Vedere anche

- [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)
- [Auto](../../../visual-basic/language-reference/modifiers/auto.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
