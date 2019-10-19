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
ms.openlocfilehash: 5894761c4b6258cbf90d369a722ffc5abca51885
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582554"
---
# <a name="how-to-get-and-set-the-main-application-window"></a>Procedura: ottenere e impostare la finestra principale dell'applicazione
Questo esempio illustra come ottenere e impostare la finestra principale dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Il primo <xref:System.Windows.Window> di cui viene creata un'istanza in un'applicazione Windows Presentation Foundation (WPF) viene impostato automaticamente <xref:System.Windows.Application> come finestra principale dell'applicazione. Il primo <xref:System.Windows.Window> di cui creare un'istanza sarà probabilmente la finestra specificata come URI (Uniform Resource Identifier) di avvio (vedere <xref:System.Windows.Application.StartupUri%2A>).  
  
 È anche possibile creare un'istanza della prima <xref:System.Windows.Window> usando il codice. Un esempio è l'apertura di una finestra durante l'avvio dell'applicazione, come la seguente:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 In alcuni casi, la prima <xref:System.Windows.Window> di cui è stata creata un'istanza non è in realtà la finestra principale dell'applicazione, ad esempio una schermata iniziale. In questo caso, è possibile specificare la finestra principale dell'applicazione usando il markup, come indicato di seguito:  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 Se la finestra principale viene specificata automaticamente o manualmente, è possibile ottenere la finestra principale da <xref:System.Windows.Application.MainWindow%2A> usando il codice seguente, ad esempio:  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
