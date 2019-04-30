---
title: 111 - CustomTrackingRecordError
ms.date: 03/30/2017
ms.assetid: d469fb12-e094-4d6c-9b4d-abd7ce0d17da
ms.openlocfilehash: 737d48714020e20fc7b864de4e650ae234a8580e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009760"
---
# <a name="111---customtrackingrecorderror"></a>111 - CustomTrackingRecordError
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|111|  
|Parole chiave|UserEvents, EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|Livello|Error|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento viene creato dal partecipante del rilevamento ETW quando un'attività all'interno di un'istanza del flusso di lavoro crea CustomTrackingRecord con errore di livello.  
  
## <a name="message"></a>Messaggio  
 TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|ID istanza del flusso di lavoro.|  
|RecordNumber|xs:long|Numero di sequenza del record creato.|  
|EventTime|xs:dateTime|Ora di creazione dell'evento in UTC.|  
|Nome|xs:string|Nome dell'oggetto CustomTrackingRecord.|  
|ActivityName|xs:string|Nome dell'attività che ha creato l'oggetto CustomTrackingRecord.|  
|ActivityId|xs:string|ID dell'attività che ha creato l'oggetto CustomTrackingRecord.|  
|ActivityInstanceId|xs:string|ID istanza dell'attività che ha creato l'oggetto CustomTrackingRecord.|  
|ActivityTypeName|xs:string|Nome dell'attività che ha creato l'oggetto CustomTrackingRecord.|  
|Dati|xs:string|Dati rilevati con questo evento.  I valori vengono archiviati in un elemento xml nel formato \<gli elementi >\< nome elemento = "Nomedati" Type = "> Valorevalore\</item > \< /items >.  Se è stato rilevato alcun dato, la stringa contiene \<elementi / >. La dimensione dell'evento ETW è limitata da quella del buffer ETW o dal payload massimo per un evento ETW. Se la dimensione dell'evento supera i limiti ETW, quindi l'evento viene troncato eliminando le annotazioni e sostituendo il valore dei dati con \<elementi >...  \< /items >.  I tipi seguenti vengono archiviati come i relativi valori quando restituiti da ToString(); string,char,bool,int,short,long,uint,ushort,ulong,System.Single,float,double,System.Guid,System.DateTimeOffset,System.DateTime.  Tutti gli altri tipi sono serializzati usando System.Runtime.Serialization.NetDataContractSerializer.|  
|Annotazioni|xs:string|Annotazioni aggiunte a questo evento.  I valori vengono archiviati in un elemento xml nel formato \<gli elementi >\< nome elemento = "Nomeannotazione" Type = "> Valoreannotazione\</item > \< /items >.  Se viene specificata alcuna annotazione, la stringa contiene \<elementi / >. La dimensione dell'evento ETW è limitata da quella del buffer ETW o dal payload massimo per un evento ETW. Se la dimensione dell'evento supera i limiti ETW, quindi l'evento viene troncato eliminando le annotazioni e sostituendo il valore dell'annotazione con \<elementi >...  \< /items >.|  
|ProfileName|xs:string|Nome o profilo di rilevamento che ha determinato la creazione di questo evento.|  
|HostReference|xs:string|Per i servizi ospitati su Web questo campo identifica in modo univoco il servizio nella gerarchia Web.  Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;nomeservizio ' esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
