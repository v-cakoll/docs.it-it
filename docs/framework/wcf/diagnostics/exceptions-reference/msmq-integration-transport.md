---
title: Trasporto di integrazione MSMQ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2bf9893a-fbd1-41fc-b6de-a41a44279936
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 18dd1262c572a7e8844d9fe2beb5de7f52c28e1e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="msmq-integration-transport"></a>Trasporto di integrazione MSMQ
In questo argomento vengono elencate tutte le eccezioni generate dal trasporto di integrazione MSMQ.  
  
## <a name="exception-list"></a>Elenco delle eccezioni  
  
|Codice risorsa|Stringa di risorsa|  
|-------------------|---------------------|  
|MessageSizeMustBeInIntegerRange|Questa factory memorizza nel buffer i messaggi, le cui dimensioni, pertanto, devono rientrare nell'intervallo di un valore integer.|  
|MsmqByteArrayBodyExpected|Si è verificata una mancata corrispondenza tra il formato di serializzazione specificato e il corpo del messaggio MSMQ. Impossibile inviare o ricevere il messaggio. Il formato di serializzazione ByteArray richiede che il corpo del messaggio MSMQ sia di tipo byte[].|  
|MsmqCannotDeserializeActiveXMessage|Si è verificato un errore di serializzazione ActiveX. Impossibile inviare o ricevere il messaggio. Il tipo di variante specificato per il corpo non corrisponde al corpo effettivo del messaggio MSMQ.|  
|MsmqCannotUseBodyTypeWithActiveXSerialization|Le proprietà del messaggio non corrispondono. Impossibile inviare o ricevere il messaggio. Impossibile specificare la proprietà del messaggio BodyType se si utilizza il formato di serializzazione ActiveX.|  
|MsmqInvalidServiceOperationForMsmqIntegrationBinding|La convalida di MsmqIntegrationBinding non è riuscita. Impossibile avviare l'endpoint del servizio. L'associazione specificata non supporta la firma del metodo per l'operazione del servizio specificata nel contratto specificato. Correggere l'operazione del servizio per utilizzare MsmqIntegrationBinding.|  
|MsmqInvalidTypeDeserialization|La serializzazione ActiveX non è riuscita perché è impossibile riconoscere il formato di serializzazione. Impossibile inviare o ricevere il messaggio.|  
|MsmqInvalidTypeSerialization|Il tipo di variante non è riconosciuto. La serializzazione ActiveX non è riuscita. Impossibile inviare o ricevere il messaggio. Il tipo di variante specificato non è supportato.|  
|MsmqStreamBodyExpected|Mancata corrispondenza tra formato di serializzazione e contenuto del corpo. Impossibile inviare o ricevere il messaggio. Utilizzando la modalità di serializzazione del flusso, è possibile inviare o ricevere solo un corpo di tipo Stream.|
