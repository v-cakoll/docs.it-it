---
title: Esecuzione degli esempi di Windows Communication Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db8a83da-95c1-4a21-a9d2-48caeb6398ea
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1a37c7b01d4ef40727c02e0782422776086b5297
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="running-the-windows-communication-foundation-samples"></a>Esecuzione degli esempi di Windows Communication Foundation
Gli esempi [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] possono essere eseguiti in un singolo computer o su una configurazione che prevede più computer. Nel modo in cui sono forniti, essi sono pronti per essere eseguiti su un solo computer. In una configurazione a più computer, è necessario modificare le impostazioni del file di configurazione di un esempio. Le procedure descritte di seguito spiegano come eseguire un esempio nello stesso computer e configurazioni su più computer. Notare che ci sono variazioni nei passaggi per servizi ospitati su Internet Information Services (IIS) e gli esempi indipendenti. La maggior parte degli esempi sono ospitati su IIS; vedere le informazioni leggimi dell'esempio per determinare come viene ospitato l'esempio.  
  
 In [!INCLUDE[wv](../../../../includes/wv-md.md)] gli esempi che non sono ospitati da IIS richiedono privilegi elevati per registrare un listener con Http.sys. Usare Httpcfg.exe per registrare gli indirizzi di ascolto del servizio con l'account sotto cui il servizio è in esecuzione o avviare il servizio da un prompt dei comandi in esecuzione con privilegi di amministratore.  
  
> [!NOTE]
>  Prima di compilare o eseguire uno del [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] esempi, assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
### <a name="to-run-the-sample-on-the-same-machine"></a>Per eseguire l'esempio sullo stesso computer  
  
1.  Se il servizio è ospitato da IIS, verificare che sia possibile accedere al servizio usando un browser, immettendo l'indirizzo seguente: http://localhost/servicemodelsamples/service.svc. In risposta, viene visualizzata un pagina di conferma. Se non viene visualizzata la pagina di conferma, vedere [suggerimenti per la risoluzione dei problemi](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).  
  
2.  Se il servizio è indipendente, eseguire Service.exe da \service\bin, dalla cartella specifica del linguaggio. L'attività del servizio viene visualizzata nella finestra della console del servizio.  
  
3.  Eseguire Client.exe da \Client\Bin.\\, nella cartella della specifica del linguaggio. L'attività del client viene visualizzata nella finestra della console client.  
  
4.  Se il client e il servizio non possono comunicare, vedere [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### <a name="to-run-the-sample-across-machines"></a>Per eseguire l'esempio tra più computer  
  
1.  Se il servizio è ospitato su IIS:  
  
    1.  Sul computer del servizio, creare una directory virtuale denominata ServiceModelSamples. Il file batch Setupvroot.bat incluso con [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) può essere utilizzato per creare la directory del disco e la directory virtuale.  
  
    2.  Copiare i file del programma del servizio da %SystemDrive%\Inetpub\wwwroot\servicemodelsamples alla directory virtuale di ServiceModelSamples sul computer del servizio. Assicurarsi di includere i file nella directory \bin.  
  
    3.  Verificare che sia possibile accedere al servizio dal computer client usando un browser.  
  
     Se il servizio è indipendente:  
  
    1.  Sul computer del servizio, creare una directory per archiviare i file del servizio.  
  
    2.  Copiare i file del programma servizio dalla cartella \service\bin\, nella cartella specifica della lingua, al computer del servizio.  
  
    3.  Nel file di configurazione del servizio, modificare il valore dell'indirizzo della definizione dell'endpoint affinché corrisponda al nuovo indirizzo del servizio. Nell'indirizzo sostituire qualsiasi riferimento a "localhost" con un nome di dominio completo.  
  
    4.  Avviare Service.exe da un prompt dei comandi.  
  
2.  Copiare i file del programma client dalla cartella \client\bin\, nella cartella specifica del linguaggio, al computer client.  
  
3.  Impostare l'indirizzo dell'endpoint.  
  
    1.  Se il servizio è in esecuzione con un account di dominio, aprire il file di configurazione del client e modificare il valore dell'indirizzo della definizione dell'endpoint perché corrisponda al nuovo indirizzo del servizio. Nell'indirizzo sostituire qualsiasi riferimento a "localhost" con un nome di dominio completo.  
  
    2.  Se il servizio è in esecuzione con un account di dominio, rigenerare la configurazione client eseguendo Svcutil.exe sul servizio. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]esegue Svcutil.exe, vedere [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md). Usare il file generato anziché il file di configurazione dell'esempio. Il file di configurazione generato contiene informazioni di identità aggiuntive e tutte le impostazioni necessarie per connettersi all'endpoint del servizio, anche se si tratta di impostazioni predefinite. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]informazioni di identità, vedere [autenticazione e identità del servizio](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md), e [ \<identità >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md).  
  
4.  Sul computer client, avviare Client.exe da un prompt dei comandi.  
  
### <a name="to-debug-a-service"></a>Per eseguire il debug di un servizio  
  
1.  Compilazione di soluzione (client e servizio) utilizzando il **compilare** menu o CTRL + MAIUSC + B.  
  
2.  Se il servizio è ospitato su IIS:  
  
    1.  Attivare il servizio inserendo in un browser l'indirizzo http://localhost/servicemodelsamples/service.svc.  
  
    2.  Nella soluzione, scegliere il **Debug** menu e **Connetti a processo** voce di menu.  
  
    3.  Selezionare il **Mostra i processi di tutti gli utenti** casella di controllo.  
  
    4.  Selezionare il processo di lavoro dell' host W3wp.exe sul quale eseguire il debug (selezionare ASPNet_wp.exe su Windows XP).  
  
3.  È ora possibile impostare punti di interruzione nel codice del servizio e abilitare punti di interruzione sulle eccezioni.  
  
4.  L'elemento del progetto client di mouse e scegliere **Debug**, **Avvia nuova istanza**.  
  
### <a name="to-clean-up-after-the-sample"></a>Per eseguire la pulizia dopo l'esempio  
  
-   Se il servizio è ospitato su IIS, per motivi di sicurezza, rimuovere la definizione della directory virtuale e le autorizzazioni concesse durante l'installazione quando si è finito di lavorare con gli esempi eseguendo il file batch denominato Cleanupvroot.bat.  
  
## <a name="see-also"></a>Vedere anche  
 [Compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md)  
 [Esecuzione degli esempi di un gruppo di lavoro e tra più computer](http://msdn.microsoft.com/en-us/a451a525-e7ce-452d-9da9-620221260113)  
 [Suggerimenti di risoluzione dei problemi](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)
