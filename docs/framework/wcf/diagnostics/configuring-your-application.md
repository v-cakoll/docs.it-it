---
title: Configurazione dell'applicazione
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 170583239ed357904e723aebdaef9809938b5123
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="configuring-your-application"></a>Configurazione dell'applicazione
In [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] viene utilizzato il sistema di configurazione .NET ed è possibile configurare i servizi sia nell'ambito del computer che nell'ambito dell'applicazione.  
  
 Le impostazioni di configurazione definite da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] si trovano nel gruppo di sezioni `<system.serviceModel>`. Per ulteriori informazioni su come configurare un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] del servizio, vedere gli argomenti seguenti:  
  
-   [Configurazione dei servizi](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Le impostazioni delle configurazioni definite dall'applicazione sono definite nel gruppo di sezioni `<appSettings>`. Per ulteriori informazioni sulle impostazioni dell'applicazione nei file di configurazione .NET, vedere [ \<appSettings >](http://go.microsoft.com/fwlink/?LinkId=95159).  
  
## <a name="using-the-configuration-editor"></a>Utilizzo dell’Editor di configurazione  
 Il [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] [strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) consente ad amministratori e sviluppatori di creare e modificare le impostazioni di configurazione per [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servizi mediante un'interfaccia utente grafica. Con questo strumento è possibile gestire le impostazioni di associazioni, comportamenti, servizi e diagnostica di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] senza la necessità di modificare direttamente i file di configurazione XML.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Modifica dei file di configurazione in Visual Studio  
 Per modificare il file di configurazione di un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servizio progetto in Visual Studio, farvi clic nel **Esplora soluzioni** e scegliere il **modifica Config WCF** menu di scelta rapida. Verrà avviata la [strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
>  Se si modifica il file di configurazione di un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] progetto servizio Web in Visual Studio facendo clic su esso in **Esplora soluzioni**, si noti che il **modifica Config WCF** menu di scelta rapida è mancante. Per risolvere questo problema, fare clic su di **strumenti** menu, scegliere **Editor di configurazione del servizio WCF**. Successivamente, è possibile fare doppio clic su un file di configurazione e usare il **modifica Config WCF** menu di scelta rapida.  
  
## <a name="see-also"></a>Vedere anche  
 [Strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [Configurazione dei servizi](../../../../docs/framework/wcf/configuring-services.md)  
 [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
