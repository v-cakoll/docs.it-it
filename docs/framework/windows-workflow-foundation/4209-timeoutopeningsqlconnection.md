---
title: 4209 - TimeoutOpeningSqlConnection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7528c967cbd88f00af448d6163c10e807f603bc6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="4209---timeoutopeningsqlconnection"></a>4209 - TimeoutOpeningSqlConnection
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|4209|  
|Parole chiave|WFInstanceStore|  
|Livello|Errore|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che è stato rilevato un timeout durante il tentativo di stabilire una connessione SQL.  
  
## <a name="message"></a>Messaggio  
 Timeout durante il tentativo di aprire una connessione SQL. Operazione non completata entro il timeout assegnato di %1. È possibile che la durata consentita per l'operazione fosse una porzione di un timeout più lungo.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Timeout|xs:string|Valore di timeout per l'apertura della connessione SQL.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
