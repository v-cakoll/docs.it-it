---
title: Aggiornamenti flusso personalizzati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3da85c8-57f3-4e32-a4cb-50123f30fea6
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d7cf7a45051c6cd550225ebc29e587bc937b0953
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="custom-stream-upgrades"></a>Aggiornamenti flusso personalizzati
I trasporti orientati al flusso, quali TCP e named pipe, operano su un flusso continuo di byte tra il client e il server. Questo flusso viene realizzato da un oggetto <xref:System.IO.Stream>. In un aggiornamento flusso, il client desidera aggiungere un livello di protocollo facoltativo allo stack di canali e chiede all'altra estremità del canale di comunicazione di farlo. L'aggiornamento flusso consiste nel sostituire l'oggetto <xref:System.IO.Stream> originale con un oggetto aggiornato.  
  
 È, ad esempio, possibile creare un flusso di compressione direttamente all'inizio del flusso di trasporto. In questo caso, la classe di trasporto <xref:System.IO.Stream> originale viene sostituita con una classe che esegue il wrapping della classe di compressione <xref:System.IO.Stream> sull'originale.  
  
 È possibile applicare più aggiornamenti flusso, ognuno dei quali esegue il wrapping del precedente.  
  
## <a name="how-stream-upgrades-work"></a>Funzionamento degli aggiornamenti flusso  
 Il processo di aggiornamento flusso include quattro componenti.  
  
1.  Un aggiornamento flusso *iniziatore* inizia il processo: in fase di esecuzione, può inviare una richiesta a altra estremità della connessione per aggiornare il livello di trasporto del canale.  
  
2.  Un aggiornamento flusso *Acceptor* esegue l'aggiornamento: in fase di esecuzione, riceve la richiesta di aggiornamento da altro computer e, se possibile, accetta l'aggiornamento.  
  
3.  Un aggiornamento *Provider* crea il *iniziatore* sul client e il *Acceptor* sul server.  
  
4.  Un aggiornamento flusso *elemento di associazione* viene aggiunto alle associazioni sul servizio e il client e crea il provider in fase di esecuzione.  
  
 Si noti che, nel caso di più aggiornamenti, iniziatore e acceptor incapsulano macchine a stati da imporre, le cui transizioni di aggiornamento sono valide per ogni avvio.  
  
## <a name="how-to-implement-a-stream-upgrade"></a>Come implementare un aggiornamento flusso  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] fornisce quattro classi `abstract` che è possibile implementare:  
  
-   <xref:System.ServiceModel.Channels.StreamUpgradeInitiator?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Channels.StreamUpgradeProvider?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement?displayProperty=nameWithType>  
  
 Per implementare un aggiornamento flusso personalizzato, eseguire le operazioni seguenti. In questa procedura viene implementato un processo di aggiornamento flusso minimo sui computer client e server.  
  
1.  Creare una classe che implementi <xref:System.ServiceModel.Channels.StreamUpgradeInitiator>.  
  
    1.  Eseguire l'override del metodo <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.InitiateUpgrade%2A> per accettare il flusso da aggiornare e restituire il flusso aggiornato. Questo metodo funziona in modo sincrono; sono disponibili metodi analoghi per avviare l'aggiornamento in modo asincrono.  
  
    2.  Eseguire l'override del metodo <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> per ricercare aggiornamenti aggiuntivi.  
  
2.  Creare una classe che implementi <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor>.  
  
    1.  Eseguire l'override del metodo <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.AcceptUpgrade%2A> per accettare il flusso da aggiornare e restituire il flusso aggiornato. Questo metodo funziona in modo sincrono; sono disponibili metodi analoghi per accettare l'aggiornamento in modo asincrono.  
  
    2.  Eseguire l'override del metodo <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A> per determinare se l'aggiornamento richiesto è supportato da questo acceptor di aggiornamento in questo punto del processo di aggiornamento.  
  
3.  Creare una classe che implementi <xref:System.ServiceModel.Channels.StreamUpgradeProvider>. Eseguire l'override dei metodi <xref:System.ServiceModel.Channels.StreamUpgradeProvider.CreateUpgradeAcceptor%2A> e <xref:System.ServiceModel.Channels.StreamUpgradeProvider.CreateUpgradeInitiator%2A> per restituire istanze dell'acceptor e dell'iniziatore definiti ai passaggi 2 e 1.  
  
4.  Creare una classe che implementi <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement>.  
  
    1.  Eseguire l'override del metodo <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement.BuildClientStreamUpgradeProvider%2A> sul client e del metodo <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement.BuildServerStreamUpgradeProvider%2A> sul servizio.  
  
    2.  Eseguire l'override del metodo <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> sul client e il metodo <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> sul servizio, per aggiungere l'elemento di associazione di aggiornamento a <xref:System.ServiceModel.Channels.BindingContext.BindingParameters%2A>.  
  
5.  Aggiungere il nuovo elemento di associazione di aggiornamento flusso alle associazioni sui computer server e client.  
  
## <a name="security-upgrades"></a>Aggiornamenti della protezione  
 L'aggiunta di un aggiornamento della protezione è una versione specifica del processo generale di aggiornamento flusso.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fornisce già due elementi di associazione per l'aggiornamento della protezione del flusso. La configurazione della protezione a livello di trasporto viene incapsulata dalle classi <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement> e <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>, che possono essere configurate e aggiunte a un'associazione personalizzata. Questi elementi di associazione estendono la classe <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement> che crea i provider di aggiornamento flusso client e server. Questi elementi di associazione includono metodi che creano le classi di provider di aggiornamento flusso di sicurezza specifiche, che non sono `public`, pertanto, per questi due casi, tutto ciò che è necessario fare è aggiungere l'elemento di associazione all'associazione.  
  
 Per gli scenari di sicurezza non soddisfatti dai due elementi di associazione precedenti vengono derivate tre classi `abstract` correlate alla protezione dalle classi di base di iniziatore, acceptor e provider precedenti:  
  
1.  <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator?displayProperty=nameWithType>  
  
2.  <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor?displayProperty=nameWithType>  
  
3.  <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider?displayProperty=nameWithType>  
  
 Il processo di implementazione di un aggiornamento flusso di sicurezza è identico al precedente, con la sola differenza della derivazione da queste tre classi. Eseguire l'override delle proprietà aggiuntive in queste classi, per fornire informazioni sulla protezione al runtime.  
  
## <a name="multiple-upgrades"></a>Aggiornamenti multipli  
 Per creare ulteriori richieste di aggiornamento ripetere il processo precedente: creare estensioni aggiuntive di <xref:System.ServiceModel.Channels.StreamUpgradeProvider> ed elementi di associazione. Aggiungere gli elementi di associazione all'associazione. Gli elementi di associazione aggiuntivi vengono elaborati in sequenza, a partire dal primo elemento di associazione aggiunto all'associazione. In <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> e <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A>, ogni provider di aggiornamento può determinare a quale livello collocarsi su qualsiasi parametro di associazione di aggiornamento preesistente. Deve quindi sostituire il parametro di associazione di aggiornamento esistente con un nuovo parametro di associazione di aggiornamento composito.  
  
 In alternativa, un provider di aggiornamento può supportare più aggiornamenti. Può, ad esempio, essere necessario implementare un provider di aggiornamento flusso personalizzato che supporti sia la protezione che la compressione. Eseguire i passaggi seguenti:  
  
1.  Sottoclassare <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider> per scrivere la classe di provider che crea l'iniziatore e l'acceptor.  
  
2.  Sottoclassare <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator> assicurandosi di eseguire l'override del metodo <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> per restituire i tipi di contenuto per il flusso di compressione e il flusso di sicurezza, in ordine.  
  
3.  Sottoclassare <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor> che comprende i tipi di contenuto personalizzati nel relativo metodo <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A>.  
  
4.  Il flusso verrà aggiornato dopo ogni chiamata a <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> e <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.StreamUpgradeInitiator>  
 <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator>  
 <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor>  
 <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor>  
 <xref:System.ServiceModel.Channels.StreamUpgradeProvider>  
 <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider>  
 <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement>  
 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
