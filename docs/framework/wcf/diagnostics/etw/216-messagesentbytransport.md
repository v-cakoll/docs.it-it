---
title: 216 - MessageSentByTransport
ms.date: 03/30/2017
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
ms.openlocfilehash: fa21568e4c8c38eefe359c417d47ec0a9d30a7c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458683"
---
# <a name="216---messagesentbytransport"></a>216 - MessageSentByTransport
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|216|  
|Parole chiave|Troubleshooting, ServiceModel|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento si verifica nel caso in cui un trasporto basato su TCP invia un messaggio. A livello di trasporto è possibile scambiare più messaggi tra client e servizi per una sola operazione. Ciò può essere dovuto a un comportamento dell'infrastruttura (un esempio valido può essere rappresentato dalla sicurezza). Pertanto, il numero di **MessageSentByTransport** gli eventi generati variano in base all'associazione del servizio e la relativa configurazione.  
  
## <a name="message"></a>Messaggio  
 Il trasporto ha inviato un messaggio a '%1'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|DestinationAddress|`xs:string`|L'indirizzo a cui è stato inviato il messaggio di richiesta.|  
|HostReference|xs:string|Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web. Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso&#124;percorso virtuale servizio&#124;nomeservizio '. Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
