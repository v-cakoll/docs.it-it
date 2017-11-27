---
title: 'Procedura: impostare l''altezza di una finestra da una pagina'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 29de47eceae4b8927f2701ca0bbda2ecc7243919
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a><span data-ttu-id="198ad-102">Procedura: impostare l'altezza di una finestra da una pagina</span><span class="sxs-lookup"><span data-stu-id="198ad-102">How to: Set the Height of a Window from a Page</span></span>
<span data-ttu-id="198ad-103">In questo esempio viene illustrato come impostare l'altezza della finestra da un <xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="198ad-103">This example illustrates how to set the height of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="198ad-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="198ad-104">Example</span></span>  
 <span data-ttu-id="198ad-105">Oggetto <xref:System.Windows.Controls.Page> possibile impostare l'altezza della finestra host impostando <xref:System.Windows.Controls.Page.WindowHeight%2A>.</span><span class="sxs-lookup"><span data-stu-id="198ad-105">A <xref:System.Windows.Controls.Page> can set the height of its host window by setting <xref:System.Windows.Controls.Page.WindowHeight%2A>.</span></span> <span data-ttu-id="198ad-106">Questa proprietà consente di <xref:System.Windows.Controls.Page> senza che abbiano una conoscenza esplicita del tipo di finestra che lo ospita.</span><span class="sxs-lookup"><span data-stu-id="198ad-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="198ad-107">Per impostare l'altezza di una finestra utilizzando <xref:System.Windows.Controls.Page.WindowHeight%2A>, <xref:System.Windows.Controls.Page> deve essere il figlio di una finestra.</span><span class="sxs-lookup"><span data-stu-id="198ad-107">To set the height of a window using <xref:System.Windows.Controls.Page.WindowHeight%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
