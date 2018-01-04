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
# <a name="how-to-specify-the-security-context-for-services"></a><span data-ttu-id="399f0-102">Procedura: specificare il contesto di sicurezza per i servizi</span><span class="sxs-lookup"><span data-stu-id="399f0-102">How to: Specify the Security Context for Services</span></span>
<span data-ttu-id="399f0-103">Per impostazione predefinita, i servizi eseguiti in un contesto di sicurezza diverso rispetto a quello dell'utente connesso.</span><span class="sxs-lookup"><span data-stu-id="399f0-103">By default, services run in a different security context than that of the logged-in user.</span></span> <span data-ttu-id="399f0-104">Vengono eseguiti nel contesto dell'account di sistema predefinito, i servizi chiamato `LocalSystem`, che concede privilegi di accesso diversi a risorse di sistema rispetto all'utente.</span><span class="sxs-lookup"><span data-stu-id="399f0-104">Services run in the context of the default system account, called `LocalSystem`, which gives them different access privileges to system resources than the user.</span></span> <span data-ttu-id="399f0-105">È possibile modificare questo comportamento per specificare un account utente diverso in cui eseguire il servizio.</span><span class="sxs-lookup"><span data-stu-id="399f0-105">You can change this behavior to specify a different user account under which your service should run.</span></span>  
  
 <span data-ttu-id="399f0-106">Impostare il contesto di sicurezza modificando la <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> proprietà per il processo in cui viene eseguito il servizio.</span><span class="sxs-lookup"><span data-stu-id="399f0-106">You set the security context by manipulating the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property for the process within which the service runs.</span></span> <span data-ttu-id="399f0-107">Questa proprietà consente di impostare il servizio in uno dei quattro tipi di account:</span><span class="sxs-lookup"><span data-stu-id="399f0-107">This property allows you to set the service to one of four account types:</span></span>  
  
-   <span data-ttu-id="399f0-108">`User`, che comporta il sistema per la richiesta di un nome utente valido e una password quando il servizio viene installato ed eseguito nel contesto di un account specificato da un singolo utente della rete.</span><span class="sxs-lookup"><span data-stu-id="399f0-108">`User`, which causes the system to prompt for a valid user name and password when the service is installed and runs in the context of an account specified by a single user on the network;</span></span>  
  
-   <span data-ttu-id="399f0-109">`LocalService`, che viene eseguita nel contesto di un account che opera come utente senza privilegi nel computer locale e presenta credenziali anonime a tutti i server remoti.</span><span class="sxs-lookup"><span data-stu-id="399f0-109">`LocalService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents anonymous credentials to any remote server;</span></span>  
  
-   <span data-ttu-id="399f0-110">`LocalSystem`, che viene eseguita nel contesto di un account che fornisce privilegi locali estesi e presenta le credenziali del computer per tutti i server remoti.</span><span class="sxs-lookup"><span data-stu-id="399f0-110">`LocalSystem`, which runs in the context of an account that provides extensive local privileges, and presents the computer's credentials to any remote server;</span></span>  
  
-   <span data-ttu-id="399f0-111">`NetworkService`, che viene eseguita nel contesto di un account che opera come utente senza privilegi nel computer locale e presenta le credenziali del computer per tutti i server remoti.</span><span class="sxs-lookup"><span data-stu-id="399f0-111">`NetworkService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents the computer's credentials to any remote server.</span></span>  
  
 <span data-ttu-id="399f0-112">Per altre informazioni, vedere l'enumerazione <xref:System.ServiceProcess.ServiceAccount>.</span><span class="sxs-lookup"><span data-stu-id="399f0-112">For more information, see the <xref:System.ServiceProcess.ServiceAccount> enumeration.</span></span>  
  
### <a name="to-specify-the-security-context-for-a-service"></a><span data-ttu-id="399f0-113">Per specificare il contesto di sicurezza per un servizio</span><span class="sxs-lookup"><span data-stu-id="399f0-113">To specify the security context for a service</span></span>  
  
1.  <span data-ttu-id="399f0-114">Dopo aver creato il servizio, aggiungere i programmi di installazione necessari per tale.</span><span class="sxs-lookup"><span data-stu-id="399f0-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="399f0-115">Per ulteriori informazioni, vedere [procedura: aggiungere programmi di installazione per l'applicazione di servizio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="399f0-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2.  <span data-ttu-id="399f0-116">Nella finestra di progettazione, accedere la `ProjectInstaller` classe e fare clic su installazione del processo del servizio per il servizio in uso.</span><span class="sxs-lookup"><span data-stu-id="399f0-116">In the designer, access the `ProjectInstaller` class and click the service process installer for the service you are working with.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="399f0-117">Per ogni applicazione di servizio, sono disponibili almeno due componenti di installazione di `ProjectInstaller` classe, uno per installare i processi per tutti i servizi nel progetto e un programma di installazione per ogni servizio contiene l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="399f0-117">For every service application, there are at least two installation components in the `ProjectInstaller` class — one that installs the processes for all services in the project, and one installer for each service the application contains.</span></span> <span data-ttu-id="399f0-118">In questo caso, si desidera selezionare <xref:System.ServiceProcess.ServiceProcessInstaller>.</span><span class="sxs-lookup"><span data-stu-id="399f0-118">In this instance, you want to select <xref:System.ServiceProcess.ServiceProcessInstaller>.</span></span>  
  
3.  <span data-ttu-id="399f0-119">Nel **proprietà** finestra, impostare il <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> sul valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="399f0-119">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> to the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="399f0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="399f0-120">See Also</span></span>  
 [<span data-ttu-id="399f0-121">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="399f0-121">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="399f0-122">Procedura: aggiungere programmi di installazione all'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="399f0-122">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="399f0-123">Procedura: creare servizi Windows</span><span class="sxs-lookup"><span data-stu-id="399f0-123">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)
