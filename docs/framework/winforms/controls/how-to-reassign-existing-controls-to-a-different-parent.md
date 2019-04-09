---
title: 'Procedura: Riassegnare i controlli esistenti a un elemento padre diverso'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
ms.openlocfilehash: 113afc642ca313f10062a496d2f170e3666d5043
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162243"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="e4a58-102">Procedura: Riassegnare i controlli esistenti a un elemento padre diverso</span><span class="sxs-lookup"><span data-stu-id="e4a58-102">How to: Reassign Existing Controls to a Different Parent</span></span>
<span data-ttu-id="e4a58-103">È possibile assegnare i controlli presenti nel form a un nuovo controllo contenitore.</span><span class="sxs-lookup"><span data-stu-id="e4a58-103">You can assign controls that exist on your form to a new container control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4a58-104">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="e4a58-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e4a58-105">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="e4a58-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e4a58-106">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="e4a58-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="e4a58-107">Per riassegnare i controlli esistenti a un padre diverso</span><span class="sxs-lookup"><span data-stu-id="e4a58-107">To reassign existing controls to a different parent</span></span>  
  
1.  <span data-ttu-id="e4a58-108">Trascinare i tre controlli <xref:System.Windows.Forms.Button> dalla **Casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="e4a58-108">Drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span>  
  
     <span data-ttu-id="e4a58-109">Posizionarli uno accanto a altro, ma lasciarli non allineati.</span><span class="sxs-lookup"><span data-stu-id="e4a58-109">Position them near to each other, but leave them unaligned.</span></span>  
  
2.  <span data-ttu-id="e4a58-110">Nella **Casella degli strumenti**fare clic sull'icona del controllo <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="e4a58-110">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span>  
  
     <span data-ttu-id="e4a58-111">Non trascinare l'icona nel form.</span><span class="sxs-lookup"><span data-stu-id="e4a58-111">Do not drag the icon onto the form.</span></span>  
  
3.  <span data-ttu-id="e4a58-112">Spostare il puntatore del mouse accanto ai tre controlli <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="e4a58-112">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
     <span data-ttu-id="e4a58-113">Il puntatore assume la forma di un mirino con l'icona del controllo <xref:System.Windows.Forms.FlowLayoutPanel> associata.</span><span class="sxs-lookup"><span data-stu-id="e4a58-113">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>  
  
4.  <span data-ttu-id="e4a58-114">Fare clic e tenere premuto il pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="e4a58-114">Click and hold the mouse button.</span></span>  
  
5.  <span data-ttu-id="e4a58-115">Trascinare il puntatore del mouse per disegnare la struttura del controllo <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="e4a58-115">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
6.  <span data-ttu-id="e4a58-116">Disegnare la struttura intorno ai tre controlli <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="e4a58-116">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
7.  <span data-ttu-id="e4a58-117">Rilasciare il pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="e4a58-117">Release the mouse button.</span></span>  
  
     <span data-ttu-id="e4a58-118">I tre controlli <xref:System.Windows.Forms.Button> sono stati inseriti nel controllo <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="e4a58-118">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4a58-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4a58-119">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="e4a58-120">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="e4a58-120">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="e4a58-121">Procedura dettagliata: Disposizione dei controlli in Windows Forms usando TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="e4a58-121">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="e4a58-122">Procedura dettagliata: Disposizione dei controlli in Windows Forms usando le guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="e4a58-122">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
