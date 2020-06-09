---
title: Istruzioni di installazione certificato server IIS (Internet Information Services)
ms.date: 03/30/2017
ms.assetid: 11281490-d2ac-4324-8f33-e7714611a34b
ms.openlocfilehash: 301a10c615a13a42e1a6e1b89d2724476ca4fbae
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594660"
---
# <a name="internet-information-services-iis-server-certificate-installation-instructions"></a>Istruzioni di installazione certificato server IIS (Internet Information Services)
Per eseguire gli esempi che comunicano in modo sicuro con IIS (Internet Information Services) è necessario creare e installare un certificato server.  
  
## <a name="step-1-creating-certificates"></a>Passaggio 1. Creazione di certificati  
 Per creare un certificato per il computer, aprire un Prompt dei comandi per gli sviluppatori per Visual Studio con privilegi di amministratore ed eseguire il file Setup. bat incluso in tutti gli esempi che usano la comunicazione protetta con IIS. Assicurarsi che il percorso includa la cartella contenente Makecert.exe prima di eseguire questo file batch. Il comando seguente viene utilizzato per creare il certificato nel file Setup.bat.  
  
```console  
makecert -sr LocalMachine -ss My -n CN=ServiceModelSamples-HTTPS-Server -sky exchange -sk ServiceModelSamples-HTTPS-Key  
```  
  
## <a name="step-2-installing-certificates"></a>Passaggio 2: Installazione dei certificati  
 I passaggi necessari per installare i certificati appena creati dipendono dalla versione di IIS che si sta utilizzando.  
  
#### <a name="to-install-iis-on-iis-51-windows-xp-and-iis-60-windows-server-2003"></a>Installazione di IIS su IIS 5.1 (Windows XP) e IIS 6.0 (Windows Server 2003)  
  
1. Aprire lo snap-in MMC della Gestione Internet Information Services (IIS).  
  
2. Fare clic con il pulsante destro del mouse sul sito Web predefinito e scegliere **Proprietà**.  
  
3. Selezionare la scheda **sicurezza directory** .  
  
4. Fare clic sul pulsante **certificato server** . Verrà avviata la Procedura guidata certificati server Web.  
  
5. Completare la procedura guidata. Selezionare l'opzione per assegnare un certificato. Selezionare il certificato server HTTPS ServiceModelSamples nell'elenco di certificati visualizzati.  
  
     ![Gestione guidata certificati IIS](media/iiscertificate-wizard.GIF "IISCertificate_Wizard")  
  
6. Testare l'accesso al servizio in un browser tramite l'indirizzo HTTPS `https://localhost/servicemodelsamples/service.svc` .  
  
#### <a name="if-ssl-was-previously-configured-by-using-httpcfgexe"></a>Se SSL è stato precedentemente configurato utilizzando Httpcfg.exe  
  
1. Utilizzare Makecert.exe (o eseguire Setup.bat) per creare il certificato server.  
  
2. Eseguire la gestione IIS e installare il certificato secondo i passaggi precedenti.  
  
3. Aggiungere le righe di codice seguenti al programma client.  
  
> [!IMPORTANT]
> Questo codice è necessario solo per certificati di prova come ad esempio quelli creati da Makecert.exe. Non è una pratica consigliabile per il codice di produzione.  
  
```csharp  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
#### <a name="to-install-iis-on-iis-70-windows-vista-and-windows-server-2008"></a>Per installare IIS su IIS 7.0 (Windows Vista e Windows Server 2008)  
  
1. Dal menu **Start** fare clic su **Esegui**, quindi digitare **inetmgr** per aprire lo snap-in MMC Internet Information Services (IIS).  
  
2. Fare clic con il pulsante destro del mouse sul **sito Web predefinito** e scegliere **Modifica binding...**  
  
3. Fare clic sul pulsante **Aggiungi** della finestra di dialogo **binding sito** .  
  
4. Selezionare **https** dall'elenco a discesa **tipo** .  
  
5. Selezionare **servicemodelsamples-https-server** dall'elenco a discesa **certificato SSL** e fare clic su **OK**.  
  
6. Testare l'accesso al servizio in un browser tramite l'indirizzo HTTPS `https://localhost/servicemodelsamples/service.svc` .  
  
> [!NOTE]
> Dato che il certificato di prova appena installato non è un certificato attendibile, possono essere visualizzati avvisi di sicurezza di Internet Explorer aggiuntivi quando si visitano indirizzi Web locali protetti da questo certificato.  
  
## <a name="removing-certificates"></a>Rimozione dei certificati  
  
- Utilizzare Gestione Internet Information Services come illustrato in precedenza, ma rimuovere il certificato o l'associazione anziché aggiungerlo.  
  
- Rimuovere il certificato del computer utilizzando il comando seguente.  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:443  
    ```
