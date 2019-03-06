---
title: 'Procedura: Impostare la larghezza di una finestra da una pagina'
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: fee6d4c9ae9dae03e81cc4be56576763cb59958b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379354"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a><span data-ttu-id="f8cd5-102">Procedura: Impostare la larghezza di una finestra da una pagina</span><span class="sxs-lookup"><span data-stu-id="f8cd5-102">How to: Set the Width of a Window from a Page</span></span>
<span data-ttu-id="f8cd5-103">In questo esempio viene illustrato come impostare la larghezza della finestra da una <xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="f8cd5-103">This example illustrates how to set the width of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8cd5-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8cd5-104">Example</span></span>  
 <span data-ttu-id="f8cd5-105">Oggetto <xref:System.Windows.Controls.Page> possono impostare la larghezza della finestra host impostando <xref:System.Windows.Controls.Page.WindowWidth%2A>.</span><span class="sxs-lookup"><span data-stu-id="f8cd5-105">A <xref:System.Windows.Controls.Page> can set the width of its host window by setting <xref:System.Windows.Controls.Page.WindowWidth%2A>.</span></span> <span data-ttu-id="f8cd5-106">Questa proprietà consente la <xref:System.Windows.Controls.Page> senza che abbiano una conoscenza esplicita del tipo di finestra che lo ospita.</span><span class="sxs-lookup"><span data-stu-id="f8cd5-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8cd5-107">Impostare la larghezza di una finestra tramite <xref:System.Windows.Controls.Page.WindowWidth%2A>, un <xref:System.Windows.Controls.Page> deve essere il figlio di una finestra.</span><span class="sxs-lookup"><span data-stu-id="f8cd5-107">To set the width of a window using <xref:System.Windows.Controls.Page.WindowWidth%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
