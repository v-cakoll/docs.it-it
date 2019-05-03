---
title: Auto (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: e4beb320b3aa0cadb790dd3ab92255496bc32f05
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802700"
---
# <a name="auto-visual-basic"></a>Auto (Visual Basic)
Specifica che Visual Basic deve eseguire il marshalling di stringhe in base alle regole di .NET Framework in base al nome esterno della routine esterna viene dichiarato.  
  
 Quando si chiama una routine definita all'esterno del progetto, il compilatore Visual Basic è privo di accesso alle informazioni necessario per chiamare correttamente la routine. Queste informazioni includono la procedura in cui si trova, come viene identificato, la sequenza di chiamata e tipo restituito e il carattere stringa set utilizzato. Il [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) crea un riferimento a una routine esterna e fornisce le informazioni necessarie.  
  
 Il `charsetmodifier` parte nel `Declare` istruzione fornisce le informazioni sul set di caratteri per il marshalling di stringhe durante una chiamata alla routine esterna. Influisce anche sulla modalità di ricerca di file esterno per il nome della routine esterna. Il `Auto` modificatore specifica che Visual Basic deve effettuare il marshalling delle stringhe in base alle regole di .NET Framework e che è necessario determinare il carattere di base impostato della piattaforma in fase di esecuzione ed eventualmente modificare il nome della routine esterna se esegue una ricerca iniziale si verifica un errore. Per altre informazioni, vedere "Set di caratteri" nella [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).  
  
 Se non viene specificato alcun modificatore del set di caratteri, `Ansi` è il valore predefinito.  
  
## <a name="remarks"></a>Note  
 Il `Auto` modificatore può essere usato in questo contesto:  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Note per gli sviluppatori di Smart Device  
 Questa parola chiave non è supportata.  
  
## <a name="see-also"></a>Vedere anche

- [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)
- [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
