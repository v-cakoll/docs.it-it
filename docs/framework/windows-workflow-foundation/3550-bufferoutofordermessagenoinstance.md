---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.date: 03/30/2017
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
ms.openlocfilehash: 1af943e23aa643c6614b946175c0b1854a7ceb62
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="3550---bufferoutofordermessagenoinstance"></a>3550 - BufferOutOfOrderMessageNoInstance
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|3550|  
|Parole chiave|WFServices|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Indica che un'operazione di ricezione memorizzata nel buffer non è riuscita. L'operazione verrà tentata nuovamente quando l'istanza del servizio sarà pronta per l'elaborazione di questa operazione specifica.  
  
## <a name="message"></a>Messaggio  
 Impossibile eseguire l'operazione '%1'. Verrà effettuato un altro tentativo quando l'istanza del servizio è pronta a elaborare questa operazione.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|OperationName|xs:string|Nome dell'operazione.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
