---
title: 'Procedura: allineare ed estendere un controllo in un controllo TableLayoutPanel'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 043adb68b88ab031cea3de1206d1f2c4252b75d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a><span data-ttu-id="85e3c-102">Procedura: allineare ed estendere un controllo in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="85e3c-102">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>
<span data-ttu-id="85e3c-103">È possibile allineare ed estendere i controlli in un <xref:System.Windows.Forms.TableLayoutPanel> con il <xref:System.Windows.Forms.Control.Anchor%2A> e <xref:System.Windows.Forms.Control.Dock%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="85e3c-103">You can align and stretch controls in a <xref:System.Windows.Forms.TableLayoutPanel> with the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85e3c-104">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="85e3c-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="85e3c-105">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="85e3c-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="85e3c-106">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="85e3c-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-align-and-stretch-a-control"></a><span data-ttu-id="85e3c-107">Per allineare ed estendere un controllo</span><span class="sxs-lookup"><span data-stu-id="85e3c-107">To align and stretch a control</span></span>  
  
1.  <span data-ttu-id="85e3c-108">Trascinare un <xref:System.Windows.Forms.TableLayoutPanel> controllo il **della casella degli strumenti** nel form.</span><span class="sxs-lookup"><span data-stu-id="85e3c-108">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="85e3c-109">Trascinare un <xref:System.Windows.Forms.Button> controllo il **della casella degli strumenti** nella cella superiore sinistra del <xref:System.Windows.Forms.TableLayoutPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="85e3c-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="85e3c-110">Il <xref:System.Windows.Forms.Button> controllo è centrato nella cella.</span><span class="sxs-lookup"><span data-stu-id="85e3c-110">The <xref:System.Windows.Forms.Button> control is centered in the cell.</span></span>  
  
3.  <span data-ttu-id="85e3c-111">Impostare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Anchor%2A> proprietà `Left,Right`.</span><span class="sxs-lookup"><span data-stu-id="85e3c-111">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left,Right`.</span></span> <span data-ttu-id="85e3c-112">Il <xref:System.Windows.Forms.Button> controllo occupa in base alla larghezza della cella.</span><span class="sxs-lookup"><span data-stu-id="85e3c-112">The <xref:System.Windows.Forms.Button> control stretches to match the width of the cell.</span></span>  
  
4.  <span data-ttu-id="85e3c-113">Impostare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Anchor%2A> proprietà `Top,Bottom`.</span><span class="sxs-lookup"><span data-stu-id="85e3c-113">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top,Bottom`.</span></span> <span data-ttu-id="85e3c-114">Il <xref:System.Windows.Forms.Button> controllo occupa in base all'altezza della cella.</span><span class="sxs-lookup"><span data-stu-id="85e3c-114">The <xref:System.Windows.Forms.Button> control stretches to match the height of the cell.</span></span>  
  
5.  <span data-ttu-id="85e3c-115">Impostare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="85e3c-115">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="85e3c-116">Il <xref:System.Windows.Forms.Button> controllo si espande per riempire la cella.</span><span class="sxs-lookup"><span data-stu-id="85e3c-116">The <xref:System.Windows.Forms.Button> control expands to fill the cell.</span></span>  
  
6.  <span data-ttu-id="85e3c-117">Impostare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="85e3c-117">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.None>.</span></span> <span data-ttu-id="85e3c-118">Il <xref:System.Windows.Forms.Button> controllo si sposterà all'angolo superiore sinistro della cella e restituisce le dimensioni originali.</span><span class="sxs-lookup"><span data-stu-id="85e3c-118">The <xref:System.Windows.Forms.Button> control returns to its original size and moves to the upper-left corner of the cell.</span></span> <span data-ttu-id="85e3c-119">Il **Progettazione Windows Form** è impostato il <xref:System.Windows.Forms.Control.Anchor%2A> proprietà `Top, Left`.</span><span class="sxs-lookup"><span data-stu-id="85e3c-119">The **Windows Forms Designer** has set the <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span>  
  
7.  <span data-ttu-id="85e3c-120">Impostare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Anchor%2A> proprietà `Bottom,Right`.</span><span class="sxs-lookup"><span data-stu-id="85e3c-120">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Bottom,Right`.</span></span> <span data-ttu-id="85e3c-121">Il <xref:System.Windows.Forms.Button> controllo si sposta nell'angolo inferiore destro della cella.</span><span class="sxs-lookup"><span data-stu-id="85e3c-121">The <xref:System.Windows.Forms.Button> control moves to the lower-right corner of the cell.</span></span>  
  
8.  <span data-ttu-id="85e3c-122">Impostare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Anchor%2A> proprietà <xref:System.Windows.Forms.AnchorStyles.None>.</span><span class="sxs-lookup"><span data-stu-id="85e3c-122">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.None>.</span></span> <span data-ttu-id="85e3c-123">Il <xref:System.Windows.Forms.Button> controllo viene spostata al centro della cella.</span><span class="sxs-lookup"><span data-stu-id="85e3c-123">The <xref:System.Windows.Forms.Button> control moves to the center of the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e3c-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85e3c-124">See Also</span></span>  
 [<span data-ttu-id="85e3c-125">Controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="85e3c-125">TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
