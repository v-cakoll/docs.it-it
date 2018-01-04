---
title: Sviluppo di applicazioni di servizio Windows
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
caps.latest.revision: "18"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 17d4c5908929f02077b1eb48932a50e83f48d076
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="developing-windows-service-applications"></a><span data-ttu-id="07e8d-102">Sviluppo di applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="07e8d-102">Developing Windows Service Applications</span></span>
<span data-ttu-id="07e8d-103">Utilizzando Microsoft [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] oppure Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, è possibile creare facilmente servizi creando un'applicazione che viene installata come un servizio.</span><span class="sxs-lookup"><span data-stu-id="07e8d-103">Using Microsoft [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or the Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, you can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="07e8d-104">Questo tipo di applicazione viene chiamato un servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="07e8d-104">This type of application is called a Windows service.</span></span> <span data-ttu-id="07e8d-105">Con le funzionalità di framework, è possibile creare servizi, installati, avviare, arrestare e controllarne il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="07e8d-105">With framework features, you can create services, install them, and start, stop, and otherwise control their behavior.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="07e8d-106">Il modello di servizio Windows per C++ non è stato incluso in Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="07e8d-106">The Windows service template for C++ was not included in Visual Studio 2010.</span></span> <span data-ttu-id="07e8d-107">Per creare un servizio Windows, è possibile creare un servizio nel codice gestito in Visual c# o Visual Basic, che può interagire con il codice C++ esistente se necessario, oppure è possibile creare un servizio Windows in C++ nativo tramite il [CreazioneguidataprogettoATL](/cpp/atl/reference/atl-project-wizard).</span><span class="sxs-lookup"><span data-stu-id="07e8d-107">To create a Windows service, you can either create a service in managed code in Visual C# or Visual Basic, which could interoperate with existing C++ code if required, or you can create a Windows service in native C++ by using the [ATL Project Wizard](/cpp/atl/reference/atl-project-wizard).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="07e8d-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="07e8d-108">In This Section</span></span>  
 [<span data-ttu-id="07e8d-109">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="07e8d-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 <span data-ttu-id="07e8d-110">Fornisce una panoramica delle applicazioni di servizio Windows, la durata di un servizio, le applicazioni di servizio e le differenze e da altri tipi di progetto comuni.</span><span class="sxs-lookup"><span data-stu-id="07e8d-110">Provides an overview of Windows service applications, the lifetime of a service, and how service applications differ from other common project types.</span></span>  
  
 [<span data-ttu-id="07e8d-111">Procedura dettagliata: creazione di un'applicazione di servizio Windows in Progettazione componenti</span><span class="sxs-lookup"><span data-stu-id="07e8d-111">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 <span data-ttu-id="07e8d-112">Fornisce un esempio di creazione di un servizio in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] e Visual c#.</span><span class="sxs-lookup"><span data-stu-id="07e8d-112">Provides an example of creating a service in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] and Visual C#.</span></span>  
  
 [<span data-ttu-id="07e8d-113">Architettura di programmazione delle applicazioni di servizio</span><span class="sxs-lookup"><span data-stu-id="07e8d-113">Service Application Programming Architecture</span></span>](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 <span data-ttu-id="07e8d-114">Vengono illustrati gli elementi del linguaggio utilizzati nella programmazione dei servizi.</span><span class="sxs-lookup"><span data-stu-id="07e8d-114">Explains the language elements used in service programming.</span></span>  
  
 [<span data-ttu-id="07e8d-115">Procedura: creare servizi Windows</span><span class="sxs-lookup"><span data-stu-id="07e8d-115">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 <span data-ttu-id="07e8d-116">Descrive il processo di creazione e configurazione dei servizi Windows utilizzando il modello di progetto di servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="07e8d-116">Describes the process of creating and configuring Windows services using the Windows service project template.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="07e8d-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="07e8d-117">Related Sections</span></span>  
 <xref:System.ServiceProcess.ServiceBase>  
 <span data-ttu-id="07e8d-118">Vengono descritte le funzionalità principali del <xref:System.ServiceProcess.ServiceBase> (classe), che viene utilizzato per creare servizi.</span><span class="sxs-lookup"><span data-stu-id="07e8d-118">Describes the major features of the <xref:System.ServiceProcess.ServiceBase> class, which is used to create services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 <span data-ttu-id="07e8d-119">Vengono descritte le funzionalità del <xref:System.ServiceProcess.ServiceProcessInstaller> (classe), che viene utilizzato insieme alla <xref:System.ServiceProcess.ServiceInstaller> classe per installare e disinstallare servizi.</span><span class="sxs-lookup"><span data-stu-id="07e8d-119">Describes the features of the <xref:System.ServiceProcess.ServiceProcessInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceInstaller> class to install and uninstall your services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 <span data-ttu-id="07e8d-120">Vengono descritte le funzionalità del <xref:System.ServiceProcess.ServiceInstaller> (classe), che viene utilizzato insieme alla <xref:System.ServiceProcess.ServiceProcessInstaller> classe per installare e disinstallare il servizio.</span><span class="sxs-lookup"><span data-stu-id="07e8d-120">Describes the features of the <xref:System.ServiceProcess.ServiceInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceProcessInstaller> class to install and uninstall your service.</span></span>  
  
 [<span data-ttu-id="07e8d-121">Creazione di progetti da modelli</span><span class="sxs-lookup"><span data-stu-id="07e8d-121">NIB Creating Projects from Templates</span></span>](http://msdn.microsoft.com/en-us/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 <span data-ttu-id="07e8d-122">Vengono descritti i progetti tipi utilizzati in questo capitolo e sulla scelta tra di essi.</span><span class="sxs-lookup"><span data-stu-id="07e8d-122">Describes the projects types used in this chapter and how to choose between them.</span></span>
