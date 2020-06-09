---
title: Trasporti in Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 077d63d8038b245a68083611897c1e6c68971071
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598671"
---
# <a name="transports-in-windows-communication-foundation"></a>Trasporti in Windows Communication Foundation
Il livello di trasporto è al livello più basso dello stack dei canali. I trasporti principali utilizzati in Windows Communication Foundation (WCF) sono HTTP, HTTPS, TCP e named pipe. Negli argomenti di questa sezione vengono fornite informazioni sulla scelta fra questi trasporti, la configurazione del trasporto e l'impostazione delle proprietà di ottimizzazione.  
  
 WCF include trasporti aggiuntivi. Per informazioni sul trasporto di Accodamento messaggi (noto anche come MSMQ), vedere [code e sessioni affidabili](queues-and-reliable-sessions.md). Per informazioni sul trasporto peer-to-peer, vedere la pagina relativa [alla rete peer-to-peer](peer-to-peer-networking.md).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Scelta di un trasporto](choosing-a-transport.md)  
 Descrive i tre trasporti principali con gli aspetti da considerare in fase di selezione.  
  
 [Scelta di un codificatore di messaggi](choosing-a-message-encoder.md)  
 Descrive i fattori da considerare nella scelta di un elemento di associazione di codifica dei messaggi.  
  
 [Trasferimento dei messaggi di flusso](streaming-message-transfer.md)  
 Descrive come configurare il livello del trasporto per l'esecuzione del flusso.  
  
 [Configurazione di HTTP e HTTPS](configuring-http-and-https.md)  
 Descrive come configurare gli elementi di associazione del trasporto HTTP e HTTPS.  
  
 [Procedura: Sostituire la prenotazione URL WCF con una prenotazione limitata](how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 Viene descritto come usare le prenotazioni con restrizioni WCFURL.  
  
 [Quote dei trasporti](transport-quotas.md)  
 Vengono fornite considerazioni per l'impostazione delle quote disponibili nel livello di trasporto.  
  
 [Uso di conversioni NAT e firewall](working-with-nats-and-firewalls.md)  
 Descrive come configurare il livello di trasporto quando i messaggi vengono inviati o ricevuti attraverso un firewall o quando si utilizza la conversione degli indirizzi di rete (NAT).  
  
 [Condivisione delle porte Net.TCP](net-tcp-port-sharing.md)  
 Viene descritto come utilizzare il componente di condivisione delle porte net. TCP di WCF.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Binding](bindings.md)  
  
 [Estensione delle associazioni](../extending/extending-bindings.md)
