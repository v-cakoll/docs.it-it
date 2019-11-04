---
title: 'Procedura: applicare uno stile ai controlli di un oggetto ToolBar'
ms.date: 03/30/2017
helpviewer_keywords:
- styling controls on toolbar [WPF]
- toolbars [WPF]
- customizing controls on toolbar [WPF]
ms.assetid: ba6ae056-d6a9-4c24-90f8-467ab0bc0b1a
ms.openlocfilehash: 78b9fc505c3c9045a0ca16ddaa1361c90bcc896a
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459413"
---
# <a name="how-to-style-controls-on-a-toolbar"></a><span data-ttu-id="8a6d1-102">Procedura: applicare uno stile ai controlli di un oggetto ToolBar</span><span class="sxs-lookup"><span data-stu-id="8a6d1-102">How to: Style Controls on a ToolBar</span></span>
<span data-ttu-id="8a6d1-103">Il <xref:System.Windows.Controls.ToolBar> definisce <xref:System.Windows.ResourceKey> oggetti per specificare lo stile dei controlli all'interno della <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="8a6d1-103">The <xref:System.Windows.Controls.ToolBar> defines <xref:System.Windows.ResourceKey> objects to specify the style of controls within the <xref:System.Windows.Controls.ToolBar>.</span></span>  <span data-ttu-id="8a6d1-104">Per applicare uno stile a un controllo in una <xref:System.Windows.Controls.ToolBar>, impostare l'attributo `x:key` dello stile su un <xref:System.Windows.ResourceKey> definito in <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="8a6d1-104">To style a control in a <xref:System.Windows.Controls.ToolBar>, set the `x:key` attribute of the style to a <xref:System.Windows.ResourceKey> defined in <xref:System.Windows.Controls.ToolBar>.</span></span>  
  
 <span data-ttu-id="8a6d1-105">Il <xref:System.Windows.Controls.ToolBar> definisce gli oggetti <xref:System.Windows.ResourceKey> seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a6d1-105">The <xref:System.Windows.Controls.ToolBar> defines the following <xref:System.Windows.ResourceKey> objects:</span></span>  
  
- <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## <a name="example"></a><span data-ttu-id="8a6d1-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a6d1-106">Example</span></span>  
 <span data-ttu-id="8a6d1-107">Nell'esempio seguente vengono definiti gli stili per i controlli all'interno di una <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="8a6d1-107">The following example defines styles for the controls within a <xref:System.Windows.Controls.ToolBar>.</span></span>  
  
 [!code-xaml[ToolBar_snip#ToolBarAllStyles](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xaml[ToolBar_snip#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## <a name="see-also"></a><span data-ttu-id="8a6d1-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a6d1-108">See also</span></span>

- [<span data-ttu-id="8a6d1-109">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="8a6d1-109">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
