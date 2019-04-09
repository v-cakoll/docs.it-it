---
title: Uso di WS-AtomicTransaction
ms.date: 03/30/2017
helpviewer_keywords:
- WS-AT protocol [WCF]
ms.assetid: 04a4c200-0af0-4c5d-a3d9-87cb7339e054
ms.openlocfilehash: 8a8265873e4287e1455659aa4d9fae7e1d570a00
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165483"
---
# <a name="using-ws-atomictransaction"></a>Uso di WS-AtomicTransaction
WS-AtomicTransaction (WS-AT) è un protocollo di transazione interoperativo. Consente di propagare transazioni distribuite utilizzando i messaggi dei servizi Web e di eseguire il coordinamento in modo interoperativo tra infrastrutture di transazioni eterogenee. WS-AT utilizza il protocollo di commit a due fasi per condurre un risultato atomico tra applicazioni distribuite, gestori di transazioni e gestori di risorse.  
  
 L'implementazione di WS-AT fornisce Windows Communication Foundation (WCF) include un servizio di protocollo incorporato nel gestore di transazioni Microsoft Distributed Transaction Coordinator (MSDTC). Usa WS-AT, le applicazioni WCF possono propagare transazioni alle altre applicazioni, tra cui servizi Web interoperativi creati mediante la tecnologia di terze parti.  
  
 Durante la propagazione di una transazione tra un'applicazione client e un'applicazione server, il protocollo di transazione utilizzato viene determinato dall'associazione esposta dal server sull'endpoint selezionato dal client. Alcuni specificano per impostazione predefinita le associazioni fornite dal sistema WCF il `OleTransactions` protocollo come il formato di propagazione delle transazioni, mentre altre specificando WS-AT. La scelta del protocollo di transazione può anche essere modificata a livello di codice all'interno di una determinata associazione.  
  
 La scelta del protocollo influisce sugli elementi seguenti:  
  
-   Formato delle intestazioni dei messaggi utilizzate propagare la transazione dal client al server.  
  
-   Protocollo di rete utilizzato per eseguire il protocollo di commit a due fasi tra il gestore di transazioni del client e la transazione del server, al fine di risolvere il risultato della transazione.  
  
 Se il server e client vengono scritti tramite WCF, non devi usare WS-AT. È possibile invece utilizzare le impostazioni predefinite di `NetTcpBinding` con l'attributo `TransactionFlow` abilitato, in modo da utilizzare il protocollo `OleTransactions`. Per altre informazioni, vedere [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md). In caso contrario, se le transazioni vengono propagate a servizi Web basati su tecnologie di terze parti, sarà necessario utilizzare WS-AT.  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione del supporto transazioni WS-Atomic](../../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)
