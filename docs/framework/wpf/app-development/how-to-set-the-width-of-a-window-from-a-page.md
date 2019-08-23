---
title: 'Procedura: Impostare la larghezza di una finestra da una pagina'
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: 1e16b75ecb85550facdf24a5b9e341cf0c061178
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940769"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a>Procedura: Impostare la larghezza di una finestra da una pagina
Questo esempio illustra come impostare la larghezza della finestra da un oggetto <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Esempio  
 Un <xref:System.Windows.Controls.Page> oggetto può impostare la larghezza della finestra <xref:System.Windows.Controls.Page.WindowWidth%2A>host impostando. Questa proprietà consente <xref:System.Windows.Controls.Page> a di non avere una conoscenza esplicita del tipo di finestra che la ospita.  
  
> [!NOTE]
> Per impostare la larghezza di una finestra utilizzando <xref:System.Windows.Controls.Page.WindowWidth%2A>, un <xref:System.Windows.Controls.Page> oggetto deve essere l'elemento figlio di una finestra.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
