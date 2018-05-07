---
title: 'Procedura: installare e configurare componenti di attivazione WCF'
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: f362bd1e4a644488e85cdeca674d46ca340bde05
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a>Procedura: installare e configurare componenti di attivazione WCF
In questo argomento vengono descritti i passaggi richiesti per impostare il servizio Attivazione processo Windows (anche noto come WAS) in [!INCLUDE[wv](../../../../includes/wv-md.md)] per Windows Communication Foundation (WCF) di ospitare servizi che non comunicano su HTTP i protocolli di rete. Nelle sezioni seguenti vengono spiegati i passaggi relativi a tale configurazione:  
  
-   Installare (o confermare l'installazione di) i componenti di attivazione di WCF.  
  
-   Configurare WAS per supportare un protocollo non HTTP. Nella procedura seguente viene illustrato come configurare [!INCLUDE[wv](../../../../includes/wv-md.md)] per l'attivazione TCP.  
  
 Dopo l'installazione e configurazione WAS, vedere [procedura: ospitare un servizio WCF in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) per le procedure creare un servizio WCF che espone un endpoint non HTTP che utilizza WAS.  
  
### <a name="to-install-the-wcf-non-http-activation-components"></a>Per installare i componenti di attivazione WCF non HTTP  
  
1.  Fare clic su di **avviare** pulsante e quindi fare clic su **Pannello di controllo**.  
  
2.  Fare clic su **programmi**, quindi fare clic su **programmi e funzionalità**.  
  
3.  Nel **attività** menu, fare clic su **o disattivazione delle funzionalità Windows attivare**.  
  
4.  Individuare il nodo [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], selezionarlo e quindi espanderlo.  
  
5.  Selezionare il **componenti di attivazione Non Http di WCF** e salvare l'impostazione.  
  
### <a name="to-configure-the-was-to-support-tcp-activation"></a>Per configurare WAS per supportare l'attivazione TCP  
  
1.  Per supportare l'attivazione net.tcp, è prima necessario associare il sito Web predefinito a una porta net.tcp. A tale fine, utilizzare Appcmd.exe, installato con il set di strumenti di gestione di [!INCLUDE[iisver](../../../../includes/iisver-md.md)]. In una finestra del prompt dei comandi a livello di amministratore, eseguire il comando seguente.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  Questo comando è una singola riga di testo. Il comando aggiunge un'associazione del sito net.tcp al sito Web predefinito in ascolto sulla porta TCP 808 con qualsiasi nome host.  
  
2.  Anche se tutte le applicazioni all'interno di un sito condividono un'associazione net.tcp comune, ognuna di esse può attivare il supporto net.tcp individualmente. Per attivare net.tcp per l'applicazione, eseguire il comando seguente da un prompt dei comandi a livello di amministratore.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app   
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp  
    ```  
  
    > [!NOTE]
    >  Questo comando è una singola riga di testo. Questo comando abilita la /\<*applicazione WCF*> dell'applicazione per l'accesso tramite entrambi http://localhost  */ \<applicazione WCF >* e net.tcp:// localhost /*\<applicazione WCF >*.  
  
     Rimuovere l'associazione del sito net.tcp aggiunta per questo esempio.  
  
     Per comodità, i due passaggi seguenti vengono implementati in un file batch chiamato RemoveNetTcpSiteBinding.cmd situato nella directory di esempio.  
  
    1.  Rimuovere net.tcp dall'elenco dei protocolli attivati tramite il comando seguente in una finestra del prompt dei comandi a livello di amministratore.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  Questo comando è una singola riga di testo.  
  
    2.  Rimuovere l'associazione del sito net.tcp tramite il comando seguente in una finestra del prompt dei comandi con privilegi elevati:  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  Questo comando è una singola riga di testo.  
  
### <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a>Per rimuovere net.tcp dall'elenco dei protocolli attivati  
  
1.  Per rimuovere net.tcp dall'elenco dei protocolli attivati, eseguire il comando seguente in una finestra del prompt dei comandi a livello di amministratore.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
    ```  
  
    > [!NOTE]
    >  Questo comando è una singola riga di testo.  
  
### <a name="to-remove-the-nettcp-site-binding"></a>Per rimuovere l'associazione del sito net.tcp  
  
1.  Per rimuovere l'associazione del sito net.tcp, eseguire il comando seguente in una finestra del prompt dei comandi a livello di amministratore.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
    -bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  Questo comando è una singola riga di testo.  
  
## <a name="see-also"></a>Vedere anche  
 [Attivazione TCP](../../../../docs/framework/wcf/samples/tcp-activation.md)  
 [Attivazione MSMQ](../../../../docs/framework/wcf/samples/msmq-activation.md)  
 [Attivazione di NamedPipe](../../../../docs/framework/wcf/samples/namedpipe-activation.md)  
 [Windows Server AppFabric con funzionalità di Hosting](http://go.microsoft.com/fwlink/?LinkId=201276)
