---
title: Impossibile scrivere nel file di log. Verrebbe superato il valore MaximumSize
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_FileExceedsMaximumSize
ms.assetid: 61747a9c-e460-424b-a365-73cdba9dd428
ms.openlocfilehash: 170612dfc294f3d2326ad34216f699cf4af6cdb0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554660"
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-cause-it-to-exceed-maximumsize-value"></a>Impossibile scrivere nel file di log. Verrebbe superato il valore MaximumSize
La classe <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> non è riuscita a scrivere nel file di log perché:  
  
-   La dimensione del file di log (in byte) è maggiore rispetto al valore della proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>   
  
     e  
  
-   Il valore della proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> è <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Archiviare i log esistenti e rimuoverli dal computer per consentire all'oggetto <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> di creare nuovi log.  
  
2.  Modificare il valore della proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> per consentire log di dimensioni maggiori.  
  
3.  Impostare la proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> su <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> per eliminare i messaggi senza avviso se il log è troppo grande.  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [My.Application.Log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [My.Application.Info.DirectoryPath](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
