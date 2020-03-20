---
title: Esempio di integrazione di SystemWebRouting
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: 2f12d80085e3ac27dac8ce80b6bb09f69337bfd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143954"
---
# <a name="systemwebrouting-integration-sample"></a>Esempio di integrazione di SystemWebRouting
In questo esempio viene descritta l'integrazione del livello di hosting con le classi nello spazio dei nomi <xref:System.Web.Routing>. Le classi nello spazio dei nomi <xref:System.Web.Routing> consentono a un'applicazione di usare URL che non corrispondono direttamente a una risorsa fisica. L'utilizzo del routing Web consente allo sviluppatore di creare indirizzi virtuali per HTTP che vengono quindi mappati ai servizi WCF effettivi. Ciò si rivela utile quando un servizio WCF deve essere ospitato senza richiedere una risorsa o un file fisico oppure quando l'accesso ai servizi deve essere eseguito con URL che non contengono file con estensioni quali html o aspx. In questo esempio viene descritto come usare la classe <xref:System.Web.Routing.RouteTable> per creare URI virtuali mappati a servizi in esecuzione definiti in global.asax.

> [!NOTE]
> Le classi nello spazio dei nomi <xref:System.Web.Routing> possono essere usate solo per i servizi ospitati su HTTP.  
  
In questo esempio viene utilizzato WCF per `movies` creare `channels` due feed RSS: un feed e un feed. Gli URL per attivare i servizi non contengono `Application_Start` un'estensione `Global` e vengono <xref:System.Web.HttpApplication> registrati nel metodo della classe derivata dalla classe.  
  
> [!NOTE]
> Questo esempio funziona solo in Internet Information Services (IIS) 7.0 e versioni successive, poiché IIS 6.0 utilizza un metodo diverso per supportare gli URL senza estensione.  

#### <a name="to-download-this-sample"></a>Per scaricare questo esempioTo download this sample
  
Questo esempio potrebbe essere già installato nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  

`<InstallDrive>:\WF_WCF_Samples`  

 Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  

`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1. Utilizzando Visual Studio, aprire il file WebRoutingIntegration.sln.  
  
2. Per eseguire la soluzione e avviare il server Web di sviluppo, premere F5.  
  
     Verrà aperta la visualizzazione directory per l'esempio. Si noti che non sono presenti file con l'estensione di file svc.  
  
3. Nella barra degli `movies` indirizzi aggiungere all'URL, `http://localhost:[port]/movies` in modo che venga letto e premere INVIO.  
  
     Il feed movies verrà visualizzato nel browser.  
  
4. Nella barra degli `channels` indirizzi aggiungere all'URL, `http://localhost:[port]/channels` in modo che venga letto e premere INVIO.  
  
     Il feed channels verrà visualizzato nel browser.  
  
5. Chiudere il browser premendo ALT+F4.  
  
     Se il server di sviluppo non è stato chiuso, fare clic con il pulsante destro del mouse sull'icona dell'area di notifica e scegliere **Arresta**.  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a>Per usare questo esempio ospitato in IIS  
  
1. Utilizzando Visual Studio, aprire il file WebRoutingIntegration.sln.  
  
2. Premere CTRL+MAIUSC+B per compilare il progetto.  
  
3. Creare un'applicazione Web in Gestione Internet Information Services (IIS).  
  
    1. In Gestione IIS fare clic con il pulsante destro del mouse sul **sito Web predefinito** e scegliere Aggiungi **applicazione**.  
  
    2. Per **l'alias** `WebRoutingIntegration`, digitare .  
  
    3. Per **Percorso fisico**, selezionare la cartella Servizio all'interno del progetto.  
  
    4. Fare clic su **OK**.  
  
4. Avviare l'applicazione facendo clic con il pulsante destro del mouse sull'applicazione Web e **scegliendo Gestisci applicazione,** quindi **Sfoglia**.  
  
5. Nella barra degli `movies` indirizzi aggiungere all'URL, `http://localhost:[port]/movies` in modo che venga letto e premere INVIO.  
  
     Il feed movies verrà visualizzato nel browser.  
  
6. Nella barra degli `channels` indirizzi aggiungere all'URL, `http://localhost:[port]/channels` in modo che venga letto e premere INVIO.  
  
     Il feed channels verrà visualizzato nel browser.  
  
7. Chiudere il browser premendo ALT+F4.  
  
 In questo esempio illustrato come il livello di hosting sia in grado di interagire con le classi nello spazio dei nomi <xref:System.Web.Routing> per l'indirizzamento delle richieste dei servizi ospitati su HTTP.  
  
> [!NOTE]
> È necessario aggiornare la versione del pool di applicazioni predefinita a .NET Framework 4 se è impostata sulla versione 2.  
  
## <a name="see-also"></a>Vedere anche

- [Hosting e salvataggio permanente](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))
