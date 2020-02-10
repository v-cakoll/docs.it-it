---
title: Esempio di integrazione di SystemWebRouting
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: a91763e7dacb04a68cfea1079d55bbc1eda01668
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094891"
---
# <a name="systemwebrouting-integration-sample"></a>Esempio di integrazione di SystemWebRouting
In questo esempio viene descritta l'integrazione del livello di hosting con le classi nello spazio dei nomi <xref:System.Web.Routing>. Le classi nello spazio dei nomi <xref:System.Web.Routing> consentono a un'applicazione di usare URL che non corrispondono direttamente a una risorsa fisica. L'utilizzo del routing Web consente allo sviluppatore di creare indirizzi virtuali per HTTP di cui viene quindi eseguito il mapping ai servizi WCF effettivi. Ciò si rivela utile quando un servizio WCF deve essere ospitato senza richiedere una risorsa o un file fisico oppure quando l'accesso ai servizi deve essere eseguito con URL che non contengono file con estensioni quali html o aspx. In questo esempio viene descritto come usare la classe <xref:System.Web.Routing.RouteTable> per creare URI virtuali mappati a servizi in esecuzione definiti in global.asax. 

> [!NOTE]
> Le classi nello spazio dei nomi <xref:System.Web.Routing> possono essere usate solo per i servizi ospitati su HTTP.  
  
Questo esempio USA WCF per creare due feed RSS: un feed di `movies` e un feed di `channels`. Gli URL per l'attivazione dei servizi non contengono un'estensione e vengono registrati nel metodo `Application_Start` della classe `Global` derivata dalla classe <xref:System.Web.HttpApplication>.  
  
> [!NOTE]
> Questo esempio funziona solo in Internet Information Services (IIS) 7,0 e versioni successive, perché IIS 6,0 usa un metodo diverso per supportare URL senza estensione.  

#### <a name="to-download-this-sample"></a>Per scaricare questo esempio
  
Questo esempio può essere già installato nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
   
`<InstallDrive>:\WF_WCF_Samples`  
   
 Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
   
`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1. Con Visual Studio aprire il file WebRoutingIntegration. sln.  
  
2. Per eseguire la soluzione e avviare il server Web di sviluppo, premere F5.  
  
     Verrà aperta la visualizzazione directory per l'esempio. Si noti che non sono presenti file con l'estensione di file svc.  
  
3. Nella barra degli indirizzi aggiungere `movies` all'URL, in modo che legga `http://localhost:[port]/movies` e premere INVIO.  
  
     Il feed movies verrà visualizzato nel browser.  
  
4. Nella barra degli indirizzi aggiungere `channels` all'URL, in modo che sia Reads `http://localhost:[port]/channels` e premere INVIO.  
  
     Il feed channels verrà visualizzato nel browser.  
  
5. Chiudere il browser premendo ALT+F4.  
  
     Se il server di sviluppo non è stato chiuso, fare clic con il pulsante destro del mouse sull'icona dell'area di notifica e scegliere **Arresta**.  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a>Per usare questo esempio ospitato in IIS  
  
1. Con Visual Studio aprire il file WebRoutingIntegration. sln.  
  
2. Premere CTRL+MAIUSC+B per compilare il progetto.  
  
3. Creare un'applicazione Web in Gestione Internet Information Services (IIS).  
  
    1. In Gestione IIS fare clic con il pulsante destro del mouse sul **sito Web predefinito** e scegliere **Aggiungi applicazione**.  
  
    2. Per l' **alias**, digitare `WebRoutingIntegration`.  
  
    3. Per **percorso fisico**selezionare la cartella del servizio all'interno del progetto.  
  
    4. Premere **OK**.  
  
4. Avviare l'applicazione facendo clic con il pulsante destro del mouse sull'applicazione Web e scegliendo **Gestisci applicazione** , quindi **Sfoglia**.  
  
5. Nella barra degli indirizzi aggiungere `movies` all'URL, in modo che sia Reads `http://localhost:[port]/movies` e premere INVIO.  
  
     Il feed movies verrà visualizzato nel browser.  
  
6. Nella barra degli indirizzi aggiungere `channels` all'URL, in modo che sia Reads `http://localhost:[port]/channels` e premere INVIO.  
  
     Il feed channels verrà visualizzato nel browser.  
  
7. Chiudere il browser premendo ALT+F4.  
  
 In questo esempio illustrato come il livello di hosting sia in grado di interagire con le classi nello spazio dei nomi <xref:System.Web.Routing> per l'indirizzamento delle richieste dei servizi ospitati su HTTP.  
  
> [!NOTE]
> È necessario aggiornare la versione predefinita del pool di applicazioni a .NET Framework 4 se è impostata sulla versione 2.  
  
## <a name="see-also"></a>Vedere anche

- [Esempi di persistenza e hosting di AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))
