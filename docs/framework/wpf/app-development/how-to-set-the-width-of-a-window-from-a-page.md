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
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a><span data-ttu-id="59835-102">Procedura: Impostare la larghezza di una finestra da una pagina</span><span class="sxs-lookup"><span data-stu-id="59835-102">How to: Set the Width of a Window from a Page</span></span>
<span data-ttu-id="59835-103">Questo esempio illustra come impostare la larghezza della finestra da un oggetto <xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="59835-103">This example illustrates how to set the width of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59835-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="59835-104">Example</span></span>  
 <span data-ttu-id="59835-105">Un <xref:System.Windows.Controls.Page> oggetto può impostare la larghezza della finestra <xref:System.Windows.Controls.Page.WindowWidth%2A>host impostando.</span><span class="sxs-lookup"><span data-stu-id="59835-105">A <xref:System.Windows.Controls.Page> can set the width of its host window by setting <xref:System.Windows.Controls.Page.WindowWidth%2A>.</span></span> <span data-ttu-id="59835-106">Questa proprietà consente <xref:System.Windows.Controls.Page> a di non avere una conoscenza esplicita del tipo di finestra che la ospita.</span><span class="sxs-lookup"><span data-stu-id="59835-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="59835-107">Per impostare la larghezza di una finestra utilizzando <xref:System.Windows.Controls.Page.WindowWidth%2A>, un <xref:System.Windows.Controls.Page> oggetto deve essere l'elemento figlio di una finestra.</span><span class="sxs-lookup"><span data-stu-id="59835-107">To set the width of a window using <xref:System.Windows.Controls.Page.WindowWidth%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
