---
title: Sviluppo di applicazioni client basate su Windows con .NET Framework
ms.date: 01/09/2018
helpviewer_keywords:
- client application services
- applications [Windows Forms]
- Windows Presentation Foundation, in Visual Studio
- WPF, in Visual Studio
- Windows applications
- rich client applications
- .NET applications, Windows applications
- Visual Basic code, creating applications
- Visual C#, creating applications
- client/server applications, Windows applications
ms.assetid: 2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68
ms.openlocfilehash: 987f8e25014e8ce6413c998f6eb78d821558ecec
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43400363"
---
# <a name="developing-client-applications-with-the-net-framework"></a><span data-ttu-id="04e59-102">Sviluppo di applicazioni client con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="04e59-102">Developing client applications with the .NET Framework</span></span>

<span data-ttu-id="04e59-103">Esistono diversi modi per sviluppare applicazioni basate su Windows con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="04e59-103">There are several ways to develop Windows-based applications with the .NET Framework.</span></span> <span data-ttu-id="04e59-104">È possibile usare uno di questi strumenti e framework:</span><span class="sxs-lookup"><span data-stu-id="04e59-104">You can use any of these tools and frameworks:</span></span> 

* [<span data-ttu-id="04e59-105">Piattaforma UWP (Universal Windows Platform)</span><span class="sxs-lookup"><span data-stu-id="04e59-105">Universal Windows Platform (UWP)</span></span>](https://developer.microsoft.com/windows/apps)
* [<span data-ttu-id="04e59-106">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="04e59-106">Windows Presentation Foundation (WPF)</span></span>](../../docs/framework/wpf/index.md)
* [<span data-ttu-id="04e59-107">Windows Form</span><span class="sxs-lookup"><span data-stu-id="04e59-107">Windows Forms</span></span>](../../docs/framework/winforms/index.md)

<span data-ttu-id="04e59-108">Questa sezione include argomenti che descrivono come creare applicazioni basate su Windows con Windows Presentation Foundation o Windows Form.</span><span class="sxs-lookup"><span data-stu-id="04e59-108">This section contains topics that describe how to create Windows-based applications by using Windows Presentation Foundation or by using Windows Forms.</span></span> <span data-ttu-id="04e59-109">Tuttavia, è anche possibile creare applicazioni Web con .NET Framework e applicazioni client per computer o dispositivi da rendere disponibili tramite Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="04e59-109">However, you can also create web applications using the .NET Framework, and client applications for computers or devices that you make available through the Microsoft Store.</span></span>
 
## <a name="in-this-section"></a><span data-ttu-id="04e59-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="04e59-110">In this section</span></span>

[<span data-ttu-id="04e59-111">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="04e59-111">Windows Presentation Foundation</span></span>](../../docs/framework/wpf/index.md)  
<span data-ttu-id="04e59-112">Vengono fornite informazioni sullo sviluppo di applicazioni con WPF.</span><span class="sxs-lookup"><span data-stu-id="04e59-112">Provides information about developing applications by using WPF.</span></span>

[<span data-ttu-id="04e59-113">Windows Form</span><span class="sxs-lookup"><span data-stu-id="04e59-113">Windows Forms</span></span>](../../docs/framework/winforms/index.md)  
<span data-ttu-id="04e59-114">Vengono fornite informazioni sullo sviluppo di applicazioni con Windows Form.</span><span class="sxs-lookup"><span data-stu-id="04e59-114">Provides information about developing applications by using Windows Forms.</span></span>

[<span data-ttu-id="04e59-115">Tecnologie client comuni</span><span class="sxs-lookup"><span data-stu-id="04e59-115">Common Client Technologies</span></span>](../../docs/framework/common-client-technologies/index.md)  
<span data-ttu-id="04e59-116">Vengono fornite informazioni sulle tecnologie aggiuntive utilizzabili durante lo sviluppo di applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="04e59-116">Provides information about additional technologies that can be used when developing client applications.</span></span>

## <a name="related-sections"></a><span data-ttu-id="04e59-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="04e59-117">Related sections</span></span>

[<span data-ttu-id="04e59-118">Piattaforma UWP (Universal Windows Platform)</span><span class="sxs-lookup"><span data-stu-id="04e59-118">Universal Windows Platform</span></span>](https://developer.microsoft.com/windows/apps)  
<span data-ttu-id="04e59-119">Viene descritto come creare applicazioni per Windows 10 che è possibile mettere a disposizione degli utenti tramite Windows Store.</span><span class="sxs-lookup"><span data-stu-id="04e59-119">Describes how to create applications for Windows 10 that you can make available to users through the Windows Store.</span></span>

[<span data-ttu-id="04e59-120">.NET per app UWP</span><span class="sxs-lookup"><span data-stu-id="04e59-120">.NET for UWP apps</span></span>](https://msdn.microsoft.com/library/windows/apps/mt185501.aspx)  
<span data-ttu-id="04e59-121">Viene descritto il supporto di .NET Framework per le app di Windows Store, che è possibile distribuire in computer e dispositivi Windows.</span><span class="sxs-lookup"><span data-stu-id="04e59-121">Describes the .NET Framework support for Store apps, which can be deployed to Windows computers and devices.</span></span>

<span data-ttu-id="04e59-122">[.NET API per Windows Phone Silverlight](https://docs.microsoft.com/previous-versions/windows/apps/jj207211\(v=vs.105\))</span><span class="sxs-lookup"><span data-stu-id="04e59-122">[.NET API for Windows Phone Silverlight](https://docs.microsoft.com/previous-versions/windows/apps/jj207211\(v=vs.105\))</span></span>  
<span data-ttu-id="04e59-123">Vengono elencate le API di .NET Framework che è possibile usare per creare app con Silverlight per Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="04e59-123">Lists the .NET Framework APIs you can use for building apps with Windows Phone Silverlight.</span></span>
  
[<span data-ttu-id="04e59-124">Sviluppo per piattaforme multiple</span><span class="sxs-lookup"><span data-stu-id="04e59-124">Developing for Multiple Platforms</span></span>](../../docs/standard/cross-platform/index.md)  
<span data-ttu-id="04e59-125">Vengono descritti i diversi modi disponibili per usare .NET Framework con i diversi tipi di app client.</span><span class="sxs-lookup"><span data-stu-id="04e59-125">Describes the different methods you can use the .NET Framework to target multiple client app types.</span></span>

[<span data-ttu-id="04e59-126">Introduzione a siti Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="04e59-126">Get Started with ASP.NET Web Sites</span></span>](http://www.asp.net/get-started/websites)  
<span data-ttu-id="04e59-127">Vengono descritti i diversi modi in cui sviluppare app Web con ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="04e59-127">Describes the ways you can develop web apps using ASP.NET.</span></span>

## <a name="see-also"></a><span data-ttu-id="04e59-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04e59-128">See also</span></span>

[<span data-ttu-id="04e59-129">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="04e59-129">.NET Standard</span></span>](../../docs/standard/net-standard.md)  
[<span data-ttu-id="04e59-130">Panoramica</span><span class="sxs-lookup"><span data-stu-id="04e59-130">Overview</span></span>](../../docs/framework/get-started/overview.md)  
[<span data-ttu-id="04e59-131">Guida di sviluppo</span><span class="sxs-lookup"><span data-stu-id="04e59-131">Development Guide</span></span>](../../docs/framework/development-guide.md)  
[<span data-ttu-id="04e59-132">Applicazioni di servizi Windows</span><span class="sxs-lookup"><span data-stu-id="04e59-132">Windows Service Applications</span></span>](../../docs/framework/windows-services/index.md)  
