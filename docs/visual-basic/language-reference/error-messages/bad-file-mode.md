---
title: Modalità file non valida
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: 534ea2d8316dc29cace798c5ad9b7697a290026f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409869"
---
# <a name="bad-file-mode"></a>Modalità file non valida
Le istruzioni utilizzate per manipolare il contenuto del file devono essere appropriate per la modalità in cui il file è stato aperto. Le cause possibili includono:  
  
- Un' `FilePutObject` `FileGetObject` istruzione o specifica un file sequenziale.  
  
- Un' `Print` istruzione specifica un file aperto per una modalità di accesso diversa da `Output` o `Append` .  
  
- Un' `Input` istruzione specifica un file aperto per una modalità di accesso diversa da`Input`  
  
- Tentativo di scrittura in un file di sola lettura.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Assicurarsi `FilePutObject` che e facciano `FileGetObject` riferimento solo ai file aperti per `Random` `Binary` l'accesso o.  
  
- Assicurarsi `Print` di specificare un file aperto per la `Output` `Append` modalità di accesso o. In caso contrario, utilizzare un'istruzione diversa per inserire i dati nel file o riaprire il file in una modalità appropriata.  
  
- Assicurarsi `Input` di specificare un file aperto per `Input` . In caso contrario, utilizzare un'istruzione diversa per inserire i dati nel file o riaprire il file in una modalità appropriata.  
  
- Se si sta scrivendo in un file di sola lettura, modificare lo stato di lettura/scrittura del file o non tentare di scrivervi.  
  
- Usare la funzionalità disponibile nell'oggetto `My.Computer.FileSystem` .  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileSystem>
- [Risoluzione dei problemi: Lettura e scrittura nei file di testo](../../developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
