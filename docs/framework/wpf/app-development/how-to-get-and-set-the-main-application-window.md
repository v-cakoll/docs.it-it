---
title: 'Procedura: ottenere e impostare la finestra principale dell''applicazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows objects [WPF], setting
- setting windows objects [WPF]
- windows objects [WPF], getting
- getting windows objects [WPF]
ms.assetid: ec902bc4-4a59-46f5-8ec1-963b46789356
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0d6bca158172fd3fc31526287c6d4a9928a8ea0c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-get-and-set-the-main-application-window"></a><span data-ttu-id="3ecdd-102">Procedura: ottenere e impostare la finestra principale dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="3ecdd-102">How to: Get and Set the Main Application Window</span></span>
<span data-ttu-id="3ecdd-103">In questo esempio viene illustrato come ottenere e impostare la finestra principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3ecdd-103">This example shows how to get and set the main application window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ecdd-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="3ecdd-104">Example</span></span>  
 <span data-ttu-id="3ecdd-105">Il primo <xref:System.Windows.Window> che viene creata un'istanza all'interno di un [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] applicazione verrà impostata automaticamente da <xref:System.Windows.Application> come finestra principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3ecdd-105">The first <xref:System.Windows.Window> that is instantiated within a [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] application is automatically set by <xref:System.Windows.Application> as the main application window.</span></span> <span data-ttu-id="3ecdd-106">Il primo <xref:System.Windows.Window> sia stata creata un'istanza sarà probabilmente la finestra viene specificato come l'avvio [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (vedere <xref:System.Windows.Application.StartupUri%2A>).</span><span class="sxs-lookup"><span data-stu-id="3ecdd-106">The first <xref:System.Windows.Window> to be instantiated will most likely be the window that is specified as the startup [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (see <xref:System.Windows.Application.StartupUri%2A>).</span></span>  
  
 <span data-ttu-id="3ecdd-107">Il primo <xref:System.Windows.Window> potrebbe inoltre essere creata un'istanza tramite codice.</span><span class="sxs-lookup"><span data-stu-id="3ecdd-107">The first <xref:System.Windows.Window> could also be instantiated using code.</span></span> <span data-ttu-id="3ecdd-108">Ad esempio viene aperta una finestra durante l'avvio dell'applicazione, simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="3ecdd-108">One example is opening a window during application startup, like the following:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 <span data-ttu-id="3ecdd-109">In alcuni casi, viene creata un'istanza di primo <xref:System.Windows.Window> è non effettivamente la finestra principale dell'applicazione, ad esempio una schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="3ecdd-109">Sometimes, the first instantiated <xref:System.Windows.Window> is not actually the main application window e.g. a splash screen.</span></span> <span data-ttu-id="3ecdd-110">In questo caso, è possibile specificare la finestra principale dell'applicazione utilizzando il markup, simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="3ecdd-110">In this case, you can specify the main application window using markup, like the following:</span></span>  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 <span data-ttu-id="3ecdd-111">Se la finestra principale viene specificata automaticamente o manualmente, è possibile ottenere la finestra principale e <xref:System.Windows.Application.MainWindow%2A> utilizzando il seguente codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="3ecdd-111">Whether the main window is specified automatically or manually, you can get the main window from <xref:System.Windows.Application.MainWindow%2A> using the following code, like the following:</span></span>  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
