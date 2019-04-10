---
title: Impossibile scrivere nel file di log. Verrebbe superato il valore MaximumSize
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_FileExceedsMaximumSize
ms.assetid: 61747a9c-e460-424b-a365-73cdba9dd428
ms.openlocfilehash: 587b35282c7e78da1fdf4ccf9d08214e5665119c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59298604"
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-cause-it-to-exceed-maximumsize-value"></a>Impossibile scrivere nel file di log. Verrebbe superato il valore MaximumSize
La classe <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> non è riuscita a scrivere nel file di log perché:  
  
-   La dimensione del file di log (in byte) è maggiore rispetto al valore della proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>   
  
     e  
  
-   Il valore della proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> è <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Archiviare i log esistenti e rimuoverli dal computer per consentire all'oggetto <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> di creare nuovi log.  
  
2. Modificare il valore della proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> per consentire log di dimensioni maggiori.  
  
3. Impostare la proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> su <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> per eliminare i messaggi senza avviso se il log è troppo grande.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [My.Application.Log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [My.Application.Info.DirectoryPath](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
