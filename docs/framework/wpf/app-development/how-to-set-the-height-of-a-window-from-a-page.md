---
title: "Procedura: Impostare l'altezza di una finestra da una pagina"
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: c99ea134478635f368b71443f43e4d8f772cb5aa
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370967"
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a>Procedura: Impostare l'altezza di una finestra da una pagina
In questo esempio viene illustrato come impostare l'altezza della finestra da una <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Esempio  
 Oggetto <xref:System.Windows.Controls.Page> possono impostare l'altezza della finestra host impostando <xref:System.Windows.Controls.Page.WindowHeight%2A>. Questa proprietà consente la <xref:System.Windows.Controls.Page> senza che abbiano una conoscenza esplicita del tipo di finestra che lo ospita.  
  
> [!NOTE]
>  Per impostare l'altezza di una finestra tramite <xref:System.Windows.Controls.Page.WindowHeight%2A>, un <xref:System.Windows.Controls.Page> deve essere il figlio di una finestra.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
