---
title: Generazione degli esempi Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 2899e7a5-9cb2-4e8d-b8d2-f31391549198
ms.openlocfilehash: 46f4015c00916a5cab932e8fd2539c7c86588a30
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43462324"
---
# <a name="building-the-windows-communication-foundation-samples"></a>Generazione degli esempi Windows Communication Foundation

Gli esempi di Windows Communication Foundation (WCF) possono essere compilati usando l'IDE di Visual Studio oppure utilizzando il **msbuild** comando dalla riga di comando. Entrambe le procedure sono descritte in questo argomento.

> [!NOTE]
> Prima di compilare o eseguire uno qualsiasi degli esempi di WCF, assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

## <a name="to-build-the-sample-using-a-command-prompt"></a>Per compilare l'esempio utilizzando il prompt dei comandi

1.  Aprire il prompt dei comandi per gli sviluppatori per Visual Studio e passare alla sottodirectory specifiche del linguaggio del percorso della directory in cui è installato l'esempio.

2.  Tipo `msbuild` nella riga di comando. I file di programma client vengono compilati per *client\bin* e i file di programma vengono compilati per *service\bin*. Se il servizio è ospitato da Internet Information Services (IIS), i file di programma vengono copiati anche per il *servicemodelsamples* directory e i relativi *\bin* sottodirectory.

> [!NOTE]
> È necessario impostare gli ACL sul *%systemdrive%\inetpub\wwwroot* concedere o modificare le autorizzazioni per l'account con cui si esegue. In caso contrario vi saranno errori relativi a eventi post-compilazione. In alternativa, è possibile lasciare le ACL come sono ed eseguire il prompt dei comandi SDK come amministratore.

## <a name="to-build-the-sample-using-visual-studio"></a>Per compilare l'esempio utilizzando Visual Studio

1. Dal **File** dal menu di Visual Studio, selezionare **Open** > **progetto/soluzione**. Spostarsi nella sottodirectory specifica del linguaggio sotto la directory in cui è installato l'esempio e fare doppio clic sull'icona del file con estensione sln per aprire la soluzione in Visual Studio.

1. Dal **compilare** dal menu **Ricompila soluzione**.

   I file di programma client vengono compilati in client\bin, mentre i file del programma del servizio vengono compilati in service\bin. Se il servizio è ospitato in IIS, i file di programma vengono copiati anche per il *servicemodelsamples* directory e i relativi *\bin* sottodirectory.

> [!NOTE]
> È necessario impostare ACLs su %systemdrive%\inetpub\wwwroot per concedere autorizzazioni di modifica per l'account in esecuzione. In caso contrario vi saranno errori relativi a eventi post-compilazione. In alternativa, è possibile lasciare le ACL come sono ed eseguire il prompt dei comandi SDK o Visual Studio come amministratore. Anche alcune azioni di Visual Studio (ad esempio allegare un debugger al processo di lavoro ASP.NET) richiedono privilegi amministrativi.

## <a name="setup-batch-files-and-scripts"></a>Impostare file batch e script
 Script e Setup.exe Cleanup.exe. exe e file batch deve essere eseguito dal prompt dei comandi per gli sviluppatori per Visual Studio. Diversi file di installazione e pulizia eseguono attività che richiedono privilegi amministrativi e devono essere avviati con privilegi di questo tipo.

## <a name="important-security-information-about-metadata-endpoints"></a>Importanti informazioni di sicurezza sugli endpoint dei metadati
 Per evitare la diffusione accidentale di metadati del servizio potenzialmente riservati, la configurazione predefinita per i servizi Windows Communication Foundation (WCF) consente di disattivare la pubblicazione dei metadati. Questo comportamento è protetto per impostazione predefinita, ma significa inoltre che non è possibile usare uno strumento di importazione di metadati (ad esempio Svcutil.exe) per generare il codice client necessario per chiamare il servizio, a meno che il comportamento del servizio di pubblicazione dei metadati non venga abilitato in modo esplicito in fase di configurazione. Per rendere più semplice la sperimentazione con gli esempi, quasi tutti gli esempi espongono un endpoint di pubblicazione dei metadati non protetto. Tali endpoint sono potenzialmente disponibili per utenti anonimi non autenticati e bisogna fare attenzione prima di distribuirli per garantire che la pubblicazione dei metadati di un servizio sia appropriata. Per altre informazioni sulla pubblicazione di metadati del servizio, vedere la [comportamento di pubblicazione dei metadati](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md) esempio. Vedere le [Endpoint di metadati protetto personalizzato](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) esempio per un esempio di protezione endpoint di metadati.

## <a name="exception-handling"></a>Gestione delle eccezioni
 In genere questi esempi non includono la gestione delle eccezioni per focalizzare il codice sull'argomento dell'esempio. Per altre informazioni sulla gestione delle eccezioni, vedere la [eccezioni previsto](../../../../docs/framework/wcf/samples/expected-exceptions.md) esempio.

## <a name="regenerating-clients-and-configuration-with-svcutil"></a>Rigenerazione client e configurazione con Svcutil
 È possibile usare la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per rigenerare codice client e la configurazione per la maggior parte degli esempi. Alcuni esempi richiedono una configurazione manuale. Ad esempio, se si utilizza Svcutil.exe per rigenerare la configurazione per un esempio che utilizza credenziali del certificato client, si devono specificare manualmente le credenziali precedentemente configurate. Alcuni esempi utilizzano opzioni Svcutil.exe specifiche per influire sul codice generato, queste opzioni sono specificate in argomenti di esempio appositi.

### <a name="to-regenerate-the-client-and-configuration-files"></a>Per rigenerare client e file di configurazione

1.  Aprire il prompt dei comandi SDK, quindi spostarsi nella sottodirectory specifica del linguaggio del percorso della directory in cui si è installato l'esempio.

2.  Se il servizio è di tipo ospitato sul Web, utilizzare il comando seguente.

    ```
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs
    ```

     Se il servizio è di tipo indipendente, digitare il comando seguente.

    ```
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /out:generatedClient.cs
    ```

     Sostituire http://localhost:8000/ServiceModelSamples/service.svc/mex con l'indirizzo dell'endpoint mex del servizio self-hosted.

     Per generare il client in un tipo Visual Basic, utilizzare il comando seguente.

    ```
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb
    ```

     Se il servizio è di tipo indipendente, utilizzare il comando seguente.

    ```
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb
    ```

    > [!NOTE]
    > Per ignorare la generazione della configurazione client, aggiungere il **/noConfig** opzione.

## <a name="see-also"></a>Vedere anche

- [Esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md)
- [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
