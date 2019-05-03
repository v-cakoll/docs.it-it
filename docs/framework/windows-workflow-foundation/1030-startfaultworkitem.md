---
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 3848d644e77041a62a52eb2eae5eeef286dfe334
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924319"
---
# <a name="1030---startfaultworkitem"></a>1030 - StartFaultWorkItem
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|1030|  
|Parole chiave|WFRuntime|  
|Livello|Dettagliato|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che viene avviata l'esecuzione di FaultWorkItem.  
  
## <a name="message"></a>Messaggio  
 Avvio dell'esecuzione di FaultWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.  Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|FaultActivity|xs:string|Il nome del tipo di attività fault.|  
|FaultActivityDisplayName|xs:string|Nome visualizzato dell'attività fault.|  
|FaultActivityInstanceId|xs:string|ID dell'istanza dell'attività fault.|  
|ExceptionActivity|xs:string|Il nome del tipo di attività che ha generato l'eccezione.|  
|ExceptionActivityDisplayName|xs:string|Il nome visualizzato dell'attività che ha generato l'eccezione.|  
|ExceptionActivityInstanceId|xs:string|ID dell'istanza dell'attività che ha generato l'eccezione.|  
|Eccezione|xs:string|Dettagli dell'eccezione.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
