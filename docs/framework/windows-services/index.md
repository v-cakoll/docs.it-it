---
title: Sviluppo di applicazioni di servizio Windows
description: Vedere collegamenti ad articoli in cui viene illustrato come sviluppare app di servizio Windows tramite Visual Studio o .NET SDK.
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
ms.openlocfilehash: ed02d523c21c51df2ed886843fdb71c075c93c30
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925696"
---
# <a name="develop-windows-service-apps"></a><span data-ttu-id="54885-103">Sviluppare app di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="54885-103">Develop Windows service apps</span></span>

<span data-ttu-id="54885-104">Usando Visual Studio o .NET Framework SDK, è possibile creare facilmente servizi mediante la creazione di un'applicazione installata come servizio.</span><span class="sxs-lookup"><span data-stu-id="54885-104">Using Visual Studio or the .NET Framework SDK, you can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="54885-105">Questo tipo di applicazione viene chiamata servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="54885-105">This type of application is called a Windows service.</span></span> <span data-ttu-id="54885-106">Con le funzionalità del framework, è possibile creare servizi, installarli, avviarli, arrestarli e controllarne in altri modi il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="54885-106">With framework features, you can create services, install them, and start, stop, and otherwise control their behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="54885-107">In Visual Studio è possibile creare un servizio in codice gestito in Visual C# o Visual Basic, che può interagire con il codice C++ esistente, se necessario.</span><span class="sxs-lookup"><span data-stu-id="54885-107">In Visual Studio you can create a service in managed code in Visual C# or Visual Basic, which can interoperate with existing C++ code if required.</span></span> <span data-ttu-id="54885-108">In alternativa, è possibile creare un servizio Windows in C++ nativo tramite la [Creazione guidata progetto ATL](/cpp/atl/reference/atl-project-wizard).</span><span class="sxs-lookup"><span data-stu-id="54885-108">Or, you can create a Windows service in native C++ by using the [ATL Project Wizard](/cpp/atl/reference/atl-project-wizard).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="54885-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="54885-109">In this section</span></span>

[<span data-ttu-id="54885-110">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="54885-110">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)

<span data-ttu-id="54885-111">Offre una panoramica sulle applicazioni servizio Windows, sulla durata di un servizio e sulle differenze tra le applicazioni servizio e altri tipi di progetto comuni.</span><span class="sxs-lookup"><span data-stu-id="54885-111">Provides an overview of Windows service applications, the lifetime of a service, and how service applications differ from other common project types.</span></span>

[<span data-ttu-id="54885-112">Procedura dettagliata: creazione di un'applicazione di servizio Windows in Progettazione componenti</span><span class="sxs-lookup"><span data-stu-id="54885-112">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)

<span data-ttu-id="54885-113">Offre un esempio di creazione di un servizio in Visual Basic e Visual C#.</span><span class="sxs-lookup"><span data-stu-id="54885-113">Provides an example of creating a service in Visual Basic and Visual C#.</span></span>

[<span data-ttu-id="54885-114">Architettura di programmazione delle applicazioni di servizio</span><span class="sxs-lookup"><span data-stu-id="54885-114">Service Application Programming Architecture</span></span>](service-application-programming-architecture.md)

<span data-ttu-id="54885-115">Illustra gli elementi del linguaggio utilizzati usati programmazione dei servizi.</span><span class="sxs-lookup"><span data-stu-id="54885-115">Explains the language elements used in service programming.</span></span>

[<span data-ttu-id="54885-116">Procedura: Creare servizi Windows</span><span class="sxs-lookup"><span data-stu-id="54885-116">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)

<span data-ttu-id="54885-117">Descrive il processo di creazione e configurazione dei servizi Windows usando il modello di progetto per servizi Windows.</span><span class="sxs-lookup"><span data-stu-id="54885-117">Describes the process of creating and configuring Windows services using the Windows service project template.</span></span>

## <a name="related-sections"></a><span data-ttu-id="54885-118">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="54885-118">Related sections</span></span>

<span data-ttu-id="54885-119"><xref:System.ServiceProcess.ServiceBase> - Descrive le funzionalità principali della classe <xref:System.ServiceProcess.ServiceBase>, usata per creare i servizi.</span><span class="sxs-lookup"><span data-stu-id="54885-119"><xref:System.ServiceProcess.ServiceBase> - Describes the major features of the <xref:System.ServiceProcess.ServiceBase> class, which is used to create services.</span></span>

<span data-ttu-id="54885-120"><xref:System.ServiceProcess.ServiceProcessInstaller> - Descrive le funzionalità della classe <xref:System.ServiceProcess.ServiceProcessInstaller>, usata insieme alla classe <xref:System.ServiceProcess.ServiceInstaller> per installare e disinstallare i servizi.</span><span class="sxs-lookup"><span data-stu-id="54885-120"><xref:System.ServiceProcess.ServiceProcessInstaller> - Describes the features of the <xref:System.ServiceProcess.ServiceProcessInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceInstaller> class to install and uninstall your services.</span></span>

<span data-ttu-id="54885-121"><xref:System.ServiceProcess.ServiceInstaller> - Descrive le funzionalità della classe <xref:System.ServiceProcess.ServiceInstaller>, usata insieme alla classe <xref:System.ServiceProcess.ServiceProcessInstaller> per installare e disinstallare un servizio.</span><span class="sxs-lookup"><span data-stu-id="54885-121"><xref:System.ServiceProcess.ServiceInstaller> - Describes the features of the <xref:System.ServiceProcess.ServiceInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceProcessInstaller> class to install and uninstall your service.</span></span>

<span data-ttu-id="54885-122">[Creare progetti da modelli](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0fyc0azh(v=vs.120)) -  Descrive i tipi di progetto usati in questo capitolo e come scegliere tra i vari tipi.</span><span class="sxs-lookup"><span data-stu-id="54885-122">[Create Projects from Templates](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0fyc0azh(v=vs.120)) -  Describes the projects types used in this chapter and how to choose between them.</span></span>
