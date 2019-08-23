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
ms.openlocfilehash: 38814268c9bb271ad3d88d549fb6ec4c6cbfed40
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966034"
---
# <a name="how-to-navigate-to-a-page"></a>Procedura: Passare a una pagina
In questo esempio vengono illustrati diversi modi in cui una pagina può essere spostata da <xref:System.Windows.Navigation.NavigationWindow>un oggetto.  
  
## <a name="example"></a>Esempio  
 Per passare a una pagina <xref:System.Windows.Navigation.NavigationWindow> , è possibile usare uno dei seguenti elementi:  
  
- La proprietà <xref:System.Windows.Navigation.NavigationWindow.Source%2A>.  
  
- Metodo <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> .  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
> [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)]può essere relativo o assoluto. Per altre informazioni, vedere [URI di tipo pack in WPF](pack-uris-in-wpf.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
