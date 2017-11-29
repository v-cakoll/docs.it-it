---
title: 1031 - CompleteFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 260647b56d945600afea5609f06d36385fa66014
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1031---completefaultworkitem"></a>1031 - CompleteFaultWorkItem
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|1031|  
|Parole chiave|WFRuntime|  
|Livello|Dettagliato|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che FaultWorkItem è completato.  
  
## <a name="message"></a>Messaggio  
 FaultWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'. Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.  
  
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
