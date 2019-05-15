---
title: 'Procedura: Associare ContextMenuStrip a un controllo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
ms.openlocfilehash: e1b2a49196d6da66d478a3d44eab64298cebe969
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586613"
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a><span data-ttu-id="a252d-102">Procedura: Associare ContextMenuStrip a un controllo</span><span class="sxs-lookup"><span data-stu-id="a252d-102">How to: Associate a ContextMenuStrip with a Control</span></span>
<span data-ttu-id="a252d-103">Dopo avere creato controlli e menu di scelta rapida, attenersi alle procedure riportate di seguito per visualizzare un determinato menu di scelta rapida quando l'utente fa clic sul controllo con il pulsante destro del mouse.</span><span class="sxs-lookup"><span data-stu-id="a252d-103">After creating your controls and shortcut menus, use the following procedures to display a given shortcut menu when the user right-clicks the control.</span></span> <span data-ttu-id="a252d-104">Queste procedure consentono di associare un oggetto <xref:System.Windows.Forms.ContextMenuStrip> a un Windows Form e a un controllo <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="a252d-104">These procedures associate a <xref:System.Windows.Forms.ContextMenuStrip> with a Windows Form and with a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a><span data-ttu-id="a252d-105">Per associare un oggetto ContextMenuStrip a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="a252d-105">To associate a ContextMenuStrip with a Windows Form</span></span>  
  
1. <span data-ttu-id="a252d-106">Impostare la proprietà <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> sul nome del controllo <xref:System.Windows.Forms.ContextMenuStrip> associato.</span><span class="sxs-lookup"><span data-stu-id="a252d-106">Set the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a><span data-ttu-id="a252d-107">Per associare un oggetto ContextMenuStrip a un controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="a252d-107">To associate a ContextMenuStrip with a ToolStrip control</span></span>  
  
1. <span data-ttu-id="a252d-108">Impostare la proprietà <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> del controllo sul nome del controllo <xref:System.Windows.Forms.ContextMenuStrip> associato.</span><span class="sxs-lookup"><span data-stu-id="a252d-108">Set the control's <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a252d-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="a252d-109">Example</span></span>  
 <span data-ttu-id="a252d-110">Nell'esempio di codice seguente vengono creati un Windows Form e un controllo <xref:System.Windows.Forms.ToolStrip> e a ciascuno di essi viene associato un controllo <xref:System.Windows.Forms.ContextMenuStrip> diverso.</span><span class="sxs-lookup"><span data-stu-id="a252d-110">The following code example creates a Windows Form and a <xref:System.Windows.Forms.ToolStrip>, and associates a different <xref:System.Windows.Forms.ContextMenuStrip> control with each of them.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a252d-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a252d-111">Compiling the Code</span></span>  
 <span data-ttu-id="a252d-112">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a252d-112">This example requires:</span></span>  
  
- <span data-ttu-id="a252d-113">Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="a252d-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a252d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a252d-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="a252d-115">Procedura: Aggiungere le voci di Menu a un controllo ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="a252d-115">How to: Add Menu Items to a ContextMenuStrip</span></span>](how-to-add-menu-items-to-a-contextmenustrip.md)
- [<span data-ttu-id="a252d-116">Controllo ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="a252d-116">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
