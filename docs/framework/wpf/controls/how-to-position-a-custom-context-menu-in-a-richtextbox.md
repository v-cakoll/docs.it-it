---
title: 'Procedura: Posizionare un menu di scelta rapida personalizzato in un controllo RichTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom context menus [WPF], positioning
- positioning custom context menus [WPF]
- RichTextBox control [WPF], positioning custom context menus
- context menus [WPF], positioning
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
ms.openlocfilehash: f9407f59c3daafd09fa5b84006f33ef2f3ebd31f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770825"
---
# <a name="how-to-position-a-custom-context-menu-in-a-richtextbox"></a><span data-ttu-id="dbaa8-102">Procedura: Posizionare un menu di scelta rapida personalizzato in un controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="dbaa8-102">How to: Position a Custom Context Menu in a RichTextBox</span></span>
<span data-ttu-id="dbaa8-103">In questo esempio mostra come posizionare un menu contestuale personalizzato per un <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="dbaa8-103">This example shows how to position a custom context menu for a <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="dbaa8-104">Quando si implementa un menu contestuale personalizzato per un oggetto **RichTextBox**, si è responsabili della gestione del posizionamento del menu contestuale.</span><span class="sxs-lookup"><span data-stu-id="dbaa8-104">When you implement a custom context menu for a **RichTextBox**, you are responsible for handling the placement of the context menu.</span></span>  <span data-ttu-id="dbaa8-105">Per impostazione predefinita, un menu contestuale personalizzato si apre al centro dell'oggetto **RichTextBox**.</span><span class="sxs-lookup"><span data-stu-id="dbaa8-105">By default, a custom context menu is opened at the center of the **RichTextBox**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbaa8-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="dbaa8-106">Example</span></span>  
 <span data-ttu-id="dbaa8-107">Per eseguire l'override del comportamento del posizionamento predefinito, aggiungere un listener per il <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> evento.</span><span class="sxs-lookup"><span data-stu-id="dbaa8-107">To override the default placement behavior, add a listener for the <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event.</span></span>  <span data-ttu-id="dbaa8-108">L'esempio seguente illustra come eseguire questa operazione a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="dbaa8-108">The following example shows how to do this programmatically.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a><span data-ttu-id="dbaa8-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="dbaa8-109">Example</span></span>  
 <span data-ttu-id="dbaa8-110">Nell'esempio seguente viene illustrata un'implementazione corrispondente <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> listener di eventi.</span><span class="sxs-lookup"><span data-stu-id="dbaa8-110">The following example shows an implementation the corresponding <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event listener.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="dbaa8-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbaa8-111">See also</span></span>

- [<span data-ttu-id="dbaa8-112">Cenni preliminari sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="dbaa8-112">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="dbaa8-113">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="dbaa8-113">TextBox Overview</span></span>](textbox-overview.md)
