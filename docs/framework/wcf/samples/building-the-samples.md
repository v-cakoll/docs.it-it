---
title: Generazione degli esempi Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 2899e7a5-9cb2-4e8d-b8d2-f31391549198
ms.openlocfilehash: 53599b3b1827651b48df9921bb59a679a36ee39c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592619"
---
# <a name="building-the-windows-communication-foundation-samples"></a>Generazione degli esempi Windows Communication Foundation

Gli esempi di Windows Communication Foundation (WCF) possono essere compilati usando l'IDE di Visual Studio o tramite il comando **MSBuild** dalla riga di comando. Entrambe le procedure sono descritte in questo argomento.

> [!NOTE]
> Prima di compilare o eseguire uno degli esempi WCF, verificare di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

## <a name="to-build-the-sample-using-a-command-prompt"></a>Per compilare l'esempio utilizzando il prompt dei comandi

1. Aprire Prompt dei comandi per gli sviluppatori per Visual Studio e passare alla sottodirectory specifica del linguaggio nel percorso della directory in cui è stato installato l'esempio.

2. Digitare `msbuild` nella riga di comando. I file di programma client vengono compilati in *client\bin* e i file di programma del servizio sono compilati in *service\bin*. Se il servizio è ospitato da Internet Information Services (IIS), i file di programma del servizio vengono copiati anche nella directory *servicemodelsamples* e nella relativa sottodirectory *\bin* .

> [!NOTE]
> È necessario impostare gli ACL in *%SystemDrive%\inetpub\wwwroot.* per concedere le autorizzazioni di modifica all'account con cui si esegue. In caso contrario vi saranno errori relativi a eventi post-compilazione. In alternativa, è possibile lasciare le ACL come sono ed eseguire il prompt dei comandi SDK come amministratore.

## <a name="to-build-the-sample-using-visual-studio"></a>Per compilare l'esempio utilizzando Visual Studio

1. Dal menu **file** in Visual Studio selezionare **Apri**  >  **progetto/soluzione**. Passare alla sottodirectory specifica della lingua nella directory in cui è stato installato l'esempio e fare doppio clic sull'icona del file con estensione sln per aprire la soluzione in Visual Studio.

1. Scegliere **Ricompila soluzione**dal menu **Compila** .

   I file di programma client vengono compilati in client\bin, mentre i file del programma del servizio vengono compilati in service\bin. Se il servizio è ospitato in IIS, i file di programma del servizio vengono copiati anche nella directory *servicemodelsamples* e nella sottodirectory *\bin* .

> [!NOTE]
> È necessario impostare ACLs su %systemdrive%\inetpub\wwwroot per concedere autorizzazioni di modifica per l'account in esecuzione. In caso contrario vi saranno errori relativi a eventi post-compilazione. In alternativa, è possibile lasciare le ACL come sono ed eseguire il prompt dei comandi SDK o Visual Studio come amministratore. Anche alcune azioni di Visual Studio (ad esempio allegare un debugger al processo di lavoro ASP.NET) richiedono privilegi amministrativi.

## <a name="setup-batch-files-and-scripts"></a>Impostare file batch e script
 I file batch Setup. exe e Cleanup. exe e gli script devono essere eseguiti da Prompt dei comandi per gli sviluppatori per Visual Studio. Diversi file di installazione e pulizia eseguono attività che richiedono privilegi amministrativi e devono essere avviati con privilegi di questo tipo.

## <a name="important-security-information-about-metadata-endpoints"></a>Importanti informazioni di sicurezza sugli endpoint dei metadati
 Per impedire la divulgazione accidentale di metadati del servizio potenzialmente sensibili, la configurazione predefinita per i servizi di Windows Communication Foundation (WCF) Disabilita la pubblicazione dei metadati. Questo comportamento è protetto per impostazione predefinita, ma significa inoltre che non è possibile usare uno strumento di importazione di metadati (ad esempio Svcutil.exe) per generare il codice client necessario per chiamare il servizio, a meno che il comportamento del servizio di pubblicazione dei metadati non venga abilitato in modo esplicito in fase di configurazione. Per rendere più semplice la sperimentazione con gli esempi, quasi tutti gli esempi espongono un endpoint di pubblicazione dei metadati non protetto. Tali endpoint sono potenzialmente disponibili per utenti anonimi non autenticati e bisogna fare attenzione prima di distribuirli per garantire che la pubblicazione dei metadati di un servizio sia appropriata. Per ulteriori informazioni sulla pubblicazione dei metadati del servizio, vedere l'esempio relativo al [comportamento di pubblicazione dei metadati](metadata-publishing-behavior.md) . Vedere l'esempio di [endpoint dei metadati protetti personalizzato](custom-secure-metadata-endpoint.md) per un esempio di protezione di un endpoint di metadati.

## <a name="exception-handling"></a>Gestione delle eccezioni
 In genere questi esempi non includono la gestione delle eccezioni per focalizzare il codice sull'argomento dell'esempio. Per ulteriori informazioni sulla gestione delle eccezioni, vedere l'esempio relativo alle [eccezioni previste](expected-exceptions.md) .

## <a name="regenerating-clients-and-configuration-with-svcutil"></a>Rigenerazione client e configurazione con Svcutil
 È possibile utilizzare lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per rigenerare il codice client e la configurazione per la maggior parte degli esempi. Alcuni esempi richiedono una configurazione manuale. Ad esempio, se si utilizza Svcutil.exe per rigenerare la configurazione per un esempio che utilizza credenziali del certificato client, si devono specificare manualmente le credenziali precedentemente configurate. Alcuni esempi utilizzano opzioni Svcutil.exe specifiche per influire sul codice generato, queste opzioni sono specificate in argomenti di esempio appositi.

### <a name="to-regenerate-the-client-and-configuration-files"></a>Per rigenerare client e file di configurazione

1. Aprire il prompt dei comandi SDK, quindi spostarsi nella sottodirectory specifica del linguaggio del percorso della directory in cui si è installato l'esempio.

2. Se il servizio è di tipo ospitato sul Web, utilizzare il comando seguente.

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs
    ```

     Se il servizio è di tipo indipendente, digitare il comando seguente.

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /out:generatedClient.cs
    ```

     Sostituire `http://localhost:8000/ServiceModelSamples/service.svc/mex` con l'indirizzo dell'endpoint MEX del servizio indipendente.

     Per generare il client in un tipo Visual Basic, utilizzare il comando seguente.

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb
    ```

     Se il servizio è di tipo indipendente, utilizzare il comando seguente.

    ```console
    svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost:8000/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb
    ```

    > [!NOTE]
    > Per ignorare la generazione della configurazione client, aggiungere l'opzione **/noconfig** .

## <a name="see-also"></a>Vedere anche

- [Esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md)
- [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
