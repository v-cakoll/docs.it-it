---
title: Formattatori dei messaggi personalizzati
ms.date: 03/30/2017
ms.assetid: c07435f3-5214-4791-8961-2c2b61306d71
ms.openlocfilehash: 9f66071d3c400ca2adc615afc7f93b2483fe2136
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795793"
---
# <a name="custom-message-formatters"></a>Formattatori dei messaggi personalizzati
Il contenuto di un messaggio è spesso nel formato XML, che in genere non è un formato pratico per un'applicazione. Le applicazioni modificano gli oggetti, ottenendo e impostando le relative proprietà. Windows Communication Foundation (WCF) utilizza il *contratto dati* per convertire un <xref:System.ServiceModel.Channels.Message> oggetto in un oggetto facilmente gestito da un'applicazione. Questi processi sono definiti serializzazione e deserializzazione. Questi stessi termini vengono usati per descrivere la serializzazione e la deserializzazione eseguita dal livello del trasporto verso e dal formato di trasmissione del messaggio, che sono processi non correlati.  
  
 È possibile usare un formattatore dei messaggi personalizzato se è necessario implementare una conversione specializzata tra messaggi e oggetti che non può essere eseguita mediante un contratto dati. Per questo scopo, modificare o estendere il comportamento di esecuzione di un'operazione del contratto specifica su un client o un servizio.  
  
## <a name="custom-message-formatters-on-the-client"></a>Formattatori dei messaggi personalizzati sul client  
 L'interfaccia <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> definisce i metodi usati per controllare la conversione dei messaggi in oggetti e degli oggetti in messaggi per le applicazioni client.  
  
 È necessario implementare questa interfaccia. Eseguire innanzitutto l'override del metodo <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.DeserializeReply%2A> per deserializzare un messaggio. Questo metodo viene chiamato dopo la ricezione di un messaggio in ingresso, ma prima che il messaggio venga inviato all'operazione client.  
  
 Eseguire quindi l'override del metodo <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.SerializeRequest%2A> per serializzare un oggetto. Questo metodo viene chiamato prima di inviare un messaggio in uscita.  
  
 Per inserire il formattatore personalizzato nell'applicazione del servizio, assegnare l'oggetto <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> alla proprietà <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A> usando un comportamento dell'operazione. Per informazioni sui comportamenti, vedere [configurazione ed estensione del runtime con i comportamenti](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="custom-message-formatters-on-the-service"></a>Formattatori dei messaggi personalizzati sul servizio  
 L'interfaccia <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> definisce i metodi che convertono un oggetto <xref:System.ServiceModel.Channels.Message> in parametri per un'operazione e da parametri in un oggetto <xref:System.ServiceModel.Channels.Message> in un'applicazione di servizio.  
  
 È necessario implementare questa interfaccia. Eseguire innanzitutto l'override del metodo <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.DeserializeReply%2A> per deserializzare un messaggio. Questo metodo viene chiamato dopo la ricezione di un messaggio in ingresso, ma prima che il messaggio venga inviato all'operazione client.  
  
 Eseguire quindi l'override del metodo <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.SerializeRequest%2A> per serializzare un oggetto. Questo metodo viene chiamato prima di inviare un messaggio in uscita.  
  
 Per inserire il formattatore personalizzato nell'applicazione del servizio, assegnare l'oggetto <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> alla proprietà <xref:System.ServiceModel.Dispatcher.DispatchOperation.Formatter%2A> usando un comportamento dell'operazione. Per informazioni sui comportamenti, vedere [configurazione ed estensione del runtime con i comportamenti](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>
- [Configurazione ed estensione del runtime con i comportamenti](configuring-and-extending-the-runtime-with-behaviors.md)
