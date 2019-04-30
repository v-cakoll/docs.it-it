---
title: 100 - WorkflowInstanceRecord
ms.date: 03/30/2017
ms.assetid: ed4d1851-b378-489b-a22d-c1db09571fb4
ms.openlocfilehash: c7abb2c59c65e0b0f4c4f209e3c7c2d0cf4641d7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008668"
---
# <a name="100---workflowinstancerecord"></a>100 - WorkflowInstanceRecord
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|100|  
|Parole chiave|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento viene creato dal partecipante del rilevamento ETW quando un'istanza del flusso di lavoro crea WorkflowInstanceRecord per gli stati del flusso di lavoro: Avviato, Resumed, Persisted, Idle, eliminati, completato, annullato, scaricata, la sospensione.  
  
## <a name="message"></a>Messaggio  
 TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|ID istanza del flusso di lavoro.|  
|RecordNumber|xs:long|Numero di sequenza del record creato.|  
|EventTime|xs:dateTime|Ora di creazione dell'evento in UTC.|  
|ActivityDefinitionId|xs:string|Nome dell'attività radice nel flusso di lavoro.|  
|Stato|xs:string|Stato corrente del flusso di lavoro.|  
|Annotazioni|xs:string|Annotazioni aggiunte a questo evento.  I valori vengono archiviati in un elemento xml nel formato \<gli elementi >\< nome elemento = "Nomeannotazione" Type = "> Valoreannotazione\</item > \< /items >.  Se viene specificata alcuna annotazione, la stringa contiene \<elementi / >. La dimensione dell'evento ETW è limitata da quella del buffer ETW o dal payload massimo per un evento ETW. Se la dimensione dell'evento supera i limiti ETW, quindi l'evento viene troncato eliminando le annotazioni e sostituendo il valore dell'annotazione con \<elementi >...  \< /items >.|  
|ProfileName|xs:string|Nome o profilo di rilevamento che ha determinato la creazione di questo evento.|  
|HostReference|xs:string|Per i servizi ospitati su Web questo campo identifica in modo univoco il servizio nella gerarchia Web.  Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;nomeservizio ' esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
