---
title: 'Procedura: passare a una pagina'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: 25a0dbbc609c7b6f8f2878d2068e61e492a59c7e
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582545"
---
# <a name="how-to-navigate-to-a-page"></a>Procedura: passare a una pagina
In questo esempio vengono illustrati diversi modi in cui una pagina può essere spostata da un <xref:System.Windows.Navigation.NavigationWindow>.  
  
## <a name="example"></a>Esempio  
 È possibile che un <xref:System.Windows.Navigation.NavigationWindow> di passare a una pagina usando uno dei seguenti elementi:  
  
- La proprietà <xref:System.Windows.Navigation.NavigationWindow.Source%2A>.  
  
- Metodo <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> .  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
> Gli URI (Uniform Resource Identifier) possono essere relativi o assoluti. Per altre informazioni, vedere [URI di tipo pack in WPF](pack-uris-in-wpf.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
