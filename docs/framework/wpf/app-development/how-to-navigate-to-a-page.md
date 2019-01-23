---
title: 'Procedura: Passare a una pagina'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: 7b76a12cbe6e1622e5624f5416abf24a4ca292a4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536910"
---
# <a name="how-to-navigate-to-a-page"></a>Procedura: Passare a una pagina
In questo esempio vengono illustrati vari modi in cui una pagina per spostarsi da un <xref:System.Windows.Navigation.NavigationWindow>.  
  
## <a name="example"></a>Esempio  
 È possibile che un <xref:System.Windows.Navigation.NavigationWindow> per passare alla pagina utilizzando uno dei seguenti:  
  
-   La proprietà <xref:System.Windows.Navigation.NavigationWindow.Source%2A>.  
  
-   Metodo <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> .  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)] può essere relativo o assoluto. Per altre informazioni, vedere [URI di tipo pack in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
