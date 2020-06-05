---
title: Automatico
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: b9bdeed55788252c71b8fb1c995c140cbfdf60eb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373128"
---
# <a name="auto-visual-basic"></a>Auto (Visual Basic)
Specifica che Visual Basic deve effettuare il marshalling delle stringhe in base alle regole di .NET Framework in base al nome esterno della procedura esterna dichiarata.  
  
 Quando si chiama una routine definita all'esterno del progetto, il compilatore Visual Basic non ha accesso alle informazioni necessarie per chiamare correttamente la stored procedure. Queste informazioni includono la posizione in cui si trova la stored procedure, la modalità di identificazione, la sequenza chiamante e il tipo restituito e il set di caratteri stringa utilizzato. L' [istruzione Declare](../statements/declare-statement.md) crea un riferimento a una procedura esterna e fornisce le informazioni necessarie.  
  
 La `charsetmodifier` parte nell' `Declare` istruzione fornisce le informazioni sul set di caratteri per il marshalling delle stringhe durante una chiamata alla procedura esterna. Influiscono inoltre sul modo in cui Visual Basic Cerca nel file esterno il nome della procedura esterna. Il `Auto` modificatore specifica che Visual Basic deve effettuare il marshalling delle stringhe in base alle regole di .NET Framework e che deve determinare il set di caratteri di base della piattaforma di runtime ed eventualmente modificare il nome della procedura esterna se la ricerca iniziale ha esito negativo. Per ulteriori informazioni, vedere "set di caratteri" nell' [istruzione Declare](../statements/declare-statement.md).  
  
 Se non viene specificato alcun modificatore del set di caratteri, `Ansi` è il valore predefinito.  
  
## <a name="remarks"></a>Commenti  
 Il `Auto` modificatore può essere usato in questo contesto:  
  
 [Declare Statement](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Note per gli sviluppatori di Smart Device  
 Questa parola chiave non è supportata.  
  
## <a name="see-also"></a>Vedere anche

- [Ansi](ansi.md)
- [Unicode](unicode.md)
- [Parole chiave](../keywords/index.md)
