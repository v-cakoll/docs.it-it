---
title: Trasporti in Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 6bb8e8b90c26533661684bd403b9ec439f1bb37e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498124"
---
# <a name="transports-in-windows-communication-foundation"></a>Trasporti in Windows Communication Foundation
Il livello di trasporto è al livello più basso dello stack dei canali. I trasporti principali usati in Windows Communication Foundation (WCF) sono HTTP, HTTPS, TCP e named pipe. Negli argomenti di questa sezione vengono fornite informazioni sulla scelta fra questi trasporti, la configurazione del trasporto e l'impostazione delle proprietà di ottimizzazione.  
  
 WCF sono inclusi trasporti aggiuntivi. Per informazioni sul trasporto di Accodamento messaggi (noto anche come MSMQ), vedere [code e sessioni affidabili](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md). Per informazioni sul trasporto peer-to-peer, vedere [rete Peer-to-Peer](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Scelta di un trasporto](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 Descrive i tre trasporti principali con gli aspetti da considerare in fase di selezione.  
  
 [Scelta di un codificatore di messaggi](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 Descrive i fattori da considerare nella scelta di un elemento di associazione di codifica dei messaggi.  
  
 [Trasferimento di messaggi di flusso](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 Descrive come configurare il livello del trasporto per l'esecuzione del flusso.  
  
 [Configurazione di HTTP e HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 Descrive come configurare gli elementi di associazione del trasporto HTTP e HTTPS.  
  
 [Procedura: Sostituire la prenotazione URL WCF con una prenotazione limitata](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 Viene descritto come utilizzare le prenotazioni WCFURL con restrizioni.  
  
 [Quote dei trasporti](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 Vengono fornite considerazioni per l'impostazione delle quote disponibili nel livello di trasporto.  
  
 [Uso di NAT e firewall](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 Descrive come configurare il livello di trasporto quando i messaggi vengono inviati o ricevuti attraverso un firewall o quando si utilizza la conversione degli indirizzi di rete (NAT).  
  
 [Condivisione delle porte Net.TCP](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 Viene descritto come utilizzare il componente di condivisione delle porte Net. TCP di WCF.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Associazioni](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [Estensione delle associazioni](../../../../docs/framework/wcf/extending/extending-bindings.md)
