---
title: "Procedura: aggiungere programmi di installazione all'applicazione di servizio"
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, deploying
- installation components, adding to services
- installers, adding to services
- Windows Service applications, adding installers
- services, adding installers
- ServiceInstaller class, adding installers to services
- ServiceProcessInstaller class, adding installers to services
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
author: ghogen
manager: douge
ms.openlocfilehash: faece1d7ee752e4c17f39027ff8a97fc95ed451b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514360"
---
# <a name="how-to-add-installers-to-your-service-application"></a>Procedura: aggiungere programmi di installazione all'applicazione di servizio
Visual Studio include componenti di installazione che consentono di installare le risorse associate alle applicazioni di servizio. I componenti di installazione registrano un singolo servizio nel sistema in cui viene installato e informazione Gestione controllo servizi dell'esistenza del servizio. Quando si lavora con un'applicazione di servizio, è possibile selezionare un collegamento nella finestra Proprietà per aggiungere automaticamente i programmi di installazione appropriati al progetto.  
  
> [!NOTE]
>  I valori delle proprietà per il servizio vengono copiati dalla classe del servizio alla classe del programma di installazione. Se si aggiornano i valori delle proprietà nella classe del servizio, essi non vengono aggiornati automaticamente nel programma di installazione.  
  
 Quando si aggiunge un programma di installazione al progetto, nel progetto viene creata una nuova classe (denominata `ProjectInstaller` per impostazione predefinita) e all'interno di tale classe vengono create le istanze dei componenti di installazione appropriati. Questa classe funge da punto centrale per tutti i componenti di installazione richiesti dal progetto. Ad esempio, se si aggiunge un secondo servizio all'applicazione e si fa clic sul collegamento Aggiungi programma di installazione, non viene creata una seconda classe per il programma di installazione, ma il componente di installazione aggiuntivo necessario per il secondo servizio viene invece aggiunto alla classe esistente.  
  
 Non è necessario codice specifico all'interno dei programmi di installazione per installare correttamente i servizi. Tuttavia, in alcuni casi potrebbe essere necessario modificare il contenuto dei programmi di installazione se è necessario aggiungere funzionalità speciali al processo di installazione.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-installers-to-your-service-application"></a>Per aggiungere programmi di installazione all'applicazione di servizio  
  
1.  In **Esplora soluzioni** accedere alla visualizzazione **Progettazione** per il servizio per il quale si vuole aggiungere un componente di installazione.  
  
2.  Fare clic sullo sfondo della finestra di progettazione per selezionare il servizio anziché il suo contenuto.  
  
3.  Nella finestra di progettazione fare clic con il pulsante destro del mouse e scegliere **Aggiungi programma di installazione**.  
  
     Al progetto vengono aggiunti una nuova classe `ProjectInstaller` e due componenti di installazione, <xref:System.ServiceProcess.ServiceProcessInstaller> e <xref:System.ServiceProcess.ServiceInstaller>, quindi i valori delle proprietà per il servizio vengono copiati nei componenti.  
  
4.  Fare clic sul componente <xref:System.ServiceProcess.ServiceInstaller> e verificare che il valore della proprietà <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> sia impostato sullo stesso valore della proprietà <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> del servizio stesso.  
  
5.  Per determinare come verrà avviato il servizio, fare clic sul componente <xref:System.ServiceProcess.ServiceInstaller> e impostare la proprietà <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> sul valore appropriato.  
  
    |Valore|Risultato|  
    |-----------|------------|  
    |<xref:System.ServiceProcess.ServiceStartMode.Manual>|Il servizio deve essere avviato manualmente dopo l'installazione. Per altre informazioni, vedere [Procedura: Avviare servizi](../../../docs/framework/windows-services/how-to-start-services.md).|  
    |<xref:System.ServiceProcess.ServiceStartMode.Automatic>|Il servizio verrà avviato automaticamente a ogni riavvio del computer.|  
    |<xref:System.ServiceProcess.ServiceStartMode.Disabled>|Impossibile avviare il servizio.|  
  
6.  Per determinare il contesto di sicurezza in cui verrà eseguito il servizio, fare clic sul componente <xref:System.ServiceProcess.ServiceProcessInstaller> e impostare i valori di proprietà appropriati. Per altre informazioni, vedere [Procedura: Specificare il contesto di sicurezza per i servizi](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).  
  
7.  Eseguire l'override degli eventuali metodi che richiedono un'elaborazione personalizzata.  
  
8.  Eseguire i passaggi da 1 a 7 per ogni servizio aggiuntivo nel progetto.  
  
    > [!NOTE]
    >  Per ogni servizio aggiuntivo nel progetto, è necessario aggiungere un ulteriore componente <xref:System.ServiceProcess.ServiceInstaller> alla classe `ProjectInstaller` del progetto. Il componente <xref:System.ServiceProcess.ServiceProcessInstaller> aggiunto nel passaggio 3 funziona con tutti i programmi di installazione dei singoli servizi nel progetto.  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione alle applicazioni di servizio Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Procedura: installare e disinstallare servizi](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [Procedura: avviare servizi](../../../docs/framework/windows-services/how-to-start-services.md)  
 [Procedura: specificare il contesto di sicurezza per i servizi](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)
