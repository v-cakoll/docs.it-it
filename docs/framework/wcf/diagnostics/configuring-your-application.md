---
title: Configurazione dell'applicazione
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 39d8c73809b8c2695ccebb1d69d1c016fd2313d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584636"
---
# <a name="configuring-your-application"></a>Configurazione dell'applicazione
Windows Communication Foundation (WCF) viene utilizzato il sistema di configurazione .NET ed è possibile configurare i servizi nell'ambito computer e dell'applicazione.  
  
 Impostazioni di configurazione definite da WCF si trovano nel `<system.serviceModel>` gruppo di sezioni. Per altre informazioni su come configurare un servizio WCF, vedere gli argomenti seguenti:  
  
-   [Configurazione dei servizi](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Le impostazioni delle configurazioni definite dall'applicazione sono definite nel gruppo di sezioni `<appSettings>`. Per altre informazioni sulle impostazioni dell'applicazione nei file di configurazione .NET, vedere [ \<appSettings >](https://go.microsoft.com/fwlink/?LinkId=95159).  
  
## <a name="using-the-configuration-editor"></a>Utilizzo dell’Editor di configurazione  
 WCF [dello strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) consente agli amministratori e sviluppatori di creare e modificare le impostazioni di configurazione dei servizi WCF tramite un'interfaccia utente grafica. Con questo strumento, è possibile gestire le impostazioni per le associazioni, comportamenti, servizi e diagnostica WCF senza modificare direttamente i file di configurazione XML.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Modifica dei file di configurazione in Visual Studio  
 Per modificare il file di configurazione di un progetto di servizio WCF in Visual Studio, fare clic nella **Esplora soluzioni** e scegliere il **modifica Config WCF** menu di scelta rapida. Verrà avviata il [dello strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
>  Se si modifica il file di configurazione di un progetto di servizio Web WCF in Visual Studio facendo clic su esso in **Esplora soluzioni**, si noti che le **modifica Config WCF** menu di scelta rapida è manca. Per risolvere questo problema, fare clic sul **degli strumenti** dal menu e scegliere **Editor di configurazione del servizio WCF**. Successivamente, è possibile fare doppio clic su un file di configurazione e usare la **modifica Config WCF** menu di scelta rapida.  
  
## <a name="see-also"></a>Vedere anche
- [Strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [Configurazione dei servizi](../../../../docs/framework/wcf/configuring-services.md)
- [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
