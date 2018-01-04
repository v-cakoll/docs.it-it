---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cf90e78ed7fbfe500ac52e6629d31bd0aff97bd8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a>3552 - MaxPendingMessagesPerChannelExceeded
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|3552|  
|Parole chiave|Quota, WFServices|  
|Livello|Avviso|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Indica che è stato raggiunto il limite per la velocità 'MaxPendingMessagesPerChannel'.  
  
## <a name="message"></a>Messaggio  
 È stato raggiunto il limite velocità 'MaxPendingMessagesPerChannel' di '%1'. Per aumentare questo limite, modificare la proprietà MaxPendingMessagesPerChannel in BufferedReceiveServiceBehavior.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Limit|xs:string|È stato raggiunto il limite per la velocità MaxPendingMessagesPerChannel.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
