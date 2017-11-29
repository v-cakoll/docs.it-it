---
title: Esempio di integrazione di SystemWebRouting
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e5050834ff01ebb6a25e746d88f7d328ded505cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="systemwebrouting-integration-sample"></a>Esempio di integrazione di SystemWebRouting
In questo esempio viene descritta l'integrazione del livello di hosting con le classi nello spazio dei nomi <xref:System.Web.Routing>. Le classi nello spazio dei nomi <xref:System.Web.Routing> consentono a un'applicazione di usare URL che non corrispondono direttamente a una risorsa fisica. L'uso del routing Web consente allo sviluppatore di creare indirizzi virtuali per HTTP dei quali viene quindi eseguito il mapping ai servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] effettivi. Ciò si rivela utile quando un servizio WCF deve essere ospitato senza richiedere una risorsa o un file fisico oppure quando l'accesso ai servizi deve essere eseguito con URL che non contengono file con estensioni quali html o aspx. In questo esempio viene descritto come usare la classe <xref:System.Web.Routing.RouteTable> per creare URI virtuali mappati a servizi in esecuzione definiti in global.asax. Per questo esempio vengono usati due feed RSS creati con WCF, ovvero un feed `movies` e un feed `channels`. Gli URL per l'attivazione dei servizi non contengono un'estensione e sono registrati nel `Application_Start` metodo il `Global` classe derivata dalla <xref:System.Web.HttpApplication.Application_Start> classe.  
  
> [!NOTE]
>  Le classi nello spazio dei nomi <xref:System.Web.Routing> possono essere usate solo per i servizi ospitati su HTTP.  
  
> [!NOTE]
>  Questo esempio può essere usato solo in [!INCLUDE[iisver](../../../../includes/iisver-md.md)], poiché [!INCLUDE[iis60](../../../../includes/iis60-md.md)] usa un metodo diverso per il supporto di URL senza estensione.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  In [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] aprire il file WebRoutingIntegration.sln.  
  
2.  Per eseguire la soluzione e avviare il server Web di sviluppo, premere F5.  
  
     Verrà aperta la visualizzazione directory per l'esempio. Si noti che non sono presenti file con l'estensione di file svc.  
  
3.  Nella barra degli indirizzi aggiungere `movies` all'URL, in modo da ottenere http://localhost:[port]/movies, quindi premere INVIO.  
  
     Il feed movies verrà visualizzato nel browser.  
  
4.  Nella barra degli indirizzi aggiungere `channels` all'URL, in modo da ottenere http://localhost:[port]/channels, quindi premere INVIO.  
  
     Il feed channels verrà visualizzato nel browser.  
  
5.  Chiudere il browser premendo ALT+F4.  
  
     Se il server di sviluppo non è stato chiuso, l'icona dell'area di notifica e scegliere **arrestare**.  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a>Per usare questo esempio ospitato in IIS  
  
1.  In [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] aprire il file WebRoutingIntegration.sln.  
  
2.  Premere CTRL+MAIUSC+B per compilare il progetto.  
  
3.  Creare un'applicazione Web in Gestione Internet Information Services (IIS).  
  
    1.  In Gestione IIS, fare clic destro la **sito Web predefinito** e selezionare **aggiungere un'applicazione**.  
  
    2.  Per il **alias**, digitare `WebRoutingIntegration`.  
  
    3.  Per il **percorso fisico**, selezionare la cartella Service all'interno del progetto.  
  
    4.  Press **OK**.  
  
4.  Avviare l'applicazione, facendo l'applicazione Web **Gestione applicazione** e quindi **Sfoglia**.  
  
5.  Nella barra degli indirizzi aggiungere `movies` all'URL, in modo da ottenere http://localhost:[port]/movies, quindi premere INVIO.  
  
     Il feed movies verrà visualizzato nel browser.  
  
6.  Nella barra degli indirizzi aggiungere `channels` all'URL, in modo da ottenere http://localhost:[port]/channels, quindi premere INVIO.  
  
     Il feed channels verrà visualizzato nel browser.  
  
7.  Chiudere il browser premendo ALT+F4.  
  
 In questo esempio illustrato come il livello di hosting sia in grado di interagire con le classi nello spazio dei nomi <xref:System.Web.Routing> per l'indirizzamento delle richieste dei servizi ospitati su HTTP.  
  
> [!NOTE]
>  Se è impostata sulla versione 2, aggiornare la versione del pool di applicazioni predefinito a [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].  
  
## <a name="see-also"></a>Vedere anche  
 [Hosting di AppFabric ed esempi di persistenza](http://go.microsoft.com/fwlink/?LinkId=193961)
