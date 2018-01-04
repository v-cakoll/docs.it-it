---
title: 'Comunicazioni principali: framework di connessione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61ee00e1-896d-47c8-942f-1db28ac89cdc
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 713788f8938e43f3516edd95646fc6dc653a56c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="core-communications-connection-framework"></a>Comunicazioni principali: framework di connessione
In questo argomento vengono elencate tutte le eccezioni generate dal framework di connessione di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## <a name="exception-list"></a>Elenco delle eccezioni  
  
|Codice risorsa|Stringa di risorsa|  
|-------------------|---------------------|  
|CloseTimedOut|Si è verificato il timeout del metodo Close. Aumentare il valore di timeout passato al metodo Close o aumentare il valore CloseTimeout dell'associazione. È possibile che la durata consentita per l'operazione fosse una porzione di un timeout più lungo.|  
|ContentTypeMismatch|Il tipo di contenuto specificato che è stato inviato al servizio non corrisponde al tipo che quest'ultimo prevede di ricevere. È possibile che le associazioni di client e servizio non corrispondano fra loro.|  
|DuplexChannelAbortedDuringOpen|Il canale duplex per l'elemento specificato è stato interrotto durante il processo di apertura.|  
|FramingValueNotAvailable|Non è possibile accedere al valore in quanto quest'ultimo non è stato decodificato in modo completo.|  
|OperationAbortedDuringConnectionEstablishment|L'operazione è stata interrotta durante il tentativo di connessione all'elemento specificato.|  
|ReceiveTimedOut2|L'operazione di ricezione è scaduta dopo il tempo specificato. È possibile che la durata consentita per l'operazione fosse una porzione di un timeout più lungo.|  
|SendCannotBeCalledAfterCloseOutputSession|Non è possibile inviare messaggi su un canale dopo aver chiamato il metodo CloseOutputSession.|
