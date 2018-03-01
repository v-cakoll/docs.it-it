---
title: Unicode (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 042908b8427de2de0de96bbb32df7be018bb915c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="unicode-visual-basic"></a>Unicode (Visual Basic)
Specifica che Visual Basic deve eseguire il marshalling di tutte le stringhe in valori Unicode indipendentemente dal nome della routine esterna che viene dichiarato.  
  
 Quando si chiama una routine definita all'esterno del progetto, il compilatore Visual Basic non hanno accesso alle informazioni è necessario per chiamare correttamente la routine. Queste informazioni includono la procedura in cui si trova, come viene identificato, la sequenza di chiamata e tipo restituito e il set di caratteri stringa viene utilizzata. Il [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md) crea un riferimento a una routine esterna e fornisce le informazioni necessarie.  
  
 Il `charsetmodifier` parte il `Declare` istruzione fornisce le informazioni sul set di caratteri per il marshalling di stringhe durante una chiamata alla routine esterna. Influisce anche sulle modalità di ricerca di file esterno per il nome della routine esterna. Il `Unicode` modificatore specifica che Visual Basic deve eseguire il marshalling di tutte le stringhe in valori Unicode e cercare la routine senza modificarne il nome durante la ricerca.  
  
 Se non viene specificato alcun modificatore del set di caratteri, `Ansi` è l'impostazione predefinita.  
  
## <a name="remarks"></a>Note  
 Il `Unicode` modificatore può essere utilizzato in questo contesto:  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Note per gli sviluppatori di Smart Device  
 Questa parola chiave non è supportata.  
  
## <a name="see-also"></a>Vedere anche  
 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)  
 [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
