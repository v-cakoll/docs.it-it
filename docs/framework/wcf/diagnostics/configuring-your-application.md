---
title: Configurazione dell'applicazione
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: e096f4b64ada8b142e8b82c8877eec7f1b84637c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939808"
---
# <a name="configuring-your-application"></a>Configurazione dell'applicazione
Windows Communication Foundation (WCF) usa il sistema di configurazione .NET e consente di configurare i servizi nell'ambito del computer e dell'applicazione.  
  
 Le impostazioni di configurazione definite da WCF si trovano `<system.serviceModel>` nel gruppo di sezioni. Per ulteriori informazioni sulla configurazione di un servizio WCF, vedere gli argomenti seguenti:  
  
- [Configurazione dei servizi](../../../../docs/framework/wcf/configuring-services.md)  
  
- [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Le impostazioni delle configurazioni definite dall'applicazione sono definite nel gruppo di sezioni `<appSettings>`. Per ulteriori informazioni sulle impostazioni dell'applicazione nei file di configurazione .NET, vedere [ \<appSettings >](https://go.microsoft.com/fwlink/?LinkId=95159).  
  
## <a name="using-the-configuration-editor"></a>Utilizzo dell’Editor di configurazione  
 Lo [strumento Editor di configurazione WCF (SvcConfigEditor. exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) consente agli amministratori e agli sviluppatori di creare e modificare le impostazioni di configurazione per i servizi WCF tramite un'interfaccia utente grafica. Con questo strumento è possibile gestire le impostazioni per associazioni, comportamenti, servizi e diagnostica WCF senza modificare direttamente i file di configurazione XML.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Modifica dei file di configurazione in Visual Studio  
 Per modificare il file di configurazione di un progetto servizio WCF in Visual Studio, fare clic con il pulsante destro del mouse su di esso in **Esplora soluzioni** e scegliere la voce del menu di scelta rapida **modifica configurazione WCF** . Verrà avviato lo [strumento Editor di configurazione (SvcConfigEditor. exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
> Se si modifica il file di configurazione di un progetto di servizio Web WCF in Visual Studio facendo clic con il pulsante destro del mouse su di esso in **Esplora soluzioni**, si noti che la voce del menu di scelta rapida **modifica configurazione WCF** è mancante. Per aggirare questo problema, fare clic sul menu **strumenti** e scegliere **Editor configurazione servizio WCF**. Successivamente, è possibile fare clic con il pulsante destro del mouse su un file di configurazione e utilizzare la voce del menu di scelta rapida **modifica configurazione WCF** .  
  
## <a name="see-also"></a>Vedere anche

- [Strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [Configurazione dei servizi](../../../../docs/framework/wcf/configuring-services.md)
- [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
