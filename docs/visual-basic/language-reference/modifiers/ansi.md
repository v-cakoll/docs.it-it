---
title: Ansi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: c7037acac58de56a396bd89f595ef897743ff4e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595079"
---
# <a name="ansi-visual-basic"></a>Ansi (Visual Basic)
Specifica che Visual Basic deve eseguire il marshalling di tutte le stringhe in valori American National Standards Institute (ANSI) indipendentemente dal nome della routine esterna che viene dichiarato.  
  
 Quando si chiama una routine definita all'esterno del progetto, il compilatore Visual Basic non hanno accesso alle informazioni necessarie per chiamare correttamente la routine. Queste informazioni includono la procedura in cui si trova, come viene identificato, la sequenza di chiamata e tipo restituito e il set di caratteri stringa viene utilizzata. Il [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md) crea un riferimento a una routine esterna e fornisce le informazioni necessarie.  
  
 Il `charsetmodifier` parte il `Declare` istruzione fornisce le informazioni sul set di caratteri per il marshalling di stringhe durante una chiamata alla routine esterna. Influisce anche sulle modalità di ricerca di file esterno per il nome della routine esterna. Il `Ansi` modificatore specifica che Visual Basic deve eseguire il marshalling di tutte le stringhe in valori ANSI e cercare la routine senza modificarne il nome durante la ricerca.  
  
 Se non viene specificato alcun modificatore del set di caratteri, `Ansi` è l'impostazione predefinita.  
  
## <a name="remarks"></a>Note  
 Il `Ansi` modificatore può essere utilizzato in questo contesto:  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Note per gli sviluppatori di Smart Device  
 Questa parola chiave non è supportata.  
  
## <a name="see-also"></a>Vedere anche  
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)  
 [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)  
 [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
