---
title: Impossibile scrivere nel file di log. Lo spazio libero su disco risulterebbe inferiore al valore ReservedSpace
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ReservedSpaceEncroached
ms.assetid: 95832e70-4ecc-47aa-90c1-f35c4d468151
ms.openlocfilehash: 38cba8c01741196de9c316ed137acf750add9e89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022532"
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-reduce-free-disk-space-below-reservedspace-value"></a>Impossibile scrivere nel file di log. Lo spazio libero su disco risulterebbe inferiore al valore ReservedSpace
La classe <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> non è riuscita a scrivere nel file di log perché:  
  
- La quantità di spazio disponibile su disco (in byte) è minore del valore della proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A>   
  
     e  
  
- Il valore della proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> è <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Archiviare i log esistenti e rimuoverli dal computer per consentire all'oggetto <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> di creare nuovi log.  
  
2. Modificare il valore della proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> impostando un numero inferiore per riservare meno spazio su disco.  
  
3. Impostare la proprietà <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> su <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> per eliminare i messaggi senza avviso se lo spazio disponibile su disco è insufficiente.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [My.Application.Log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [My.Application.Info.DirectoryPath](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
