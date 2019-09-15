---
title: 'Procedura: Installare e configurare componenti di attivazione WCF'
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: 70eab39e4bb24dfd1cdd6abc5216e50126ef1f4c
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972187"
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a>Procedura: Installare e configurare componenti di attivazione WCF

In questo argomento vengono descritti i passaggi necessari per configurare il servizio di attivazione dei processi di Windows (anche [!INCLUDE[wv](../../../../includes/wv-md.md)] noto come was) in per ospitare i servizi di Windows Communication Foundation (WCF) che non comunicano tramite protocolli di rete http. Nelle sezioni seguenti vengono spiegati i passaggi relativi a tale configurazione:

- Installare o confermare l'installazione dei componenti di attivazione WCF.

- Configurare WAS per supportare un protocollo non HTTP. Nella procedura seguente viene illustrato come configurare [!INCLUDE[wv](../../../../includes/wv-md.md)] per l'attivazione TCP.

Dopo l'installazione e la configurazione di [was, vedere Procedura: Ospitare un servizio WCF in was](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) per le procedure per la creazione di un servizio WCF che espone un endpoint non http che utilizza was.

## <a name="to-install-the-wcf-non-http-activation-components"></a>Per installare i componenti di attivazione WCF non HTTP

1. Fare clic sul pulsante **Start** , quindi scegliere **Pannello di controllo**.

2. Fare clic su **programmi**, quindi fare clic su **programmi e funzionalità**.

3. Nel menu **attività** fare clic **su attivazione o disattivazione delle funzionalità Windows**.

4. Trovare il nodo WinFX, selezionare e quindi espanderlo.

5. Selezionare la casella **componenti di attivazione non HTTP WCF** e salvare l'impostazione.

## <a name="to-configure-the-was-to-support-tcp-activation"></a>Per configurare WAS per supportare l'attivazione TCP

1. Per supportare l'attivazione net.tcp, è prima necessario associare il sito Web predefinito a una porta net.tcp. A tale scopo, è possibile utilizzare Appcmd. exe, installato con il set di strumenti di gestione di IIS 7,0. In una finestra del prompt dei comandi a livello di amministratore, eseguire il comando seguente.

    ```console
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > Questo comando è una singola riga di testo. Il comando aggiunge un'associazione del sito net.tcp al sito Web predefinito in ascolto sulla porta TCP 808 con qualsiasi nome host.

2. Anche se tutte le applicazioni all'interno di un sito condividono un'associazione net.tcp comune, ognuna di esse può attivare il supporto net.tcp individualmente. Per attivare net.tcp per l'applicazione, eseguire il comando seguente da un prompt dei comandi a livello di amministratore.

    ```console
    %windir%\system32\inetsrv\appcmd.exe set app
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp
    ```

    > [!NOTE]
    > Questo comando è una singola riga di testo. Questo comando Abilita l'accesso\<all'applicazione/*WCF*> applicazione tramite `http://localhost/<WCF Application>` e `net.tcp://localhost/<WCF Application>`.

     Rimuovere l'associazione del sito net.tcp aggiunta per questo esempio.

     Per comodità, i due passaggi seguenti vengono implementati in un file batch chiamato RemoveNetTcpSiteBinding.cmd situato nella directory di esempio.

    1. Rimuovere net.tcp dall'elenco dei protocolli attivati tramite il comando seguente in una finestra del prompt dei comandi a livello di amministratore.

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
        ```

        > [!NOTE]
        > Questo comando è una singola riga di testo.

    2. Rimuovere l'associazione del sito net.tcp tramite il comando seguente in una finestra del prompt dei comandi con privilegi elevati:

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        --bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!NOTE]
        > Questo comando è una singola riga di testo.

## <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a>Per rimuovere net.tcp dall'elenco dei protocolli attivati

1. Per rimuovere net.tcp dall'elenco dei protocolli attivati, eseguire il comando seguente in una finestra del prompt dei comandi a livello di amministratore.

    ```console
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
    ```

    > [!NOTE]
    > Questo comando è una singola riga di testo.

## <a name="to-remove-the-nettcp-site-binding"></a>Per rimuovere l'associazione del sito net.tcp

1. Per rimuovere l'associazione del sito net.tcp, eseguire il comando seguente in una finestra del prompt dei comandi a livello di amministratore.

    ```console
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
    -bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > Questo comando è una singola riga di testo.

## <a name="see-also"></a>Vedere anche

- [Attivazione TCP](../../../../docs/framework/wcf/samples/tcp-activation.md)
- [Attivazione MSMQ](../../../../docs/framework/wcf/samples/msmq-activation.md)
- [Attivazione di NamedPipe](../../../../docs/framework/wcf/samples/namedpipe-activation.md)
- [Funzionalità di hosting di Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=201276)
