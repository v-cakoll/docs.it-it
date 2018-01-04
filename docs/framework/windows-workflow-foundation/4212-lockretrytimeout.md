---
title: 4212 - LockRetryTimeout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f47b383547da5145c5307670fee2eda10fcab402
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="4212---lockretrytimeout"></a>4212 - LockRetryTimeout
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|4212|  
|Parole chiave|WFInstanceStore|  
|Livello|Avviso|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Timeout rilevato del provider SQL durante il tentativo di acquisire il blocco di istanza.  
  
## <a name="message"></a>Messaggio  
 Timeout durante il tentativo di acquisire il blocco di istanza.  Operazione non completata entro il timeout assegnato di %1. È possibile che la durata consentita per l'operazione fosse una porzione di un timeout più lungo.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Delay|xs:string|Il ritardo tra i tentativi.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
