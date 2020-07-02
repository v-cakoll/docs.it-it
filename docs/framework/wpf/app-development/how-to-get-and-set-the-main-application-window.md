---
title: "Procedura: ottenere e impostare la finestra principale dell'applicazione"
description: Seguire questo esempio per ottenere e impostare la finestra principale dell'applicazione all'interno di Windows Presentation Foundation applicazione (WPF).
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
ms.openlocfilehash: 9bb5bce9b90482796acd8c62e77dc8bd9a850eeb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622679"
---
# <a name="how-to-get-and-set-the-main-application-window"></a>Procedura: ottenere e impostare la finestra principale dell'applicazione
Questo esempio illustra come ottenere e impostare la finestra principale dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Il primo oggetto <xref:System.Windows.Window> di cui viene creata un'istanza all'interno di un'applicazione Windows Presentation Foundation (WPF) viene impostato automaticamente da <xref:System.Windows.Application> come finestra principale dell'applicazione. Il primo oggetto <xref:System.Windows.Window> di cui creare un'istanza sarà probabilmente la finestra specificata come URI (Uniform Resource Identifier) di avvio (vedere <xref:System.Windows.Application.StartupUri%2A> ).  
  
 <xref:System.Windows.Window>È anche possibile creare un'istanza del primo utilizzando il codice. Un esempio è l'apertura di una finestra durante l'avvio dell'applicazione, come la seguente:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 In alcuni casi, la prima istanza di <xref:System.Windows.Window> non è in realtà la finestra principale dell'applicazione, ad esempio una schermata iniziale. In questo caso, è possibile specificare la finestra principale dell'applicazione usando il markup, come indicato di seguito:  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 Se la finestra principale viene specificata automaticamente o manualmente, è possibile ottenere la finestra principale <xref:System.Windows.Application.MainWindow%2A> usando il codice seguente, come segue:  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
