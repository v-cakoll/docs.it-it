---
title: Modalità file non valida
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: d3d0ebd003f178567ec9e9b19d6baccb8bc15f60
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935239"
---
# <a name="bad-file-mode"></a>Modalità file non valida
Istruzioni utilizzate nella manipolazione di contenuto del file devono essere appropriate per la modalità in cui è stato aperto il file. Fra le cause possibili vi sono le seguenti:  
  
- Oggetto `FilePutObject` o `FileGetObject` istruzione specifica un file sequenziale.  
  
- Oggetto `Print` istruzione specifica un file aperto per la modalità di accesso diverso da `Output` o `Append`.  
  
- Un `Input` istruzione specifica un file aperto per la modalità di accesso diverso da `Input`  
  
- Un tentativo di scrivere in un file di sola lettura.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Assicurarsi che `FilePutObject` e `FileGetObject` facciano riferimento solo a file aperti per `Random` o `Binary` accesso.  
  
- Assicurarsi che `Print` specifica un file aperto per la `Output` o `Append` modalità di accesso. In caso contrario, utilizzare un'istruzione diversi per inserire dati nel file o riaprire il file in una modalità appropriata.  
  
- Assicurarsi che `Input` specifica un file aperto per `Input`. In caso contrario, utilizzare un'istruzione diversi per inserire dati nel file o riaprire il file in una modalità appropriata.  
  
- Se si scrive in un file di sola lettura, modificare lo stato di lettura/scrittura del file o non tentare di scrivervi.  
  
- Usare la funzionalità disponibile nell'oggetto `My.Computer.FileSystem` .  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileSystem>
- [Risoluzione dei problemi: Lettura e scrittura nei file di testo](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
