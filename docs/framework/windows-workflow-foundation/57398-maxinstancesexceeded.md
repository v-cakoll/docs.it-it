---
title: 57398 - MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: d644c25ec2dee06eea4a5fb66c30792bb650f252
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945964"
---
# <a name="57398---maxinstancesexceeded"></a>57398 - MaxInstancesExceeded
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|57398|  
|Parole chiave|WFServices|  
|Livello|Avviso|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Indica che il sistema ha raggiunto il limite impostato per la velocità 'MaxConcurrentInstances'.  
  
## <a name="message"></a>Messaggio  
 Il sistema ha raggiunto il limite impostato per la velocità 'MaxConcurrentInstances'. Il limite per questa velocità è stato impostato su %1. Il valore della velocità può essere modificato cambiando l'attributo 'maxConcurrentInstances' nell'elemento serviceThrottle o modificando la proprietà 'MaxConcurrentInstances' nel comportamento ServiceThrottlingBehavior.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Nome|xs:string|Nome dell'elemento.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
