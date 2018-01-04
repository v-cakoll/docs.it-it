---
title: 4203 - RenewLockSystemError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8fabe6f2c023bf9b997d2a4e19b4a3755c93f408
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="4203---renewlocksystemerror"></a>4203 - RenewLockSystemError
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|4203|  
|Parole chiave|WFInstanceStore|  
|Livello|Errore|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che il provider SQL non è in grado di estendere la scadenza del blocco perché la scadenza è già passata o il proprietario del blocco è stato eliminato. SqlWorkflowInstanceStore verrà interrotto.  
  
## <a name="message"></a>Messaggio  
 Impossibile estendere la scadenza del blocco. Scadenza già passata o proprietario del blocco eliminato. Interruzione di SqlWorkflowInstanceStore in corso.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
