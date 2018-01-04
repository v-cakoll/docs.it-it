---
title: 'Procedura: specificare il contesto di sicurezza per i servizi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 9ce65358f6d63414dbe6798d3cc2464ee2741980
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-security-context-for-services"></a>Procedura: specificare il contesto di sicurezza per i servizi
Per impostazione predefinita, i servizi eseguiti in un contesto di sicurezza diverso rispetto a quello dell'utente connesso. Vengono eseguiti nel contesto dell'account di sistema predefinito, i servizi chiamato `LocalSystem`, che concede privilegi di accesso diversi a risorse di sistema rispetto all'utente. È possibile modificare questo comportamento per specificare un account utente diverso in cui eseguire il servizio.  
  
 Impostare il contesto di sicurezza modificando la <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> proprietà per il processo in cui viene eseguito il servizio. Questa proprietà consente di impostare il servizio in uno dei quattro tipi di account:  
  
-   `User`, che comporta il sistema per la richiesta di un nome utente valido e una password quando il servizio viene installato ed eseguito nel contesto di un account specificato da un singolo utente della rete.  
  
-   `LocalService`, che viene eseguita nel contesto di un account che opera come utente senza privilegi nel computer locale e presenta credenziali anonime a tutti i server remoti.  
  
-   `LocalSystem`, che viene eseguita nel contesto di un account che fornisce privilegi locali estesi e presenta le credenziali del computer per tutti i server remoti.  
  
-   `NetworkService`, che viene eseguita nel contesto di un account che opera come utente senza privilegi nel computer locale e presenta le credenziali del computer per tutti i server remoti.  
  
 Per altre informazioni, vedere l'enumerazione <xref:System.ServiceProcess.ServiceAccount>.  
  
### <a name="to-specify-the-security-context-for-a-service"></a>Per specificare il contesto di sicurezza per un servizio  
  
1.  Dopo aver creato il servizio, aggiungere i programmi di installazione necessari per tale. Per ulteriori informazioni, vedere [procedura: aggiungere programmi di installazione per l'applicazione di servizio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
2.  Nella finestra di progettazione, accedere la `ProjectInstaller` classe e fare clic su installazione del processo del servizio per il servizio in uso.  
  
    > [!NOTE]
    >  Per ogni applicazione di servizio, sono disponibili almeno due componenti di installazione di `ProjectInstaller` classe, uno per installare i processi per tutti i servizi nel progetto e un programma di installazione per ogni servizio contiene l'applicazione. In questo caso, si desidera selezionare <xref:System.ServiceProcess.ServiceProcessInstaller>.  
  
3.  Nel **proprietà** finestra, impostare il <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> sul valore appropriato.  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione alle applicazioni di servizio Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Procedura: aggiungere programmi di installazione all'applicazione di servizio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [Procedura: creare servizi Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)
