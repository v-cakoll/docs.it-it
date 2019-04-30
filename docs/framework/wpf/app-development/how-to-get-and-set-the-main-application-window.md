---
title: "Procedura: Ottenere e impostare la finestra principale dell'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows objects [WPF], setting
- setting windows objects [WPF]
- windows objects [WPF], getting
- getting windows objects [WPF]
ms.assetid: ec902bc4-4a59-46f5-8ec1-963b46789356
ms.openlocfilehash: ea8333aa82f1159afb438215940ee1e7c2605e96
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947797"
---
# <a name="how-to-get-and-set-the-main-application-window"></a><span data-ttu-id="4b8da-102">Procedura: Ottenere e impostare la finestra principale dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="4b8da-102">How to: Get and Set the Main Application Window</span></span>
<span data-ttu-id="4b8da-103">In questo esempio viene illustrato come ottenere e impostare la finestra principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b8da-103">This example shows how to get and set the main application window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b8da-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b8da-104">Example</span></span>  
 <span data-ttu-id="4b8da-105">Il primo <xref:System.Windows.Window> che viene creata un'istanza all'interno di un Windows Presentation Foundation (WPF) dell'applicazione viene impostata automaticamente da <xref:System.Windows.Application> come finestra principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b8da-105">The first <xref:System.Windows.Window> that is instantiated within a Windows Presentation Foundation (WPF) application is automatically set by <xref:System.Windows.Application> as the main application window.</span></span> <span data-ttu-id="4b8da-106">Il primo <xref:System.Windows.Window> sia stata creata un'istanza sarà probabilmente la finestra viene specificato come l'avvio [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (vedere <xref:System.Windows.Application.StartupUri%2A>).</span><span class="sxs-lookup"><span data-stu-id="4b8da-106">The first <xref:System.Windows.Window> to be instantiated will most likely be the window that is specified as the startup [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (see <xref:System.Windows.Application.StartupUri%2A>).</span></span>  
  
 <span data-ttu-id="4b8da-107">Il primo <xref:System.Windows.Window> potrebbe inoltre essere creata un'istanza usando il codice.</span><span class="sxs-lookup"><span data-stu-id="4b8da-107">The first <xref:System.Windows.Window> could also be instantiated using code.</span></span> <span data-ttu-id="4b8da-108">Un esempio viene aperta una finestra durante l'avvio dell'applicazione, come segue:</span><span class="sxs-lookup"><span data-stu-id="4b8da-108">One example is opening a window during application startup, like the following:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 <span data-ttu-id="4b8da-109">In alcuni casi, viene creata un'istanza di primo <xref:System.Windows.Window> è non effettivamente la finestra principale dell'applicazione, ad esempio una schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="4b8da-109">Sometimes, the first instantiated <xref:System.Windows.Window> is not actually the main application window e.g. a splash screen.</span></span> <span data-ttu-id="4b8da-110">In questo caso, è possibile specificare la finestra principale dell'applicazione tramite markup simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="4b8da-110">In this case, you can specify the main application window using markup, like the following:</span></span>  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 <span data-ttu-id="4b8da-111">Se la finestra principale viene specificata automaticamente o manualmente, è possibile ottenere la finestra principale e <xref:System.Windows.Application.MainWindow%2A> usando il codice seguente, simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="4b8da-111">Whether the main window is specified automatically or manually, you can get the main window from <xref:System.Windows.Application.MainWindow%2A> using the following code, like the following:</span></span>  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
