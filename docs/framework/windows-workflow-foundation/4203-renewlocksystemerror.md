---
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 984f7ddae8797cba17753a618d0820d21bde5eef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
