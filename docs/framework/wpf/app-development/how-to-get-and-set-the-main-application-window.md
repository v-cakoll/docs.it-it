---
title: "Procedura: ottenere e impostare la finestra principale dell'applicazione"
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
ms.openlocfilehash: ae70b482eba8fb4e0bf587def06bb90d751a4312
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547982"
---
# <a name="how-to-get-and-set-the-main-application-window"></a>Procedura: ottenere e impostare la finestra principale dell'applicazione
In questo esempio viene illustrato come ottenere e impostare la finestra principale dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Il primo <xref:System.Windows.Window> che viene creata un'istanza all'interno di un Windows Presentation Foundation (WPF) dell'applicazione verrà impostata automaticamente da <xref:System.Windows.Application> come la finestra principale dell'applicazione. Il primo <xref:System.Windows.Window> sia stata creata un'istanza sarà probabilmente la finestra viene specificato come l'avvio [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (vedere <xref:System.Windows.Application.StartupUri%2A>).  
  
 Il primo <xref:System.Windows.Window> potrebbe inoltre essere creata un'istanza tramite codice. Ad esempio viene aperta una finestra durante l'avvio dell'applicazione, simile al seguente:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 In alcuni casi, viene creata un'istanza di primo <xref:System.Windows.Window> è non effettivamente la finestra principale dell'applicazione, ad esempio una schermata iniziale. In questo caso, è possibile specificare la finestra principale dell'applicazione utilizzando il markup, simile al seguente:  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 Se la finestra principale viene specificata automaticamente o manualmente, è possibile ottenere la finestra principale e <xref:System.Windows.Application.MainWindow%2A> utilizzando il seguente codice simile al seguente:  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
