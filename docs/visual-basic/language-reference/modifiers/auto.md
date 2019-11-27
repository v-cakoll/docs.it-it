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
ms.openlocfilehash: 7ea46e5f8b882bb986f23e792b240bad0c5be7a5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351613"
---
# <a name="auto-visual-basic"></a>Auto (Visual Basic)
Specifica che Visual Basic deve effettuare il marshalling delle stringhe in base alle regole di .NET Framework in base al nome esterno della procedura esterna dichiarata.  
  
 Quando si chiama una routine definita all'esterno del progetto, il compilatore Visual Basic non ha accesso alle informazioni necessarie per chiamare correttamente la stored procedure. Queste informazioni includono la posizione in cui si trova la stored procedure, la modalità di identificazione, la sequenza chiamante e il tipo restituito e il set di caratteri stringa utilizzato. L' [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md) crea un riferimento a una procedura esterna e fornisce le informazioni necessarie.  
  
 La `charsetmodifier` parte nell'istruzione `Declare` fornisce le informazioni sul set di caratteri per il marshalling delle stringhe durante una chiamata alla procedura esterna. Influiscono inoltre sul modo in cui Visual Basic Cerca nel file esterno il nome della procedura esterna. Il modificatore `Auto` specifica che Visual Basic deve effettuare il marshalling delle stringhe in base alle regole di .NET Framework e che deve determinare il set di caratteri di base della piattaforma di runtime ed eventualmente modificare il nome della procedura esterna se la ricerca iniziale ha esito negativo. Per ulteriori informazioni, vedere "set di caratteri" nell' [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md).  
  
 Se non viene specificato alcun modificatore del set di caratteri, `Ansi` è il valore predefinito.  
  
## <a name="remarks"></a>Note  
 Il modificatore `Auto` può essere usato in questo contesto:  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Note per gli sviluppatori di Smart Device  
 Questa parola chiave non è supportata.  
  
## <a name="see-also"></a>Vedere anche

- [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)
- [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
