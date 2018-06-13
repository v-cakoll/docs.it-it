---
title: Record di rilevamento personalizzati
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: 6c68c08e5beacee30b517bf0c2bad3e83785409b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511335"
---
# <a name="custom-tracking-records"></a>Record di rilevamento personalizzati
In questo argomento viene illustrato come creare record di rilevamento personalizzati e come popolarli con dati da creare insieme ai record.  
  
## <a name="emitting-custom-tracking-records"></a>Creazione di record di rilevamento personalizzati  
 I record di rilevamento personalizzati possono essere creati da un'attività del codice come illustrato nell'esempio seguente.  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
…  
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");  
            customRecord.Data.Add("SendTime", sendTime);  
            context.Track(customRecord);  
}  
```  
  
 Un oggetto <xref:System.Activities.Tracking.CustomTrackingRecord> viene creato in un'attività del codice richiamando il metodo <xref:System.Activities.NativeActivityContext.Track%2A> su `ActvityContext`.  
  
## <a name="see-also"></a>Vedere anche  
 [Monitoraggio dell'infrastruttura di App di Windows Server](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [Monitoraggio delle applicazioni con App Fabric](http://go.microsoft.com/fwlink/?LinkId=201275)
