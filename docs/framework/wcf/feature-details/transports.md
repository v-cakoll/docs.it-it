---
title: Trasporti in Windows Communication Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 115e2a69c7d990c7d4c59634644fb557e83ad405
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="transports-in-windows-communication-foundation"></a>Trasporti in Windows Communication Foundation
Il livello di trasporto è al livello più basso dello stack dei canali. I trasporti principali utilizzati in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sono HTTP, Https, TCP e named pipe. Negli argomenti di questa sezione vengono fornite informazioni sulla scelta fra questi trasporti, la configurazione del trasporto e l'impostazione delle proprietà di ottimizzazione.  
  
 In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sono inclusi trasporti aggiuntivi. Per informazioni sul trasporto di Accodamento messaggi (noto anche come MSMQ), vedere [code e sessioni affidabili](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md). Per informazioni sul trasporto peer-to-peer, vedere [rete Peer-to-Peer](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Scelta di un trasporto](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 Descrive i tre trasporti principali con gli aspetti da considerare in fase di selezione.  
  
 [Scelta di un codificatore di messaggi](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 Descrive i fattori da considerare nella scelta di un elemento di associazione di codifica dei messaggi.  
  
 [Trasferimento dei messaggi di flusso](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 Descrive come configurare il livello del trasporto per l'esecuzione del flusso.  
  
 [Configurazione di HTTP e HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 Descrive come configurare gli elementi di associazione del trasporto HTTP e HTTPS.  
  
 [Procedura: sostituire la prenotazione URL WCF con una prenotazione limitata](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 Descrive come utilizzare le prenotazioni limitate URL di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Quote del trasporto](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 Vengono fornite considerazioni per l'impostazione delle quote disponibili nel livello di trasporto.  
  
 [Utilizzo di NAT e firewall](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 Descrive come configurare il livello di trasporto quando i messaggi vengono inviati o ricevuti attraverso un firewall o quando si utilizza la conversione degli indirizzi di rete (NAT).  
  
 [Condivisione porta Net. TCP](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 Descrive come utilizzare il componente di condivisione porte Net.TCP di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="reference"></a>Riferimento  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Associazioni](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [Estensione delle associazioni](../../../../docs/framework/wcf/extending/extending-bindings.md)
