---
title: "Modalità file non valida"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a540135727eb97f4df5027e2ded7271e21bb4648
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-mode"></a>Modalità file non valida
Le istruzioni utilizzate nella modifica dei contenuti del file devono essere appropriate per la modalità in cui è stato aperto il file. Fra le cause possibili vi sono le seguenti:  
  
-   Oggetto `FilePutObject` o `FileGetObject` istruzione specifica un file sequenziale.  
  
-   Oggetto `Print` istruzione specifica un file aperto in modalità di accesso diverso da `Output` o `Append`.  
  
-   Un `Input` istruzione specifica un file aperto in modalità di accesso diverso da`Input`  
  
-   Tentativo di scrivere in un file di sola lettura.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Assicurarsi che `FilePutObject` e `FileGetObject` facciano riferimento solo a file aperti per `Random` o `Binary` accesso.  
  
-   Assicurarsi che `Print` specifica un file aperto per la `Output` o `Append` modalità di accesso. In caso contrario, utilizzare un'istruzione diversa per inserire dati nel file o riaprire il file in una modalità appropriata.  
  
-   Assicurarsi che `Input` specifica un file aperto per `Input`. In caso contrario, utilizzare un'istruzione diversa per inserire dati nel file o riaprire il file in una modalità appropriata.  
  
-   Se si scrive in un file di sola lettura, modificare lo stato di lettura/scrittura del file o non tentare di scrivervi.  
  
-   Usare la funzionalità disponibile nell'oggetto `My.Computer.FileSystem` .  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.FileSystem>  
 [Risoluzione dei problemi: lettura e scrittura nei file di testo](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
