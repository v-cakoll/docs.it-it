---
title: Cenni preliminari sul controllo TableLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- TableLayoutPanel
helpviewer_keywords:
- controls [Windows Forms], resizing
- resizable controls [Windows Forms]
- Windows Forms controls, proportional resizing
- Windows Forms, proportional resizing of controls
- layout [Windows Forms], TableLayoutPanel control
- TableLayoutPanel control [Windows Forms], about TableLayoutPanel control
ms.assetid: 337661c8-61cb-44ee-93e0-3662bddec327
ms.openlocfilehash: be7ef4055d809349fe97a3d48e29158c5449576b
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855803"
---
# <a name="tablelayoutpanel-control-overview"></a><span data-ttu-id="64cb1-102">Cenni preliminari sul controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="64cb1-102">TableLayoutPanel Control Overview</span></span>
<span data-ttu-id="64cb1-103">Il controllo <xref:System.Windows.Forms.TableLayoutPanel> dispone il contenuto in una griglia.</span><span class="sxs-lookup"><span data-stu-id="64cb1-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="64cb1-104">Poiché il layout viene effettuato sia in fase di progettazione che in fase di esecuzione, può cambiare dinamicamente in base alle modifiche dell'ambiente di applicazione,</span><span class="sxs-lookup"><span data-stu-id="64cb1-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="64cb1-105">consentendo il ridimensionamento proporzionale dei controlli presenti nel pannello in risposta a modifiche quali il ridimensionamento del controllo padre o la variazione della lunghezza del testo dovuta alla localizzazione.</span><span class="sxs-lookup"><span data-stu-id="64cb1-105">This gives the controls in the panel the ability to proportionally resize, so they can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
 <span data-ttu-id="64cb1-106">Qualsiasi controllo Windows Form può essere figlio del controllo <xref:System.Windows.Forms.TableLayoutPanel>, tra cui altre istanze di <xref:System.Windows.Forms.TableLayoutPanel>,</span><span class="sxs-lookup"><span data-stu-id="64cb1-106">Any Windows Forms control can be a child of the <xref:System.Windows.Forms.TableLayoutPanel> control, including other instances of <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="64cb1-107">consentendo la creazione di layout sofisticati che si adattano alle modifiche in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="64cb1-107">This allows you to construct sophisticated layouts that adapt to changes at run time.</span></span>  
  
 <span data-ttu-id="64cb1-108">Il controllo <xref:System.Windows.Forms.TableLayoutPanel> può espandersi per contenere nuovi controlli aggiunti, a seconda del valore delle proprietà <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> e <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="64cb1-108">The <xref:System.Windows.Forms.TableLayoutPanel> control can expand to accommodate new controls when they are added, depending on the value of the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A>, and <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> properties.</span></span> <span data-ttu-id="64cb1-109">L'impostazione della proprietà <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> o <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> su 0 indica che il controllo <xref:System.Windows.Forms.TableLayoutPanel> non è limitato nella direzione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="64cb1-109">Setting either the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> or <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> property to a value of 0 specifies that the <xref:System.Windows.Forms.TableLayoutPanel> will be unbound in the corresponding direction.</span></span>  
  
 <span data-ttu-id="64cb1-110">È anche possibile controllare la direzione di espansione, orizzontale o verticale, per quando il controllo <xref:System.Windows.Forms.TableLayoutPanel> non riesce più a contenere i controlli figlio.</span><span class="sxs-lookup"><span data-stu-id="64cb1-110">You can also control the direction of expansion (horizontal or vertical) after the <xref:System.Windows.Forms.TableLayoutPanel> control is full of child controls.</span></span> <span data-ttu-id="64cb1-111">Per impostazione predefinita, il controllo <xref:System.Windows.Forms.TableLayoutPanel> si espande verso il basso aggiungendo delle righe.</span><span class="sxs-lookup"><span data-stu-id="64cb1-111">By default, the <xref:System.Windows.Forms.TableLayoutPanel> control expands downward by adding rows.</span></span>  
  
 <span data-ttu-id="64cb1-112">Per modificare il comportamento predefinito di righe e colonne, impostare le proprietà di righe e colonne mediante <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> e <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>.</span><span class="sxs-lookup"><span data-stu-id="64cb1-112">If you want rows and columns that behave differently from the default behavior, you can control the properties of rows and columns by using the <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> and <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> properties.</span></span> <span data-ttu-id="64cb1-113">Le proprietà delle righe possono essere impostate separatamente da quelle delle colonne.</span><span class="sxs-lookup"><span data-stu-id="64cb1-113">You can set the properties of rows or columns individually.</span></span>  
  
 <span data-ttu-id="64cb1-114">Il controllo <xref:System.Windows.Forms.TableLayoutPanel> aggiunge ai propri controlli figlio le proprietà `Cell`, `Column`. `Row`, `ColumnSpan` e `RowSpan`.</span><span class="sxs-lookup"><span data-stu-id="64cb1-114">The <xref:System.Windows.Forms.TableLayoutPanel> control adds the following properties to its child controls: `Cell`, `Column`, `Row`, `ColumnSpan`, and `RowSpan`.</span></span>  
  
 <span data-ttu-id="64cb1-115">Per unire le celle nel controllo <xref:System.Windows.Forms.TableLayoutPanel>, impostare la proprietà `ColumnSpan` o `RowSpan` in un controllo figlio.</span><span class="sxs-lookup"><span data-stu-id="64cb1-115">You can merge cells in the <xref:System.Windows.Forms.TableLayoutPanel> control by setting the `ColumnSpan` or `RowSpan` properties on a child control.</span></span>  
  
1.  [<span data-ttu-id="64cb1-116">Procedura: Allineare ed estendere un controllo in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="64cb1-116">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2.  [<span data-ttu-id="64cb1-117">Procedura: Inserire righe e colonne in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="64cb1-117">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
3.  [<span data-ttu-id="64cb1-118">Procedura: Modificare colonne e righe in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="64cb1-118">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
4.  <span data-ttu-id="64cb1-119">[Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel](https://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="64cb1-119">[Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](https://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64cb1-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64cb1-120">See Also</span></span>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutSettings>  
 [<span data-ttu-id="64cb1-121">Procedura: Progettare un layout di Windows Form che risponda correttamente alla localizzazione</span><span class="sxs-lookup"><span data-stu-id="64cb1-121">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 [<span data-ttu-id="64cb1-122">Procedura: Creare un Windows Form ridimensionabile per immissione dati</span><span class="sxs-lookup"><span data-stu-id="64cb1-122">How to: Create a Resizable Windows Form for Data Entry</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-resizable-windows-form-for-data-entry.md)  
 [<span data-ttu-id="64cb1-123">Procedure consigliate per il controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="64cb1-123">Best Practices for the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)
