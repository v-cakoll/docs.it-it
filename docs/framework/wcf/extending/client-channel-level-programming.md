---
title: Programmazione a livello di canale client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3b787719-4e77-4e77-96a6-5b15a11b995a
ms.openlocfilehash: ea56c99d7d122dd20fc217f8ecb2937bcf81bec3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923266"
---
# <a name="client-channel-level-programming"></a>Programmazione a livello di canale client
In questo argomento viene descritto come scrivere un'applicazione client Windows Communication Foundation (WCF) senza usare il <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> classe e il modello a oggetti associato.  
  
## <a name="sending-messages"></a>Invio di messaggi  
 Per l'invio di messaggi e la ricezione e l'elaborazione di risposte è necessario eseguire i passaggi seguenti:  
  
1. Creare un'associazione.  
  
2. Generare una channel factory.  
  
3. Creare un canale.  
  
4. Inviare una richiesta e leggere la riposta.  
  
5. Chiudere tutti gli oggetti canale.  
  
#### <a name="creating-a-binding"></a>Creazione di un'associazione  
 Analogamente al caso di ricezione (vedere [canale del servizio a livello di programmazione](../../../../docs/framework/wcf/extending/service-channel-level-programming.md)), l'invio di messaggi inizia creando un'associazione. In questo esempio viene creato un nuovo <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> e viene aggiunto un <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> alla rispettiva raccolta di elementi.  
  
#### <a name="building-a-channelfactory"></a>Generare una channel factory.  
 Anziché creare un <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=nameWithType>, questa volta è necessario creare una <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> chiamando <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=nameWithType> nell'associazione dove il parametro del tipo è <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>. Mentre i listener del canale vengono utilizzati dalla parte in attesa di messaggi in arrivo, le channel factory vengono utilizzate dalla parte che inizia la comunicazione per creare un canale. Esattamente come i listener del canale, le channel factory devono essere aperte prima di poter essere utilizzate.  
  
#### <a name="creating-a-channel"></a>Creazione di un canale  
 È necessario quindi chiamare <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> per creare un <xref:System.ServiceModel.Channels.IRequestChannel>. Questa chiamata prende l'indirizzo dell'endpoint con il quale si vuole comunicare utilizzando il nuovo canale creato. Quando viene ottenuto un canale, è necessario chiamare Open su di esso per renderlo pronto per la comunicazione. A seconda della natura del trasporto, con questa chiamata a Open viene avviata una connessione con l'endpoint di destinazione oppure non viene eseguita alcuna operazione nella rete.  
  
#### <a name="sending-a-request-and-reading-the-reply"></a>Invio di una richiesta e lettura della risposta  
 Dopo che un canale è stato aperto, è possibile creare un messaggio e utilizzare il metodo di richiesta del canale per inviare la richiesta e attendere la risposta. Questo metodo restituisce un messaggio di risposta che è possibile leggere per scoprire quale è stata la risposta dell'endpoint.  
  
#### <a name="closing-objects"></a>Chiusura di oggetti  
 Per evitare la perdita di risorse, è necessario chiudere gli oggetti utilizzati nelle comunicazioni quando non sono più necessari.  
  
 Nell'esempio di codice seguente viene illustrato un client di base che utilizza la channel factory per inviare un messaggio e leggere la risposta.  
  
 [!code-csharp[ChannelProgrammingBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/clientprogram.cs#2)]
 [!code-vb[ChannelProgrammingBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/clientprogram.vb#2)]
