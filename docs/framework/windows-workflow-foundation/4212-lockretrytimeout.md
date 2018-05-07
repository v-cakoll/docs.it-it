---
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 9b7a463851d380eba1ef7b28fbc6decd0cfc979c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
