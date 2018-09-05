---
title: Procedura di installazione singola per gli esempi di Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: a5848ffd-3eb5-432d-812e-bd948ccb6bca
ms.openlocfilehash: 3c3c5934cbbc7dd68f03d888aa0594f9ff61c225
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43539095"
---
# <a name="one-time-setup-procedure-for-the-windows-communication-foundation-samples"></a>Procedura di installazione singola per gli esempi di Windows Communication Foundation
La maggior parte degli esempi Windows Communication Foundation (WCF) sono ospitata in Internet Information Services (IIS) ed eseguire da una directory virtuale comune. Questa procedura di installazione singola crea una cartella sul disco. Aggiunge inoltre una directory virtuale IIS denominato **ServiceModelSamples**.  
  
 Il **ServiceModelSamples** directory virtuale viene usato per compilare ed eseguire tutti gli esempi che utilizzano un servizio ospitato da IIS. Si tratta della sola directory virtuale richiesta per eseguire gli esempi. La compilazione di un esempio determinerà la sostituzione dei servizi distribuiti in precedenza in questa directory virtuale. Solo l'esempio compilato più di recente verrà distribuito e reso disponibile in tale directory.  
  
> [!NOTE]
>  Tutti i comandi devono essere eseguiti con un account di amministratore locale. Se si utilizza Windows 7, [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] o Windows Server 2008 R2, sarà inoltre necessario eseguire il prompt dei comandi con privilegi elevati. A tale scopo, fare doppio clic sull'icona del prompt dei comandi e quindi scegliere **Esegui come amministratore**. Tutti i comandi illustrati in questo argomento devono essere eseguiti in un prompt dei comandi che dispone delle impostazioni del percorso appropriate.  Il modo più semplice per garantire che questo requisito venga soddisfatto consiste nell'utilizzare il prompt dei comandi di Visual Studio. Per aprire questo prompt, fare clic su **avviare**, selezionare **tutti i programmi**, scorrere verso il basso **Visual Studio 2010**, selezionare **Visual Studio Tools**, Fare doppio clic su **prompt dei comandi di Visual Studio (2010)**, quindi fare clic su **Esegui come amministratore**. Se si dispone di una delle edizioni di Visual Studio Express installate, il prompt dei comandi non sarà disponibile e sarà necessario aggiungere "C:\Windows\Microsoft.Net\Framework\v4.0" al percorso di sistema.  
  
### <a name="one-time-setup-procedure-for-wcf-samples"></a>Procedura di installazione singola per esempi WCF  
  
1.  Assicurarsi che [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] sia configurato. Per altre informazioni su come configurare [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], vedere [istruzioni di Hosting Internet Information Services](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md).  
  
2.  Assicurarsi che [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] sia installato. Cercare le seguenti directory per v4.0 (o versioni successive): **\Windows\Microsoft.NET\Framework.**  
  
3.  Se [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] non è installato, e il sistema operativo non è Windows Server 2008 SP2 o versioni successive, installare [aggiornamento rapido 251798](https://go.microsoft.com/fwlink/?LinkId=184693).  
  
4.  Eseguire i comandi seguenti: Per altre informazioni sui motivi per cui è necessario eseguire questi comandi, vedere [IIS ospitata servizio ha esito negativo](https://msdn.microsoft.com/library/ee5499fc-1b10-4cda-a9b1-13dba70f05f8).  
  
    > [!WARNING]
    >  Se IIS viene reinstallato, nei comandi seguenti sarà necessario eseguirlo nuovamente.  
  
    ```  
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\aspnet_regiis" –i –enable  
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\ServiceModelReg.exe" -r  
    ```  
  
    > [!WARNING]
    >  Esecuzione del comando `aspnet_regiis –i –enable` renderà esecuzione usando il Pool di applicazioni predefinito [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], che potrebbe produrre problemi di incompatibilità per altre applicazioni nello stesso computer.  
  
5.  Seguire le [istruzioni del Firewall](../../../../docs/framework/wcf/samples/firewall-instructions.md) per abilitare le porte utilizzate dagli esempi.  
  
6.  Cercare la directory predefinita seguente: \<Unitàinstallazione >:**\wf_wcf_samples.**. Se gli esempi sono stati installati in precedenza, questa è la directory predefinita.  
  
7.  Se gli esempi non sono installati, installarli dal percorso di download di esempi per [Visual c#](https://go.microsoft.com/fwlink/?LinkId=190939) oppure [Visual Basic](https://go.microsoft.com/fwlink/?LinkID=193373).  
  
8.  Dopo l'installazione degli esempi, passare a: \<Unitàinstallazione >:**\WF_WCF_Samples\WCF\Setup\\**  
  
9. Eseguire la **setupvroot** file batch. Vengono eseguiti i passaggi seguenti.  
  
    -   In IIS verrà creata una directory virtuale denominata ServiceModelSamples.  
  
    -   Vengono create nuove directory su disco denominate %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples and %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples\bin.  
  
     Se si preferisce configurare manualmente queste directory, vedere la [istruzioni di configurazione di Directory virtuale](../../../../docs/framework/wcf/samples/virtual-directory-setup-instructions.md). Per ripristinare tutte le modifiche apportate in questo passaggio, eseguire cleanupvroot.bat dopo aver terminato di utilizzare gli esempi.  
  
    > [!NOTE]
    >  Questa procedura deve essere eseguita solo una volta in un computer, a meno che non venga eseguito cleanupvroot.bat.  
  
10. All'account con cui vengono compilati gli esempi e all'utente con account Servizio di rete è necessario concedere le autorizzazioni per la modifica di %SystemDrive%\inetpub\wwwroot. Durante la compilazione, alcuni esempi ospitati sul Web potrebbero tentare di copiare i file binari compilati nel percorso indicato in precedenza e se non sono state impostate le autorizzazioni appropriate, la compilazione si interromperà. In alternativa, è possibile lasciare invariate le autorizzazioni ed eseguire il prompt dei comandi SDK o il prompt dei comandi di Visual Studio (2012) come amministratore o compilare gli esempi in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], sempre come amministratore.  
  
    > [!NOTE]
    >  Se questo passaggio non viene completato, tutti gli esempi ospitati in IIS genereranno un errore durante la compilazione. Assicurarsi di impostare correttamente le autorizzazioni oppure eseguire il prompt dei comandi SDK e il prompt dei comandi di Visual Studio (2012) come amministratore.  
  
11. Creare una directory C:\logs nel computer. Alcuni esempi potrebbero prevederne l'esistenza. Verificare che l'account appropriato disponga dell'accesso in scrittura a questa cartella. Per Windows 7, [!INCLUDE[wv](../../../../includes/wv-md.md)], e Windows Server 2008 R2, questo account viene **Network Service**. Per [!INCLUDE[lserver](../../../../includes/lserver-md.md)], l'account è NT Authority\Network Service. Per [!INCLUDE[wxp](../../../../includes/wxp-md.md)] e [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], l'account è ASPNET.  
  
12. Eseguire il file Setupcerttool.bat. Questo file si trova nel \<InstallPath > cartella \WF_WCF_Samples\WCF\Setup\.  Tramite questo script verranno eseguite le attività seguenti:  
  
    -   Compilazione dello strumento FindPrivateKey.  
  
    -   Creazione di una directory denominata %ProgramFiles%\ServiceModelSampleTools.  
  
    -   Copia del nuovo strumento FindPrivateKey in questa directory.  
  
     Questo strumento è necessario per gli esempi che utilizzano certificati e sono ospitati in IIS.  
  
    > [!NOTE]
    >  Per motivi di sicurezza, dopo aver completato gli esempi, rimuovere la definizione di directory virtuale e le autorizzazioni concesse nei passaggi di installazione illustrati in precedenza eseguendo il file batch denominato Cleanupvroot.bat.  
  
13. Per gli esempi indipendenti (non ospitati in IIS) è necessaria un'autorizzazione per la registrazione degli indirizzi HTTP nel computer in ascolto. L'autorizzazione per una prenotazione dello spazio dei nomi HTTP viene dall'account utente utilizzato per eseguire l'esempio. Per impostazione predefinita, gli account amministratore dispongono delle autorizzazioni per registrare qualsiasi indirizzo HTTP. Agli account non amministratore è necessario concedere l'autorizzazione per gli spazi dei nomi HTTP utilizzati da questi esempi. Per altre informazioni su come configurare le prenotazioni dello spazio dei nomi, vedere [Configuring HTTP and HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md) (Configurazione di HTTP e HTTPS).  
  
14. Alcuni esempi richiedono Accodamento messaggi. Visualizzare [installazione di Accodamento messaggi (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md) per le istruzioni di installazione.  
  
    > [!NOTE]
    >  Assicurarsi di avviare il servizio MSMQ prima di eseguire gli esempi per i quali è necessario Accodamento messaggi.  
  
15. Alcuni esempi richiedono l'utilizzo di certificati. Visualizzare [istruzioni di installazione certificato Server (IIS) di Internet Information Services](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).  
  
## <a name="see-also"></a>Vedere anche
