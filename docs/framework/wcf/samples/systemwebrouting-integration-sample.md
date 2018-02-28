---
title: Esempio di integrazione di SystemWebRouting
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: de8869956a59cb47623dbc4d84763e19d6f181bf
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2018
---
# <a name="systemwebrouting-integration-sample"></a>Esempio di integrazione di SystemWebRouting
In questo esempio viene descritta l'integrazione del livello di hosting con le classi nello spazio dei nomi <xref:System.Web.Routing>. Le classi nello spazio dei nomi <xref:System.Web.Routing> consentono a un'applicazione di usare URL che non corrispondono direttamente a una risorsa fisica. L'uso del routing Web consente allo sviluppatore di creare indirizzi virtuali per HTTP dei quali viene quindi eseguito il mapping ai servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] effettivi. Ciò si rivela utile quando un servizio WCF deve essere ospitato senza richiedere una risorsa o un file fisico oppure quando l'accesso ai servizi deve essere eseguito con URL che non contengono file con estensioni quali html o aspx. In questo esempio viene descritto come usare la classe <xref:System.Web.Routing.RouteTable> per creare URI virtuali mappati a servizi in esecuzione definiti in global.asax. 

> [!NOTE]
>  Le classi nello spazio dei nomi <xref:System.Web.Routing> possono essere usate solo per i servizi ospitati su HTTP.  
  
In questo esempio vengono usati WCF per creare due feed RSS: un `movies` feed e un `channels` feed. Gli URL per l'attivazione dei servizi non contengono un'estensione e sono registrati nel `Application_Start` metodo il `Global` classe derivata dalla <xref:System.Web.HttpApplication> classe.  
  
> [!NOTE]
>  Questo esempio funziona solo in Internet Information Services (IIS) 7.0 e versioni successive, come IIS 6.0 utilizza un metodo diverso per il supporto di URL senza estensione.  

#### <a name="to-download-this-sample"></a>Per scaricare questo esempio
  
In questo esempio siano già installato nel computer in uso. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
   
`<InstallDrive>:\WF_WCF_Samples`  
   
 Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
   
`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Utilizzando Visual Studio, aprire il file WebRoutingIntegration.sln.  
  
2.  Per eseguire la soluzione e avviare il server Web di sviluppo, premere F5.  
  
     Verrà aperta la visualizzazione directory per l'esempio. Si noti che non sono presenti file con l'estensione di file svc.  
  
3.  Nella barra degli indirizzi, aggiungere `movies` all'URL, in modo che legge http://localhost: [port] /Movies, quindi premere INVIO.  
  
     Il feed movies verrà visualizzato nel browser.  
  
4.  Nella barra degli indirizzi aggiungere `channels` all'URL, in modo da ottenere http://localhost:[port]/channels, quindi premere INVIO.  
  
     Il feed channels verrà visualizzato nel browser.  
  
5.  Chiudere il browser premendo ALT+F4.  
  
     Se il server di sviluppo non è stato chiuso, l'icona dell'area di notifica e scegliere **arrestare**.  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a>Per usare questo esempio ospitato in IIS  
  
1.  Utilizzando Visual Studio, aprire il file WebRoutingIntegration.sln.  
  
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
>  È necessario aggiornare la versione di pool di applicazioni predefinita da [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] se è impostato per la versione 2.  
  
## <a name="see-also"></a>Vedere anche  
 [Hosting di AppFabric ed esempi di persistenza](http://go.microsoft.com/fwlink/?LinkId=193961)
