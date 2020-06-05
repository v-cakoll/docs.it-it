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
ms.openlocfilehash: 9b1bc40bb52244deefc0486d3a40c4b961ad1ee5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402681"
---
# <a name="unicode-visual-basic"></a>Unicode (Visual Basic)
Specifica che Visual Basic deve effettuare il marshalling di tutte le stringhe in valori Unicode indipendentemente dal nome della procedura esterna dichiarata.  
  
 Quando si chiama una routine definita all'esterno del progetto, il compilatore Visual Basic non ha accesso alle informazioni necessarie per chiamare correttamente la stored procedure. Queste informazioni includono la posizione in cui si trova la stored procedure, la modalità di identificazione, la sequenza chiamante e il tipo restituito e il set di caratteri stringa utilizzato. L' [istruzione Declare](../statements/declare-statement.md) crea un riferimento a una procedura esterna e fornisce le informazioni necessarie.  
  
 La `charsetmodifier` parte nell' `Declare` istruzione fornisce le informazioni sul set di caratteri per il marshalling delle stringhe durante una chiamata alla procedura esterna. Influiscono inoltre sul modo in cui Visual Basic Cerca nel file esterno il nome della procedura esterna. Il `Unicode` modificatore specifica che Visual Basic necessario effettuare il marshalling di tutte le stringhe in valori Unicode e cercare la routine senza modificarne il nome durante la ricerca.  
  
 Se non viene specificato alcun modificatore del set di caratteri, `Ansi` è il valore predefinito.  
  
## <a name="remarks"></a>Commenti  
 Il `Unicode` modificatore può essere usato in questo contesto:  
  
 [Declare Statement](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Note per gli sviluppatori di Smart Device  
 Questa parola chiave non è supportata.  
  
## <a name="see-also"></a>Vedere anche

- [Ansi](ansi.md)
- [Auto](auto.md)
- [Parole chiave](../keywords/index.md)
