---
title: Sviluppo di applicazioni di servizio Windows
ms.date: 03/30/2017
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
author: ghogen
manager: douge
ms.openlocfilehash: 2c7fb148b96d5ff9804bcb0bb7c842c475c0f117
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385981"
---
# <a name="developing-windows-service-applications"></a><span data-ttu-id="b96b4-102">Sviluppo di applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="b96b4-102">Developing Windows Service Applications</span></span>
<span data-ttu-id="b96b4-103">Usando Microsoft Visual Studio o Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, è possibile creare facilmente servizi mediante la creazione di un'applicazione installata come servizio.</span><span class="sxs-lookup"><span data-stu-id="b96b4-103">Using Microsoft Visual Studio or the Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, you can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="b96b4-104">Questo tipo di applicazione viene chiamata servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="b96b4-104">This type of application is called a Windows service.</span></span> <span data-ttu-id="b96b4-105">Con le funzionalità del framework, è possibile creare servizi, installarli, avviarli, arrestarli e controllarne in altri modi il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="b96b4-105">With framework features, you can create services, install them, and start, stop, and otherwise control their behavior.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="b96b4-106">Il modello di servizio Windows per C++ non era incluso in Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="b96b4-106">The Windows service template for C++ was not included in Visual Studio 2010.</span></span> <span data-ttu-id="b96b4-107">Per creare un servizio Windows, è possibile creare un servizio in codice gestito in Visual C# o Visual Basic, che può interagire con il codice C++ esistente se necessario, oppure è possibile creare un servizio Windows in C++ nativo tramite la [Creazione guidata progetto ATL](/cpp/atl/reference/atl-project-wizard).</span><span class="sxs-lookup"><span data-stu-id="b96b4-107">To create a Windows service, you can either create a service in managed code in Visual C# or Visual Basic, which could interoperate with existing C++ code if required, or you can create a Windows service in native C++ by using the [ATL Project Wizard](/cpp/atl/reference/atl-project-wizard).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b96b4-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="b96b4-108">In This Section</span></span>  
 [<span data-ttu-id="b96b4-109">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="b96b4-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 <span data-ttu-id="b96b4-110">Offre una panoramica sulle applicazioni servizio Windows, sulla durata di un servizio e sulle differenze tra le applicazioni servizio e altri tipi di progetto comuni.</span><span class="sxs-lookup"><span data-stu-id="b96b4-110">Provides an overview of Windows service applications, the lifetime of a service, and how service applications differ from other common project types.</span></span>  
  
 [<span data-ttu-id="b96b4-111">Procedura dettagliata: creazione di un'applicazione di servizio Windows in Progettazione componenti</span><span class="sxs-lookup"><span data-stu-id="b96b4-111">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 <span data-ttu-id="b96b4-112">Offre un esempio di creazione di un servizio in Visual Basic e Visual C#.</span><span class="sxs-lookup"><span data-stu-id="b96b4-112">Provides an example of creating a service in Visual Basic and Visual C#.</span></span>  
  
 [<span data-ttu-id="b96b4-113">Architettura di programmazione delle applicazioni di servizio</span><span class="sxs-lookup"><span data-stu-id="b96b4-113">Service Application Programming Architecture</span></span>](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 <span data-ttu-id="b96b4-114">Illustra gli elementi del linguaggio utilizzati usati programmazione dei servizi.</span><span class="sxs-lookup"><span data-stu-id="b96b4-114">Explains the language elements used in service programming.</span></span>  
  
 [<span data-ttu-id="b96b4-115">Procedura: creare servizi Windows</span><span class="sxs-lookup"><span data-stu-id="b96b4-115">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 <span data-ttu-id="b96b4-116">Descrive il processo di creazione e configurazione dei servizi Windows usando il modello di progetto per servizi Windows.</span><span class="sxs-lookup"><span data-stu-id="b96b4-116">Describes the process of creating and configuring Windows services using the Windows service project template.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b96b4-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="b96b4-117">Related Sections</span></span>  
 <xref:System.ServiceProcess.ServiceBase>  
 <span data-ttu-id="b96b4-118">Descrive le funzionalità principali della classe <xref:System.ServiceProcess.ServiceBase> usata per creare servizi.</span><span class="sxs-lookup"><span data-stu-id="b96b4-118">Describes the major features of the <xref:System.ServiceProcess.ServiceBase> class, which is used to create services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 <span data-ttu-id="b96b4-119">Descrive le funzionalità della classe <xref:System.ServiceProcess.ServiceProcessInstaller> usata insieme alla classe <xref:System.ServiceProcess.ServiceInstaller> per installare e disinstallare servizi.</span><span class="sxs-lookup"><span data-stu-id="b96b4-119">Describes the features of the <xref:System.ServiceProcess.ServiceProcessInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceInstaller> class to install and uninstall your services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 <span data-ttu-id="b96b4-120">Descrive le funzionalità della classe <xref:System.ServiceProcess.ServiceInstaller> usata insieme alla classe <xref:System.ServiceProcess.ServiceProcessInstaller> per installare e disinstallare un servizio.</span><span class="sxs-lookup"><span data-stu-id="b96b4-120">Describes the features of the <xref:System.ServiceProcess.ServiceInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceProcessInstaller> class to install and uninstall your service.</span></span>  
  
 [<span data-ttu-id="b96b4-121">NIB Creazione di progetti da modelli</span><span class="sxs-lookup"><span data-stu-id="b96b4-121">NIB Creating Projects from Templates</span></span>](https://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 <span data-ttu-id="b96b4-122">Descrive i tipi di progetto usati in questo capitolo e come scegliere tra i vari tipi.</span><span class="sxs-lookup"><span data-stu-id="b96b4-122">Describes the projects types used in this chapter and how to choose between them.</span></span>
