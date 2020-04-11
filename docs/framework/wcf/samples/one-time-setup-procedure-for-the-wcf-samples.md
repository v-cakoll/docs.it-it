---
title: Procedura di installazione singola per gli esempi di Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: a5848ffd-3eb5-432d-812e-bd948ccb6bca
ms.openlocfilehash: 954ec04d2ef1ca7667b4f75a8a6652010b5dbd33
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121626"
---
# <a name="one-time-setup-procedure-for-the-windows-communication-foundation-samples"></a>Procedura di installazione singola per gli esempi di Windows Communication Foundation

La maggior parte degli esempi di Windows Communication Foundation (WCF) sono ospitati in Internet Information Services (IIS) ed eseguiti da una directory virtuale comune. Questa procedura di installazione una tantera crea una cartella sul disco; aggiunge inoltre una directory virtuale a IIS denominato **ServiceModelSamples**.

La directory virtuale **ServiceModelSamples** viene utilizzata per la compilazione e l'esecuzione di tutti gli esempi che utilizzano un servizio ospitato da IIS. Si tratta della sola directory virtuale richiesta per eseguire gli esempi. La compilazione di un esempio determinerà la sostituzione dei servizi distribuiti in precedenza in questa directory virtuale. Solo l'esempio compilato più di recente verrà distribuito e reso disponibile in tale directory.

> [!NOTE]
> Tutti i comandi devono essere eseguiti con un account di amministratore locale. Se si utilizza Windows 7, Windows Vista o Windows Server 2008 R2, è necessario eseguire anche il prompt dei comandi con privilegi elevati. A tale scopo, fare clic con il pulsante destro del mouse sull'icona del prompt dei comandi e quindi **scegliere Esegui come amministratore**. Tutti i comandi illustrati in questo argomento devono essere eseguiti in un prompt dei comandi che dispone delle impostazioni del percorso appropriate.  Il modo più semplice per garantire che questo requisito venga soddisfatto consiste nell'utilizzare il prompt dei comandi di Visual Studio. Per aprire questo prompt, fare clic sul **pulsante Start**, scegliere **Tutti i programmi**, scorrere verso il basso fino a Visual Studio **2010**, selezionare **Visual Studio Tools**, fare clic con il pulsante destro del mouse su Prompt dei comandi di Visual **Studio (2010)** e quindi **scegliere Esegui come amministratore**. Se si dispone di una delle edizioni di Visual Studio Express installate, il prompt dei comandi non sarà disponibile e sarà necessario aggiungere "C:\Windows\Microsoft.Net\Framework\v4.0" al percorso di sistema.

### <a name="one-time-setup-procedure-for-wcf-samples"></a>Procedura di installazione singola per esempi WCF

1. Assicurarsi che ASP.NET sia impostato. Per ulteriori informazioni su come configurare ASP.NET, vedere [Istruzioni per l'hosting di Internet Information Service](internet-information-service-hosting-instructions.md).

2. Assicurarsi che .NET Framework 4 sia installato. Eseguire la ricerca nella directory seguente per v4.0 (o versione **successiva):**

3. Assicurarsi di avere installato Visual Studio 2012 o versione successiva o che il sistema operativo sia Windows Server 2008 SP2 o versione successiva.

4. Eseguire i comandi seguenti. Per ulteriori informazioni sui motivi per cui questi comandi devono essere eseguiti, vedere [IIS Hosted Service Fails](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752252(v=vs.90)).

    > [!WARNING]
    > Se IIS viene reinstallato, nei comandi seguenti sarà necessario eseguirlo nuovamente.

    ```console
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\aspnet_regiis" –i –enable
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\ServiceModelReg.exe" -r
    ```

    > [!WARNING]
    > L'esecuzione `aspnet_regiis –i –enable` del comando renderà l'esecuzione del pool di applicazioni predefinito con .NET Framework 4, che potrebbe produrre problemi di incompatibilità per altre applicazioni nello stesso computer.

5. Seguire le istruzioni del [firewall](firewall-instructions.md) per abilitare le porte utilizzate dagli esempi.

6. Verificare la presenza \<della directory predefinita seguente: InstallDrive>:**WF_WCF_Samples .** Se gli esempi sono stati installati in precedenza, questa è la directory predefinita.

7. Se gli esempi non sono installati, installarli da [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).

8. Dopo l'installazione degli esempi, passare a : \<InstallDrive>**WF_WCF_Samples:\\ **

9. Eseguire il file batch **Setupvroot.bat.** Vengono eseguiti questi passaggi:

    - In IIS verrà creata una directory virtuale denominata ServiceModelSamples.

    - Vengono create nuove directory su disco denominate %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples and %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples\bin.

    Se si preferisce configurare manualmente queste directory, vedere le istruzioni per [l'installazione di Virtual Directory](virtual-directory-setup-instructions.md). Per ripristinare tutte le modifiche apportate in questo passaggio, eseguire cleanupvroot.bat dopo aver terminato di utilizzare gli esempi.

    > [!NOTE]
    > Questa procedura deve essere eseguita solo una volta in un computer, a meno che non venga eseguito cleanupvroot.bat.

10. All'account con cui vengono compilati gli esempi e all'utente con account Servizio di rete è necessario concedere le autorizzazioni per la modifica di %SystemDrive%\inetpub\wwwroot. Durante la compilazione, alcuni esempi ospitati sul Web potrebbero tentare di copiare i file binari compilati nel percorso indicato in precedenza e se non sono state impostate le autorizzazioni appropriate, la compilazione si interromperà. In alternativa, è possibile lasciare le autorizzazioni così come sono ed eseguire il prompt dei comandi SDK o il prompt dei comandi di Visual Studio (2012) come amministratore oppure compilare gli esempi in Visual Studio 2012, anche eseguire come amministratore.

    > [!NOTE]
    > Se questo passaggio non viene completato, tutti gli esempi ospitati in IIS genereranno un errore durante la compilazione. Assicurarsi di impostare correttamente le autorizzazioni oppure eseguire il prompt dei comandi SDK e il prompt dei comandi di Visual Studio (2012) come amministratore.

11. Creare una directory C:\logs nel computer. Alcuni esempi potrebbero prevederne l'esistenza. Verificare che l'account appropriato disponga dell'accesso in scrittura a questa cartella. Per Windows 7, Windows Vista e Windows Server 2008 R2, questo account è **Servizio di rete**. Per Windows Server 2008, l'account è NT Authority-Network Service. Per Windows XP e Windows Server 2003, l'account è ASPNET.

12. Eseguire il file Setupcerttool.bat. Questo file si \<trova nella cartella WF_WCF_Samples InstallPath>.  Tramite questo script verranno eseguite le attività seguenti:

    - Compilazione dello strumento FindPrivateKey.

    - Creazione di una directory denominata %ProgramFiles%\ServiceModelSampleTools.

    - Copia del nuovo strumento FindPrivateKey in questa directory.

    Questo strumento è necessario per gli esempi che utilizzano certificati e sono ospitati in IIS.

    > [!NOTE]
    > Per motivi di sicurezza, dopo aver completato gli esempi, rimuovere la definizione di directory virtuale e le autorizzazioni concesse nei passaggi di installazione illustrati in precedenza eseguendo il file batch denominato Cleanupvroot.bat.

13. Per gli esempi indipendenti (non ospitati in IIS) è necessaria un'autorizzazione per la registrazione degli indirizzi HTTP nel computer in ascolto. L'autorizzazione per una prenotazione dello spazio dei nomi HTTP viene dall'account utente utilizzato per eseguire l'esempio. Per impostazione predefinita, gli account amministratore dispongono delle autorizzazioni per registrare qualsiasi indirizzo HTTP. Agli account non amministratore è necessario concedere l'autorizzazione per gli spazi dei nomi HTTP utilizzati da questi esempi. Per altre informazioni su come configurare le prenotazioni dello spazio dei nomi, vedere [Configuring HTTP and HTTPS](../feature-details/configuring-http-and-https.md) (Configurazione di HTTP e HTTPS).

14. Alcuni esempi richiedono Accodamento messaggi. Per istruzioni sull'installazione, vedere [Installazione di Accodamento messaggi (MSMQ).](installing-message-queuing-msmq.md)

    > [!NOTE]
    > Assicurarsi di avviare il servizio MSMQ prima di eseguire gli esempi per i quali è necessario Accodamento messaggi.

15. Alcuni esempi richiedono l'utilizzo di certificati. Vedere le [Istruzioni di installazione certificato server IIS (Internet Information Services)](iis-server-certificate-installation-instructions.md).
