---
title: 'Procedura: Impostare la larghezza di una finestra da una pagina'
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: fee6d4c9ae9dae03e81cc4be56576763cb59958b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006715"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a>Procedura: Impostare la larghezza di una finestra da una pagina
In questo esempio viene illustrato come impostare la larghezza della finestra da una <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Esempio  
 Oggetto <xref:System.Windows.Controls.Page> possono impostare la larghezza della finestra host impostando <xref:System.Windows.Controls.Page.WindowWidth%2A>. Questa proprietà consente la <xref:System.Windows.Controls.Page> senza che abbiano una conoscenza esplicita del tipo di finestra che lo ospita.  
  
> [!NOTE]
>  Impostare la larghezza di una finestra tramite <xref:System.Windows.Controls.Page.WindowWidth%2A>, un <xref:System.Windows.Controls.Page> deve essere il figlio di una finestra.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
