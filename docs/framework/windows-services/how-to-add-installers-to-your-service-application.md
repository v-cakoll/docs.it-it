---
title: 'Procedura: aggiungere programmi di installazione all''applicazione di servizio'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, deploying
- installation components, adding to services
- installers, adding to services
- Windows Service applications, adding installers
- services, adding installers
- ServiceInstaller class, adding installers to services
- ServiceProcessInstaller class, adding installers to services
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
caps.latest.revision: "14"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 8137e41f92335849916dfc9e9ce72afeb186e73c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-installers-to-your-service-application"></a>Procedura: aggiungere programmi di installazione all'applicazione di servizio
Visual Studio fornisce componenti di installazione che è possono installare le risorse associate alle applicazioni di servizio. Componenti di installazione registrano un singolo servizio sul sistema in cui viene installato e Gestione controllo servizi di informare che il servizio esista. Quando si lavora con un'applicazione di servizio, è possibile selezionare un collegamento nella finestra proprietà per aggiungere automaticamente i programmi di installazione appropriati per il progetto.  
  
> [!NOTE]
>  I valori delle proprietà per il servizio vengono copiati dalla classe di servizio per la classe installer. Se si aggiornano i valori delle proprietà nella classe del servizio, essi non vengono aggiornate automaticamente nel programma di installazione.  
  
 Quando si aggiunge un programma di installazione per il progetto, una nuova classe (che, per impostazione predefinita, denominato `ProjectInstaller`) viene creato nel progetto e le istanze della corretta installazione di componenti vengono creati all'interno di esso. Questa classe funge da punto centrale per tutti i componenti di installazione dal progetto. Ad esempio, se si aggiunge un secondo servizio all'applicazione e fare clic sul collegamento Aggiungi programma di installazione, una seconda classe di installazione non viene creata; al contrario, il componente di installazione aggiuntivi necessari per il secondo servizio viene aggiunto alla classe esistente.  
  
 Non è necessario codice specifico all'interno di programmi di installazione per installare correttamente i servizi. Tuttavia, in alcuni casi potrebbe essere necessario modificare il contenuto dei programmi di installazione se è necessario aggiungere funzionalità speciali per il processo di installazione.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-installers-to-your-service-application"></a>Per aggiungere i programmi di installazione all'applicazione di servizio  
  
1.  In **Esplora**, accesso **progettazione** visualizzazione per il servizio per il quale si desidera aggiungere un componente di installazione.  
  
2.  Fare clic sull'icona della finestra di progettazione per selezionare il servizio stesso, anziché il suo contenuto.  
  
3.  Con la finestra di progettazione in cui lo stato attivo, mouse e quindi fare clic su **Aggiungi programma di installazione**.  
  
     Una nuova classe, `ProjectInstaller`e due componenti di installazione, <xref:System.ServiceProcess.ServiceProcessInstaller> e <xref:System.ServiceProcess.ServiceInstaller>, vengono aggiunti al progetto e i valori delle proprietà per il servizio vengono copiati i componenti.  
  
4.  Fare clic sul <xref:System.ServiceProcess.ServiceInstaller> componente e verificare che il valore della <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> proprietà è impostata sullo stesso valore come il <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> proprietà del servizio stesso.  
  
5.  Per determinare come verrà avviato il servizio, scegliere il <xref:System.ServiceProcess.ServiceInstaller> componente e impostare il <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> proprietà sul valore appropriato.  
  
    |Valore|Risultato|  
    |-----------|------------|  
    |<xref:System.ServiceProcess.ServiceStartMode.Manual>|Il servizio deve essere avviato manualmente dopo l'installazione. Per ulteriori informazioni, vedere [procedura: avviare servizi](../../../docs/framework/windows-services/how-to-start-services.md).|  
    |<xref:System.ServiceProcess.ServiceStartMode.Automatic>|Il servizio verrà avviato automaticamente ogni volta che il riavvio del computer.|  
    |<xref:System.ServiceProcess.ServiceStartMode.Disabled>|Impossibile avviare il servizio.|  
  
6.  Per determinare il contesto di sicurezza in cui verrà eseguito il servizio, scegliere il <xref:System.ServiceProcess.ServiceProcessInstaller> componente e impostare i valori di proprietà appropriata. Per ulteriori informazioni, vedere [procedura: specificare il contesto di sicurezza per i servizi](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).  
  
7.  Eseguire l'override di metodi per il quale è necessario eseguire un'elaborazione personalizzata.  
  
8.  Eseguire i passaggi da 1 a 7 per ogni servizio aggiuntive nel progetto.  
  
    > [!NOTE]
    >  Per ogni servizio aggiuntiva nel progetto, è necessario aggiungere un ulteriore <xref:System.ServiceProcess.ServiceInstaller> componente per il progetto `ProjectInstaller` classe. Il <xref:System.ServiceProcess.ServiceProcessInstaller> componente aggiunto nel passaggio 3. funziona con tutti i programmi di installazione singolo servizio nel progetto.  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione alle applicazioni di servizio Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Procedura: installare e disinstallare servizi](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [Procedura: avviare servizi](../../../docs/framework/windows-services/how-to-start-services.md)  
 [Procedura: specificare il contesto di sicurezza per i servizi](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)
