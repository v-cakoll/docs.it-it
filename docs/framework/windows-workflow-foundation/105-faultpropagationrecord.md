---
title: 105 - FaultPropagationRecord
ms.date: 03/30/2017
ms.assetid: 168473b1-b1e5-4e9f-8a2a-35bbdb2ef531
ms.openlocfilehash: c48f42a91ad9a15b49aad8c1ab684f2348954174
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="105---faultpropagationrecord"></a>105 - FaultPropagationRecord
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|105|  
|Parole chiave|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|Livello|Avviso|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento viene creato dal partecipante del rilevamento ETW quando un'attività con l'istanza del flusso di lavoro crea l'oggetto FaultPropagationRecord.  
  
## <a name="message"></a>Messaggio  
 TrackRecord = FaultPropagationRecord, InstanceID=%1, RecordNumber=%2, EventTime=%3, FaultSourceActivityName=%4, FaultSourceActivityId=%5, FaultSourceActivityInstanceId=%6, FaultSourceActivityTypeName=%7, FaultHandlerActivityName=%8, FaultHandlerActivityId = %9, FaultHandlerActivityInstanceId =%10, FaultHandlerActivityTypeName=%11, Fault=%12, IsFaultSource=%13, Annotations=%14, ProfileName = %15  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|ID istanza del flusso di lavoro.|  
|RecordNumber|xs:long|Numero di sequenza del record creato.|  
|EventTime|xs:dateTime|Ora di creazione dell'evento in UTC.|  
|FaultSourceActivityName|xs:string|Nome dell'attività che ha creato l'errore.|  
|FaultSourceActivityId|xs:string|ID dell'attività che ha creato l'errore.|  
|FaultSourceActivityInstanceId|xs:string|ID istanza dell'attività che ha creato l'errore.|  
|FaultSourceActivityTypeName|xs:string|Tipo dell'attività che ha creato l'errore.|  
|FaultHandlerActivityName|xs:string|Nome visualizzato dell'attività del gestore fault.|  
|FaultHandlerActivityId|xs:string|ID dell'attività del gestore fault.|  
|FaultHandlerActivityInstanceId|xs:string|ID istanza dell'attività del gestore fault.|  
|FaultHandlerActivityTypeName|xs:string|Tipo dell'attività del gestore fault.|  
|Fault|xs:string|Dettagli dell'errore.|  
|IsFaultSource|xs:unsignedByte|Indica se l'evento è stato creato dall'origine dell'errore.|  
|Annotazioni|xs:string|Annotazioni aggiunte a questo evento.  I valori vengono archiviati in un elemento xml nel formato \<elementi >\< nome elemento = "Nomeannotazione" Type = "> Valoreannotazione\</item > \< /items >.  Se viene specificata alcuna annotazione, la stringa contiene \<elementi / >. La dimensione dell'evento ETW è limitata da quella del buffer ETW o dal payload massimo per un evento ETW. Se la dimensione dell'evento supera i limiti ETW, l'evento viene troncato eliminando le annotazioni e sostituendo il valore di annotazione con \<elementi >...  \< /items >.|  
|ProfileName|xs:string|Nome o profilo di rilevamento che ha determinato la creazione di questo evento.|  
|HostReference|xs:string|Per i servizi ospitati su Web questo campo identifica in modo univoco il servizio nella gerarchia Web.  Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso&#124;percorso virtuale servizio&#124;nomeservizio ' esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
