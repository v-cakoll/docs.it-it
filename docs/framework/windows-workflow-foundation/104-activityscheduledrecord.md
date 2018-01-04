---
title: 104 - ActivityScheduledRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae202178-8fb1-4646-a3aa-18beeda8ff93
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 78ce48c42fcac52be3b96a0782cb21266789ed20
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="104---activityscheduledrecord"></a>104 - ActivityScheduledRecord
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|104|  
|Parole chiave|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento viene creato dal partecipante del rilevamento ETW quando un'attività all'interno di un'istanza del flusso di lavoro crea l'oggetto ActivityScheduledRecord.  
  
## <a name="message"></a>Messaggio  
 TrackRecord = ActivityScheduledRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, Name = %4, ActivityId = %5, ActivityInstanceId = %6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = %10, ChildActivityTypeName =%11, Annotations=%12, ProfileName = %13  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|ID istanza del flusso di lavoro.|  
|RecordNumber|xs:long|Numero di sequenza del record creato.|  
|EventTime|xs:dateTime|Ora di creazione dell'evento in UTC.|  
|Nome|xs:string|Nome dell'attività che ha pianificato l'attività figlio.|  
|ActivityId|xs:string|ID dell'attività che ha pianificato l'attività figlio.|  
|ActivityInstanceId|xs:string|ID istanza dell'attività che ha pianificato l'attività figlio.|  
|ActivityTypeName|xs:string|Tipo di attività che ha richiesto l'operazione di annullamento.|  
|ChildActivityName|xs:string|Nome dell'attività pianificata.|  
|ChildActivityId|xs:string|ID dell'attività pianificata.|  
|ChildActivityInstanceId|xs:string|ID istanza dell'attività pianificata.|  
|ChildActivityTypeName|xs:string|Tipo dell'attività pianificata.|  
|Annotazioni|xs:string|Annotazioni aggiunte a questo evento.  I valori vengono archiviati in un elemento xml nel formato \<elementi >\< nome elemento = "Nomeannotazione" Type = "> Valoreannotazione\</item > \< /items >.  Se viene specificata alcuna annotazione, la stringa contiene \<elementi / >. La dimensione dell'evento ETW è limitata da quella del buffer ETW o dal payload massimo per un evento ETW. Se la dimensione dell'evento supera i limiti ETW, l'evento viene troncato eliminando le annotazioni e sostituendo il valore di annotazione con \<elementi >...  \< /items >.|  
|ProfileName|xs:string|Nome o profilo di rilevamento che ha determinato la creazione di questo evento.|  
|HostReference|xs:string|Per i servizi ospitati su Web questo campo identifica in modo univoco il servizio nella gerarchia Web.  Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; Nomeservizio ' esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
