---
title: 'Procedura: navigare in avanti o indietro nella cronologia di navigazione'
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
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7ad909af071d4006346d64ad8e4bd7b57c4eefad
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a>Procedura: navigare in avanti o indietro nella cronologia di navigazione
In questo esempio viene illustrato come spostarsi in avanti o indietro per le voci nella cronologia di navigazione.  
  
## <a name="example"></a>Esempio  
 Codice che viene eseguita dal contenuto di host seguenti può spostarsi in avanti o indietro nella cronologia di navigazione, una voce per volta.  
  
-   <xref:System.Windows.Navigation.NavigationWindow>utilizzo<xref:System.Windows.Navigation.NavigationService>  
  
-   <xref:System.Windows.Controls.Frame>utilizzo<xref:System.Windows.Navigation.NavigationService>  
  
-   [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 Prima è possibile spostarsi avanti di una voce, è necessario verificare che siano presenti voci nella cronologia di navigazione in avanti controllando il **CanGoForward** proprietà. Per spostarsi avanti di una voce, si chiama il **GoForward** metodo. Questo comportamento è illustrato nell'esempio seguente:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 Prima di spostarsi indietro di una voce, è necessario innanzitutto controllare che siano presenti voci nella cronologia di navigazione all'indietro controllando il **CanGoBack** proprietà. Per spostarsi indietro di una voce, si chiama il **GoBack** metodo. Questo comportamento è illustrato nell'esempio seguente:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoForward**, **GoForward**, **CanGoBack**, e **GoBack** vengono implementati da <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, e <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  Se si chiama **GoForward**, e non sono presenti voci nella cronologia di navigazione in avanti, o se si chiama **GoBack**, e non sono presenti voci nella cronologia di navigazione all'indietro, un <xref:System.InvalidOperationException> viene generata un'eccezione.
