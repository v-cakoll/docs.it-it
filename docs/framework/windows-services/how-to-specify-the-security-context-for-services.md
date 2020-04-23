---
title: 'Procedura: specificare il contesto di sicurezza per i servizi'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
author: ghogen
ms.openlocfilehash: dd2a9c4485e151d4cb1c9d5ae3a95a69fcc416d4
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053589"
---
# <a name="how-to-specify-the-security-context-for-services"></a>Procedura: specificare il contesto di sicurezza per i servizi
Per impostazione predefinita, i servizi vengono eseguiti in un contesto di sicurezza diverso rispetto a quello dell'utente connesso. I servizi vengono eseguiti nel contesto dell'account di sistema predefinito, chiamato `LocalSystem`, che concede privilegi di accesso diversi per le risorse di sistema rispetto all'account utente. È possibile modificare questo comportamento per specificare un account utente diverso nell'ambito del quale eseguire il servizio.  
  
 Per impostare il contesto di sicurezza, è necessario modificare la proprietà <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> per il processo in cui viene eseguito il servizio. Questa proprietà consente di impostare il servizio su uno di quattro tipi di account:  
  
- `User`, con il quale il sistema richiede un nome utente e una password valido quando il servizio viene installato ed eseguito nel contesto di un account specificato da un singolo utente nella rete;  
  
- `LocalService`, con il quale il servizio viene eseguito nel contesto di un account che opera come utente senza privilegi nel computer locale e presenta credenziali anonime a eventuali server remoti;  
  
- `LocalSystem`, con il quale il servizio viene eseguito nel contesto di un account con privilegi estesi locali e presenta le credenziali del computer a eventuali server remoti;  
  
- `NetworkService`, con il quale il servizio viene eseguito nel contesto di un account che opera come utente senza privilegi nel computer locale e presenta credenziali del computer a eventuali server remoti.  
  
 Per altre informazioni, vedere l'enumerazione <xref:System.ServiceProcess.ServiceAccount>.  
  
### <a name="to-specify-the-security-context-for-a-service"></a>Per specificare il contesto di sicurezza per un servizio  
  
1. Dopo aver creato il servizio, aggiungere i programmi di installazione necessari. Per altre informazioni, vedere [Procedura: Aggiungere programmi di installazione all'applicazione di servizio](how-to-add-installers-to-your-service-application.md).  
  
2. Nella finestra di progettazione accedere alla classe `ProjectInstaller` e fare clic sul programma di installazione del processo del servizio per il servizio in questione.  
  
    > [!NOTE]
    > Per ogni applicazione di servizio, esistono almeno due componenti di installazione nella classe `ProjectInstaller`, uno per installare i processi per tutti i servizi nel progetto e un programma di installazione per ogni servizio contenuto nell'applicazione. In questo caso, si vuole selezionare <xref:System.ServiceProcess.ServiceProcessInstaller>.  
  
3. Nella finestra **Proprietà** impostare <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> sul valore appropriato.  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione alle applicazioni di servizio Windows](introduction-to-windows-service-applications.md)
- [Procedura: aggiungere programmi di installazione all'applicazione di servizio](how-to-add-installers-to-your-service-application.md)
- [Procedura: creare servizi Windows](how-to-create-windows-services.md)
