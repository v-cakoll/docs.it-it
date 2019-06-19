---
title: 'Procedura: Installare e disinstallare i servizi Windows'
ms.date: 02/05/2019
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, apps, Windows services
- installation, Windows services
- uninstalling Windows services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
author: ghogen
ms.openlocfilehash: 4f6e25467e713263ab5cdecc08078153098fdede
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690686"
---
# <a name="how-to-install-and-uninstall-windows-services"></a>Procedura: Installare e disinstallare i servizi Windows

Se si sta sviluppando un servizio Windows con .NET Framework, è possibile installare rapidamente l'app del servizio usando l'utilità della riga di comando [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md). Gli sviluppatori che vogliono rilasciare un servizio Windows che gli utenti possono installare e disinstallare devono usare InstallShield. Per altre informazioni, vedere [Creare un pacchetto di installazione (client Windows)](https://docs.microsoft.com/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).

> [!WARNING]
> Se si vuole disinstallare un servizio dal computer, non seguire i passaggi di questo articolo. Individuare invece il programma o il pacchetto software che ha installato il servizio e quindi scegliere **App** in Impostazioni per disinstallare tale programma. Si noti che molti servizi sono parte integrante di Windows. Se vengono rimossi, il sistema potrebbe diventare instabile.

Per usare i passaggi descritti in questo articolo, è necessario prima aggiungere un programma di installazione del servizio al servizio Windows. Per altre informazioni, vedere [Procedura dettagliata: Creare un'app di servizio di Windows](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).

Non è possibile eseguire i progetti del servizio Windows direttamente dall'ambiente di sviluppo di Visual Studio premendo F5. Prima di eseguire il progetto, è necessario installare il servizio nel progetto.

> [!TIP]
> È possibile usare **Esplora server** e verificare se il servizio è stato installato o disinstallato. Per altre informazioni, vedere [How to use Server Explorer in Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio) (Come usare Esplora server in Visual Studio).

### <a name="install-your-service-manually"></a>Installare il servizio manualmente

1. Dal menu **Start** selezionare la directory **Visual Studio \<*versione*>**, quindi selezionare **Prompt dei comandi per gli sviluppatori per VS \<*versione*>**.

     Viene visualizzato il prompt dei comandi per gli sviluppatori per Visual Studio.

2. Accedere alla directory in cui si trova il file eseguibile compilato del progetto.

3. Eseguire *InstallUtil.exe* dal prompt dei comandi con l'eseguibile del progetto come parametro:

    ```console
    installutil <yourproject>.exe
    ```

     Se si usa il prompt dei comandi per gli sviluppatori di Visual Studio, *InstallUtil.exe* sarà nel percorso di sistema. In caso contrario, è possibile aggiungerlo al percorso o usare il percorso completo per richiamarlo. Questo strumento viene installato con .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<versione framework\>*.

     Ad esempio:
     - Per la versione a 32 bit di .NET Framework 4 o 4.5 e versioni successive, se è la directory di installazione di Windows è *C:\Windows*, il percorso predefinito è *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.
     - Per la versione a 64 bit di .NET Framework 4 o 4.5 e versioni successive, il percorso predefinito è *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.

### <a name="uninstall-your-service-manually"></a>Disinstallare il servizio manualmente

1. Dal menu **Start** selezionare la directory **Visual Studio \<*versione*>**, quindi selezionare **Prompt dei comandi per gli sviluppatori per VS \<*versione*>**.

     Viene visualizzato il prompt dei comandi per gli sviluppatori per Visual Studio.

2. Eseguire *InstallUtil.exe* dal prompt dei comandi con l'output del progetto come parametro:

    ```console
    installutil /u <yourproject>.exe
    ```

3. Dopo avere eliminato il file eseguibile di un servizio, è possibile che il servizio sia ancora presente nel Registro di sistema. In questo caso usare il comando [sc delete](/windows-server/administration/windows-commands/sc-delete) per rimuovere la voce per il servizio dal Registro di sistema.

## <a name="see-also"></a>Vedere anche

- [Introduzione alle applicazioni di servizio di Windows](../windows-services/introduction-to-windows-service-applications.md)
- [Procedura: Creare servizi Windows](../windows-services/how-to-create-windows-services.md)
- [Procedura: Aggiungere programmi di installazione all'applicazione di servizio](../windows-services/how-to-add-installers-to-your-service-application.md)
- [Installutil.exe (Strumento Programma di installazione)](../tools/installutil-exe-installer-tool.md)
