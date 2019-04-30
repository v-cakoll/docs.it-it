---
title: "Procedura: Impostare l'altezza di una finestra da una pagina"
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: c99ea134478635f368b71443f43e4d8f772cb5aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007302"
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a><span data-ttu-id="36e09-102">Procedura: Impostare l'altezza di una finestra da una pagina</span><span class="sxs-lookup"><span data-stu-id="36e09-102">How to: Set the Height of a Window from a Page</span></span>
<span data-ttu-id="36e09-103">In questo esempio viene illustrato come impostare l'altezza della finestra da una <xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="36e09-103">This example illustrates how to set the height of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36e09-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="36e09-104">Example</span></span>  
 <span data-ttu-id="36e09-105">Oggetto <xref:System.Windows.Controls.Page> possono impostare l'altezza della finestra host impostando <xref:System.Windows.Controls.Page.WindowHeight%2A>.</span><span class="sxs-lookup"><span data-stu-id="36e09-105">A <xref:System.Windows.Controls.Page> can set the height of its host window by setting <xref:System.Windows.Controls.Page.WindowHeight%2A>.</span></span> <span data-ttu-id="36e09-106">Questa proprietà consente la <xref:System.Windows.Controls.Page> senza che abbiano una conoscenza esplicita del tipo di finestra che lo ospita.</span><span class="sxs-lookup"><span data-stu-id="36e09-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36e09-107">Per impostare l'altezza di una finestra tramite <xref:System.Windows.Controls.Page.WindowHeight%2A>, un <xref:System.Windows.Controls.Page> deve essere il figlio di una finestra.</span><span class="sxs-lookup"><span data-stu-id="36e09-107">To set the height of a window using <xref:System.Windows.Controls.Page.WindowHeight%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
