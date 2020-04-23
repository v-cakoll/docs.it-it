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
# <a name="how-to-specify-the-security-context-for-services"></a><span data-ttu-id="39e22-102">Procedura: specificare il contesto di sicurezza per i servizi</span><span class="sxs-lookup"><span data-stu-id="39e22-102">How to: Specify the Security Context for Services</span></span>
<span data-ttu-id="39e22-103">Per impostazione predefinita, i servizi vengono eseguiti in un contesto di sicurezza diverso rispetto a quello dell'utente connesso.</span><span class="sxs-lookup"><span data-stu-id="39e22-103">By default, services run in a different security context than that of the logged-in user.</span></span> <span data-ttu-id="39e22-104">I servizi vengono eseguiti nel contesto dell'account di sistema predefinito, chiamato `LocalSystem`, che concede privilegi di accesso diversi per le risorse di sistema rispetto all'account utente.</span><span class="sxs-lookup"><span data-stu-id="39e22-104">Services run in the context of the default system account, called `LocalSystem`, which gives them different access privileges to system resources than the user.</span></span> <span data-ttu-id="39e22-105">È possibile modificare questo comportamento per specificare un account utente diverso nell'ambito del quale eseguire il servizio.</span><span class="sxs-lookup"><span data-stu-id="39e22-105">You can change this behavior to specify a different user account under which your service should run.</span></span>  
  
 <span data-ttu-id="39e22-106">Per impostare il contesto di sicurezza, è necessario modificare la proprietà <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> per il processo in cui viene eseguito il servizio.</span><span class="sxs-lookup"><span data-stu-id="39e22-106">You set the security context by manipulating the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property for the process within which the service runs.</span></span> <span data-ttu-id="39e22-107">Questa proprietà consente di impostare il servizio su uno di quattro tipi di account:</span><span class="sxs-lookup"><span data-stu-id="39e22-107">This property allows you to set the service to one of four account types:</span></span>  
  
- <span data-ttu-id="39e22-108">`User`, con il quale il sistema richiede un nome utente e una password valido quando il servizio viene installato ed eseguito nel contesto di un account specificato da un singolo utente nella rete;</span><span class="sxs-lookup"><span data-stu-id="39e22-108">`User`, which causes the system to prompt for a valid user name and password when the service is installed and runs in the context of an account specified by a single user on the network;</span></span>  
  
- <span data-ttu-id="39e22-109">`LocalService`, con il quale il servizio viene eseguito nel contesto di un account che opera come utente senza privilegi nel computer locale e presenta credenziali anonime a eventuali server remoti;</span><span class="sxs-lookup"><span data-stu-id="39e22-109">`LocalService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents anonymous credentials to any remote server;</span></span>  
  
- <span data-ttu-id="39e22-110">`LocalSystem`, con il quale il servizio viene eseguito nel contesto di un account con privilegi estesi locali e presenta le credenziali del computer a eventuali server remoti;</span><span class="sxs-lookup"><span data-stu-id="39e22-110">`LocalSystem`, which runs in the context of an account that provides extensive local privileges, and presents the computer's credentials to any remote server;</span></span>  
  
- <span data-ttu-id="39e22-111">`NetworkService`, con il quale il servizio viene eseguito nel contesto di un account che opera come utente senza privilegi nel computer locale e presenta credenziali del computer a eventuali server remoti.</span><span class="sxs-lookup"><span data-stu-id="39e22-111">`NetworkService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents the computer's credentials to any remote server.</span></span>  
  
 <span data-ttu-id="39e22-112">Per altre informazioni, vedere l'enumerazione <xref:System.ServiceProcess.ServiceAccount>.</span><span class="sxs-lookup"><span data-stu-id="39e22-112">For more information, see the <xref:System.ServiceProcess.ServiceAccount> enumeration.</span></span>  
  
### <a name="to-specify-the-security-context-for-a-service"></a><span data-ttu-id="39e22-113">Per specificare il contesto di sicurezza per un servizio</span><span class="sxs-lookup"><span data-stu-id="39e22-113">To specify the security context for a service</span></span>  
  
1. <span data-ttu-id="39e22-114">Dopo aver creato il servizio, aggiungere i programmi di installazione necessari.</span><span class="sxs-lookup"><span data-stu-id="39e22-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="39e22-115">Per altre informazioni, vedere [Procedura: Aggiungere programmi di installazione all'applicazione di servizio](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="39e22-115">For more information, see [How to: Add Installers to Your Service Application](how-to-add-installers-to-your-service-application.md).</span></span>  
  
2. <span data-ttu-id="39e22-116">Nella finestra di progettazione accedere alla classe `ProjectInstaller` e fare clic sul programma di installazione del processo del servizio per il servizio in questione.</span><span class="sxs-lookup"><span data-stu-id="39e22-116">In the designer, access the `ProjectInstaller` class and click the service process installer for the service you are working with.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="39e22-117">Per ogni applicazione di servizio, esistono almeno due componenti di installazione nella classe `ProjectInstaller`, uno per installare i processi per tutti i servizi nel progetto e un programma di installazione per ogni servizio contenuto nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="39e22-117">For every service application, there are at least two installation components in the `ProjectInstaller` class — one that installs the processes for all services in the project, and one installer for each service the application contains.</span></span> <span data-ttu-id="39e22-118">In questo caso, si vuole selezionare <xref:System.ServiceProcess.ServiceProcessInstaller>.</span><span class="sxs-lookup"><span data-stu-id="39e22-118">In this instance, you want to select <xref:System.ServiceProcess.ServiceProcessInstaller>.</span></span>  
  
3. <span data-ttu-id="39e22-119">Nella finestra **Proprietà** impostare <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> sul valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="39e22-119">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> to the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39e22-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39e22-120">See also</span></span>

- [<span data-ttu-id="39e22-121">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="39e22-121">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="39e22-122">Procedura: aggiungere programmi di installazione all'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="39e22-122">How to: Add Installers to Your Service Application</span></span>](how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="39e22-123">Procedura: creare servizi Windows</span><span class="sxs-lookup"><span data-stu-id="39e22-123">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)
