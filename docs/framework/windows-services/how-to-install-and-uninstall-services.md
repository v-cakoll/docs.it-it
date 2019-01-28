---
title: 'Procedura: installare e disinstallare servizi'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, Windows Services
- installation, Windows Services
- uninstalling Windows Services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
author: ghogen
ms.openlocfilehash: eab291528080b75a07c8f8c3994428eafde94568
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612814"
---
# <a name="how-to-install-and-uninstall-services"></a>Procedura: installare e disinstallare servizi
Se si sta sviluppando un servizio Windows con .NET Framework, è possibile installare rapidamente l'applicazione di servizio tramite un'utilità della riga di comando denominata InstallUtil.exe. Se uno sviluppatore vuole rilasciare un servizio Windows che gli utenti possono installare e disinstallare, può usare InstallShield. Vedere [Distribuzione con Windows Installer](https://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0).  
  
> [!WARNING]
>  Se si vuole disinstallare un servizio dal computer, non seguire i passaggi di questo articolo. Individuare invece il programma o il pacchetto software che ha installato il servizio e quindi scegliere **Installazione applicazioni** nel Pannello di controllo per disinstallare tale programma. Si noti che molti servizi sono parte integrante di Windows. Se vengono rimossi, il sistema potrebbe diventare instabile.  
  
 Per usare i passaggi descritti in questo articolo, è necessario prima aggiungere un programma di installazione del servizio al servizio Windows. Vedere [Procedura dettagliata: creazione di un'applicazione di servizio Windows in Progettazione componenti](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
 I progetti del servizio Windows non possono essere eseguiti direttamente dall'ambiente di sviluppo di Visual Studio premendo F5, perché è necessario installare il servizio prima dell'esecuzione del progetto.  
  
> [!TIP]
>  È possibile avviare **Esplora server** e verificare che il servizio sia stato installato o disinstallato. Per altre informazioni, vedere Procedura: accedere e inizializzare Esplora server/Esplora database.  
  
### <a name="to-install-your-service-manually"></a>Per installare il servizio manualmente  
  
1.  Nel menu **Start** di Windows o nella schermata **Start** scegliere **Visual Studio**, **Strumenti di Visual Studio**, **Prompt dei comandi per gli sviluppatori**.  
  
     Viene visualizzato un prompt dei comandi per gli sviluppatori per Visual Studio.  
  
2.  Accedere alla directory in cui si trova il file eseguibile compilato del progetto.  
  
3.  Eseguire InstallUtil.exe dal prompt dei comandi con l'eseguibile del progetto come parametro:  
  
    ```  
    installutil <yourproject>.exe  
    ```  
  
     Se si usa il prompt dei comandi per gli sviluppatori di Visual Studio, InstallUtil.exe sarà nel percorso di sistema. In caso contrario, è possibile aggiungerlo al percorso o usare il percorso completo per richiamarlo. Questo strumento viene installato con .NET Framework e il percorso è `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`. Ad esempio, per la versione a 32 bit di .NET Framework 4 o 4.5.*, se la directory di installazione di Windows è C:\Windows, il percorso è `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`. Per la versione a 64 bit di .NET Framework 4 o 4.5.\*, il percorso predefinito è `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.  
  
### <a name="to-uninstall-your-service-manually"></a>Per disinstallare il servizio manualmente  
  
1.  Nel menu **Start** di Windows o nella schermata **Start** scegliere **Visual Studio**, **Strumenti di Visual Studio**, **Prompt dei comandi per gli sviluppatori**.  
  
     Viene visualizzato un prompt dei comandi per gli sviluppatori per Visual Studio.  
  
2.  Eseguire InstallUtil.exe dal prompt dei comandi con l'output del progetto come parametro:  
  
    ```  
    installutil /u <yourproject>.exe  
    ```  
  
3.  In alcuni casi, dopo avere eliminato il file eseguibile di un servizio, è possibile che il servizio sia ancora presente nel Registro di sistema. In tal caso, usare il comando [sc delete](/windows-server/administration/windows-commands/sc-delete) per rimuovere la voce per il servizio dal Registro di sistema.  
  
## <a name="see-also"></a>Vedere anche
- [Introduzione alle applicazioni di servizio Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
- [Procedura: creare servizi Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)
- [Procedura: aggiungere programmi di installazione all'applicazione di servizio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
- [Installutil.exe (Strumento Programma di installazione)](../../../docs/framework/tools/installutil-exe-installer-tool.md)
