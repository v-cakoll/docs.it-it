---
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: d61d710959f99dbc8a91441766a690eb7e9a365c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774270"
---
# <a name="4209---timeoutopeningsqlconnection"></a>4209 - TimeoutOpeningSqlConnection
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|4209|  
|Parole chiave|WFInstanceStore|  
|Livello|Error|  
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
