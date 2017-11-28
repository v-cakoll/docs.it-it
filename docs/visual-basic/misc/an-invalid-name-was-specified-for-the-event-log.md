---
title: "È stato specificato un nome non valido per il log eventi"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fc5a2e93541063a129efaa0ce08fc19a98372126
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a>È stato specificato un nome non valido per il log eventi
È stato specificato un nome non valido per il log eventi. Generalmente è l'effetto della presenza di caratteri non validi nel nome, di un nome file vuoto o di un nome file troppo lungo.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se la lunghezza del nome specificato supera otto caratteri, accertarsi che non vi sia un conflitto con i nomi di altri log eventi. Quando si determina se il nome è univoco vengono presi in considerazione solo i primi otto caratteri.  
  
-   Se si fornisce un percorso, accertarsi che venga analizzato correttamente.  
  
-   Verificare che il nome non contenga caratteri non validi. I caratteri che non è possibile usare in un nome file comprendono `<`, `>`, `:`, `"`, `/`, `\`e `|`.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: analizzare percorsi di file](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)  
 [Procedura: rinominare un file](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)  
 [Procedura: creare e rimuovere i log eventi personalizzati](http://msdn.microsoft.com/en-us/af9b7da0-80c7-46ac-b7f7-897063ddd503)
