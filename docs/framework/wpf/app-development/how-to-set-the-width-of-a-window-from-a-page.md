---
title: 'Procedura: impostare la larghezza di una finestra da una pagina'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7354a6c3f1b913494da9ad45181a0c7741a1cfa2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a>Procedura: impostare la larghezza di una finestra da una pagina
In questo esempio viene illustrato come impostare la larghezza della finestra da un <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Esempio  
 Oggetto <xref:System.Windows.Controls.Page> possibile impostare la larghezza della finestra host impostando <xref:System.Windows.Controls.Page.WindowWidth%2A>. Questa proprietà consente di <xref:System.Windows.Controls.Page> senza che abbiano una conoscenza esplicita del tipo di finestra che lo ospita.  
  
> [!NOTE]
>  Per impostare la larghezza di una finestra utilizzando <xref:System.Windows.Controls.Page.WindowWidth%2A>, <xref:System.Windows.Controls.Page> deve essere il figlio di una finestra.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
