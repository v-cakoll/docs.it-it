---
title: 'Procedura: avviare servizi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: e4f93da8a2a5be00d798d64caba0f54bfd71ceb2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-start-services"></a>Procedura: avviare servizi
Dopo l'installazione di un servizio, è necessario avviarlo. Avvio delle chiamate di <xref:System.ServiceProcess.ServiceBase.OnStart%2A> metodo nella classe del servizio. In genere, il <xref:System.ServiceProcess.ServiceBase.OnStart%2A> metodo definisce le operazioni che il servizio eseguirà. Dopo l'avvio di un servizio rimane attivo fino a quando non è sospeso o interrotto manualmente.  
  
 Servizi possono essere impostati per avviare automaticamente o manualmente. Verrà avviato un servizio che viene avviato automaticamente quando il computer in cui è installato è stato riavviato oppure prima attivato. Un utente deve avviare un servizio che viene avviato manualmente.  
  
> [!NOTE]
>  Per impostazione predefinita, i servizi creati con [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] sono impostate per l'avvio manuale.  
  
 Esistono diversi modi, è possibile avviare manualmente un servizio, ovvero da **Esplora Server**, dal **Gestione controllo servizi**, o dal codice utilizzando un componente denominato il <xref:System.ServiceProcess.ServiceController>.  
  
 Impostare il <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> proprietà la <xref:System.ServiceProcess.ServiceInstaller> classe per determinare se un servizio deve essere avviato manualmente o automaticamente.  
  
### <a name="to-specify-how-a-service-should-start"></a>Per specificare la modalità in cui deve iniziare un servizio  
  
1.  Dopo aver creato il servizio, aggiungere i programmi di installazione necessari per tale. Per ulteriori informazioni, vedere [procedura: aggiungere programmi di installazione per l'applicazione di servizio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
2.  Nella finestra di progettazione, fare clic sul programma di installazione per il servizio in uso.  
  
3.  Nel **proprietà** finestra, impostare il <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> proprietà su uno dei seguenti:  
  
    |Per avviare il servizio|Impostare questo valore|  
    |----------------------------------|--------------------|  
    |Quando si riavvia il computer|**Automatico**|  
    |Avvio del servizio da parte di un'azione esplicita dell'utente|**Manuale**|  
  
    > [!TIP]
    >  Per impedire che il servizio venga avviato, è possibile impostare il <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> proprietà **disabilitato**. Se si desidera riavviare un server più volte e si desidera risparmiare tempo evitando i servizi che normalmente inizia avvio, è possibile farlo.  
  
    > [!NOTE]
    >  Queste e altre proprietà può essere modificato dopo l'installazione del servizio.  
  
     Esistono diversi modi, è possibile avviare un servizio che ha relativo <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> processo impostata su **manuale** : da **Esplora Server**, dal **Gestione controllo servizi di Windows**, o dal codice. È importante notare che non tutti questi metodi viene avviato effettivamente il servizio nel contesto del **Gestione controllo servizi**; **Esplora server** e metodi a livello di codice di avvio del servizio modificano effettivamente il controller.  
  
### <a name="to-manually-start-a-service-from-server-explorer"></a>Per avviare manualmente un servizio da Esplora Server  
  
1.  In **Esplora Server**, aggiungere il server desiderato, se non è già elencato. Per ulteriori informazioni, vedere Procedura: accedere e inizializzare Esplora Server-Esplora Database.  
  
2.  Espandere il **servizi** nodo, quindi individuare il servizio che si desidera avviare.  
  
3.  Il nome del servizio di mouse e scegliere **avviare**.  
  
### <a name="to-manually-start-a-service-from-services-control-manager"></a>Per avviare manualmente un servizio da Gestione controllo servizi  
  
1.  Aprire il **Gestione controllo servizi** effettuando una delle operazioni seguenti:  
  
    -   In Windows XP e 2000 Professional, fare doppio clic su **risorse del Computer** sul desktop e quindi fare clic su **Gestisci**. Nella finestra di dialogo che viene visualizzato, espandere il **servizi e applicazioni** nodo.  
  
         \- oppure -  
  
    -   In Windows Server 2003 e Windows 2000 Server, fare clic su **avviare**, scegliere **programmi**, fare clic su **strumenti di amministrazione**, quindi fare clic su **servizi**.  
  
        > [!NOTE]
        >  In Windows NT versione 4.0, è possibile aprire questa finestra di dialogo **Pannello di controllo**.  
  
     Viene visualizzato il servizio nel **servizi** sezione della finestra.  
  
2.  Selezionare il servizio nell'elenco, pulsante destro del mouse e quindi fare clic su **avviare**.  
  
### <a name="to-manually-start-a-service-from-code"></a>Per avviare manualmente un servizio da codice  
  
1.  Creare un'istanza di <xref:System.ServiceProcess.ServiceController> classe e configurarlo per interagire con il servizio che si desidera amministrare.  
  
2.  Chiamare il metodo <xref:System.ServiceProcess.ServiceController.Start%2A> per avviare il servizio.  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione alle applicazioni di servizio Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Procedura: creare servizi Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [Procedura: aggiungere programmi di installazione all'applicazione di servizio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
