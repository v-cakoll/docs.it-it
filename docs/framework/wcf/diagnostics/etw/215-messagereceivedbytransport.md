---
title: 215 - MessageReceivedByTransport
ms.date: 03/30/2017
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
ms.openlocfilehash: aa1ad30526aa65501e5d9875d3877631ca00879b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964179"
---
# <a name="215---messagereceivedbytransport"></a>215 - MessageReceivedByTransport
## <a name="properties"></a>Properties  
  
|||  
|-|-|  
|id|215|  
|Parole chiave|Troubleshooting, ServiceModel|  
|Level|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento si verifica quando un trasporto basato su TCP riceve un messaggio. Si noti che a livello di trasporto è possibile che si verifichi lo scambio di più messaggi tra client e servizi per una singola operazione. Questo può dipendere dal comportamento dell'infrastruttura (un esempio valido può essere rappresentato dalla sicurezza). Pertanto, il numero di eventi `MessageReceivedByTransport` generati varia in base all'associazione del servizio e alla relativa configurazione.  
  
> [!NOTE]
> Questo evento non viene generato per i trasporti unidirezionali.  
  
## <a name="message"></a>Messaggio  
 Il trasporto ha ricevuto un messaggio da '%1'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Indirizzo di ascolto|`xs:string`|Indirizzo che riceve il messaggio.|  
|HostReference|`xs:string`|Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web. Il formato è definito come ' nome sito Web dell'applicazione percorso&#124;virtuale servizio&#124;percorso virtuale servizio '. Esempio: ' Default Web site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
