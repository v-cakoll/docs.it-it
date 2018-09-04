---
title: Record di rilevamento personalizzati
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: ef3c20890f33f3ffd07a9c88de863e1ebe24851f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43520185"
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
 [Monitoraggio dell'infrastruttura di App di Windows Server](https://go.microsoft.com/fwlink/?LinkId=201273)  
 [Monitoraggio delle applicazioni con App Fabric](https://go.microsoft.com/fwlink/?LinkId=201275)
