---
title: 'Procedura: Impostare il titolo di una finestra da una pagina'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: 0f618af89965822b0df96a264997dabd9cae7608
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940779"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a><span data-ttu-id="8a266-102">Procedura: Impostare il titolo di una finestra da una pagina</span><span class="sxs-lookup"><span data-stu-id="8a266-102">How to: Set the Title of a Window from a Page</span></span>
<span data-ttu-id="8a266-103">Questo esempio illustra come impostare il titolo della finestra in cui è ospitato un <xref:System.Windows.Controls.Page> oggetto.</span><span class="sxs-lookup"><span data-stu-id="8a266-103">This example shows how to set the title of the window in which a <xref:System.Windows.Controls.Page> is hosted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a266-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a266-104">Example</span></span>  
 <span data-ttu-id="8a266-105">Una pagina può modificare il titolo della finestra che lo ospita impostando la <xref:System.Windows.Controls.Page.WindowTitle%2A> proprietà, come segue:</span><span class="sxs-lookup"><span data-stu-id="8a266-105">A page can change the title of the window that is hosting it by setting the <xref:System.Windows.Controls.Page.WindowTitle%2A> property, like so:</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
> <span data-ttu-id="8a266-106">L'impostazione <xref:System.Windows.Controls.Page.Title%2A> della proprietà di una pagina non comporta la modifica del valore del titolo della finestra.</span><span class="sxs-lookup"><span data-stu-id="8a266-106">Setting the <xref:System.Windows.Controls.Page.Title%2A> property of a page does not change the value of the window title.</span></span> <span data-ttu-id="8a266-107"><xref:System.Windows.Controls.Page.Title%2A> Specifica invece il nome di una voce di pagina nella cronologia di navigazione.</span><span class="sxs-lookup"><span data-stu-id="8a266-107">Instead, <xref:System.Windows.Controls.Page.Title%2A> specifies the name of a page entry in navigation history.</span></span>
