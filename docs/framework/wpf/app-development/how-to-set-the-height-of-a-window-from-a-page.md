---
title: "Procedura: Impostare l'altezza di una finestra da una pagina"
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: c1041af88241011b51c96d7b61423344a32b25ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940792"
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a>Procedura: Impostare l'altezza di una finestra da una pagina
Questo esempio illustra come impostare l'altezza della finestra da un oggetto <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Esempio  
 Un <xref:System.Windows.Controls.Page> oggetto può impostare l'altezza della finestra <xref:System.Windows.Controls.Page.WindowHeight%2A>host impostando. Questa proprietà consente <xref:System.Windows.Controls.Page> a di non avere una conoscenza esplicita del tipo di finestra che la ospita.  
  
> [!NOTE]
> Per impostare l'altezza di una finestra utilizzando <xref:System.Windows.Controls.Page.WindowHeight%2A>, un <xref:System.Windows.Controls.Page> oggetto deve essere l'elemento figlio di una finestra.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
