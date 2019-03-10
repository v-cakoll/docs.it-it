---
title: 'Procedura: Associare un controllo ContextMenuStrip'
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
ms.openlocfilehash: 4b61da8dc9f36e0a80807547e2049ef512c94747
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718337"
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a><span data-ttu-id="bc2ab-102">Procedura: Associare un controllo ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="bc2ab-102">How to: Associate a ContextMenuStrip with a Control</span></span>
<span data-ttu-id="bc2ab-103">Dopo avere creato controlli e menu di scelta rapida, attenersi alle procedure riportate di seguito per visualizzare un determinato menu di scelta rapida quando l'utente fa clic sul controllo con il pulsante destro del mouse.</span><span class="sxs-lookup"><span data-stu-id="bc2ab-103">After creating your controls and shortcut menus, use the following procedures to display a given shortcut menu when the user right-clicks the control.</span></span> <span data-ttu-id="bc2ab-104">Queste procedure consentono di associare un oggetto <xref:System.Windows.Forms.ContextMenuStrip> a un Windows Form e a un controllo <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="bc2ab-104">These procedures associate a <xref:System.Windows.Forms.ContextMenuStrip> with a Windows Form and with a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a><span data-ttu-id="bc2ab-105">Per associare un oggetto ContextMenuStrip a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="bc2ab-105">To associate a ContextMenuStrip with a Windows Form</span></span>  
  
1.  <span data-ttu-id="bc2ab-106">Impostare la proprietà <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> sul nome del controllo <xref:System.Windows.Forms.ContextMenuStrip> associato.</span><span class="sxs-lookup"><span data-stu-id="bc2ab-106">Set the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a><span data-ttu-id="bc2ab-107">Per associare un oggetto ContextMenuStrip a un controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="bc2ab-107">To associate a ContextMenuStrip with a ToolStrip control</span></span>  
  
1.  <span data-ttu-id="bc2ab-108">Impostare la proprietà <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> del controllo sul nome del controllo <xref:System.Windows.Forms.ContextMenuStrip> associato.</span><span class="sxs-lookup"><span data-stu-id="bc2ab-108">Set the control's <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc2ab-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc2ab-109">Example</span></span>  
 <span data-ttu-id="bc2ab-110">Nell'esempio di codice seguente vengono creati un Windows Form e un controllo <xref:System.Windows.Forms.ToolStrip> e a ciascuno di essi viene associato un controllo <xref:System.Windows.Forms.ContextMenuStrip> diverso.</span><span class="sxs-lookup"><span data-stu-id="bc2ab-110">The following code example creates a Windows Form and a <xref:System.Windows.Forms.ToolStrip>, and associates a different <xref:System.Windows.Forms.ContextMenuStrip> control with each of them.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bc2ab-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="bc2ab-111">Compiling the Code</span></span>  
 <span data-ttu-id="bc2ab-112">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc2ab-112">This example requires:</span></span>  
  
-   <span data-ttu-id="bc2ab-113">Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="bc2ab-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="bc2ab-114">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="bc2ab-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="bc2ab-115">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="bc2ab-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc2ab-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc2ab-116">See also</span></span>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="bc2ab-117">Procedura: Aggiungere le voci di Menu a un controllo ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="bc2ab-117">How to: Add Menu Items to a ContextMenuStrip</span></span>](how-to-add-menu-items-to-a-contextmenustrip.md)
- [<span data-ttu-id="bc2ab-118">Controllo ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="bc2ab-118">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
