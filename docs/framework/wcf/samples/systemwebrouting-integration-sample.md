---
title: Esempio di integrazione di SystemWebRouting
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: 1724fee816ddd210ffba73159596529bd4bc803e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548252"
---
# <a name="systemwebrouting-integration-sample"></a>Esempio di integrazione di SystemWebRouting
In questo esempio viene descritta l'integrazione del livello di hosting con le classi nello spazio dei nomi <xref:System.Web.Routing>. Le classi nello spazio dei nomi <xref:System.Web.Routing> consentono a un'applicazione di usare URL che non corrispondono direttamente a una risorsa fisica. Uso del routing Web consente allo sviluppatore di creare indirizzi virtuali per il protocollo HTTP che vengono quindi rimappata alla effettivi dei servizi WCF. Ciò si rivela utile quando un servizio WCF deve essere ospitato senza richiedere una risorsa o un file fisico oppure quando l'accesso ai servizi deve essere eseguito con URL che non contengono file con estensioni quali html o aspx. In questo esempio viene descritto come usare la classe <xref:System.Web.Routing.RouteTable> per creare URI virtuali mappati a servizi in esecuzione definiti in global.asax. 

> [!NOTE]
>  Le classi nello spazio dei nomi <xref:System.Web.Routing> possono essere usate solo per i servizi ospitati su HTTP.  
  
In questo esempio utilizza WCF per creare due feed RSS: una `movies` feed e un `channels` feed. Gli URL per attivare i servizi non contengono un'estensione e vengono registrati nel `Application_Start` metodo per il `Global` classe derivata dal <xref:System.Web.HttpApplication> classe.  
  
> [!NOTE]
>  In questo esempio funziona solo in Internet Information Services (IIS) 7.0 e versioni successive, come IIS 6.0 usa un metodo diverso per il supporto di URL senza estensione.  

#### <a name="to-download-this-sample"></a>Per scaricare questo esempio
  
In questo esempio potrebbe essere già installato nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
   
`<InstallDrive>:\WF_WCF_Samples`  
   
 Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
   
`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Usa Visual Studio, aprire il file Webroutingintegration.  
  
2.  Per eseguire la soluzione e avviare il server Web di sviluppo, premere F5.  
  
     Verrà aperta la visualizzazione directory per l'esempio. Si noti che non sono presenti file con l'estensione di file svc.  
  
3.  Nella barra degli indirizzi, aggiungere `movies` all'URL, in modo che venga legge `http://localhost:[port]/movies` e premere INVIO.  
  
     Il feed movies verrà visualizzato nel browser.  
  
4.  Nella barra degli indirizzi, aggiungere `channels` all'URL, ecco le letture `http://localhost:[port]/channels` e premere INVIO.  
  
     Il feed channels verrà visualizzato nel browser.  
  
5.  Chiudere il browser premendo ALT+F4.  
  
     Se il server di sviluppo non viene chiuso, fare doppio clic sull'icona di area di notifica e selezionare **arrestare**.  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a>Per usare questo esempio ospitato in IIS  
  
1.  Usa Visual Studio, aprire il file Webroutingintegration.  
  
2.  Premere CTRL+MAIUSC+B per compilare il progetto.  
  
3.  Creare un'applicazione Web in Gestione Internet Information Services (IIS).  
  
    1.  Fare clic in Gestione IIS, il **sito Web predefinito** e selezionare **aggiungere un'applicazione**.  
  
    2.  Per il **alias**, digitare `WebRoutingIntegration`.  
  
    3.  Per il **percorso fisico**, selezionare la cartella Service all'interno del progetto.  
  
    4.  Fare clic su **OK**.  
  
4.  Avviare l'applicazione, facendo clic all'applicazione Web e selezionando **Gestione applicazioni** e quindi **Sfoglia**.  
  
5.  Nella barra degli indirizzi, aggiungere `movies` all'URL, ecco le letture `http://localhost:[port]/movies` e premere INVIO.  
  
     Il feed movies verrà visualizzato nel browser.  
  
6.  Nella barra degli indirizzi, aggiungere `channels` all'URL, ecco le letture `http://localhost:[port]/channels` e premere INVIO.  
  
     Il feed channels verrà visualizzato nel browser.  
  
7.  Chiudere il browser premendo ALT+F4.  
  
 In questo esempio illustrato come il livello di hosting sia in grado di interagire con le classi nello spazio dei nomi <xref:System.Web.Routing> per l'indirizzamento delle richieste dei servizi ospitati su HTTP.  
  
> [!NOTE]
>  È necessario aggiornare la versione predefinita dell'applicazione del pool per [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] se è impostata per la versione 2.  
  
## <a name="see-also"></a>Vedere anche
- [Hosting di AppFabric e salvataggio permanente](https://go.microsoft.com/fwlink/?LinkId=193961)
