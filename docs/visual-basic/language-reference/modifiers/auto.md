---
title: Auto (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1e32c4c910567829a4f5c59b48020db4dfbbeb7b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="auto-visual-basic"></a>Auto (Visual Basic)
Specifica che Visual Basic deve eseguire il marshalling di stringhe in base alle regole di .NET Framework in base al nome esterno della routine esterna che viene dichiarato.  
  
 Quando si chiama una routine definita all'esterno del progetto, il compilatore Visual Basic non hanno accesso alle informazioni necessari per chiamare correttamente la routine. Queste informazioni includono la procedura in cui si trova, come viene identificato, la sequenza di chiamata e tipo restituito e il set di caratteri stringa viene utilizzata. Il [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md) crea un riferimento a una routine esterna e fornisce le informazioni necessarie.  
  
 Il `charsetmodifier` parte il `Declare` istruzione fornisce le informazioni sul set di caratteri per il marshalling di stringhe durante una chiamata alla routine esterna. Influisce anche sulle modalità di ricerca di file esterno per il nome della routine esterna. Il `Auto` modificatore specifica che Visual Basic deve eseguire il marshalling di stringhe in base alle regole di .NET Framework e che è necessario determinare il carattere di base impostato della piattaforma in fase di esecuzione ed eventualmente modificare il nome della routine esterna se esegue la ricerca iniziale ha esito negativo. Per ulteriori informazioni, vedere "Set di caratteri" in [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md).  
  
 Se non viene specificato alcun modificatore del set di caratteri, `Ansi` è l'impostazione predefinita.  
  
## <a name="remarks"></a>Note  
 Il `Auto` modificatore può essere utilizzato in questo contesto:  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Note per gli sviluppatori di Smart Device  
 Questa parola chiave non è supportata.  
  
## <a name="see-also"></a>Vedere anche  
 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)  
 [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
