---
title: Controllo TableLayoutPanel (Windows Form)
ms.date: 03/30/2017
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms]
- controls [Windows Forms], sizing
- sizing [Windows Forms], automatic
- layout [Windows Forms], TableLayoutPanel control
- automatic sizing
ms.assetid: f55175c6-424e-4782-a86e-3f79c1550235
ms.openlocfilehash: 3615ab1f9a9076b8db0e5fde1e5bd4a1a804f3bf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538528"
---
# <a name="tablelayoutpanel-control-windows-forms"></a><span data-ttu-id="0d401-102">Controllo TableLayoutPanel (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="0d401-102">TableLayoutPanel Control (Windows Forms)</span></span>
<span data-ttu-id="0d401-103">Il controllo <xref:System.Windows.Forms.TableLayoutPanel> dispone il contenuto in una griglia.</span><span class="sxs-lookup"><span data-stu-id="0d401-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="0d401-104">Poiché il layout viene effettuato sia in fase di progettazione che in fase di esecuzione, può cambiare dinamicamente in base alle modifiche dell'ambiente di applicazione,</span><span class="sxs-lookup"><span data-stu-id="0d401-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="0d401-105">consentendo il ridimensionamento proporzionale dei controlli presenti nel pannello in risposta a modifiche quali il ridimensionamento del controllo padre o la variazione della lunghezza del testo dovuta alla localizzazione.</span><span class="sxs-lookup"><span data-stu-id="0d401-105">This gives the controls in the panel the ability to proportionally resize, so it can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0d401-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="0d401-106">In This Section</span></span>  
 [<span data-ttu-id="0d401-107">Panoramica del controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0d401-107">TableLayoutPanel Control Overview</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)  
 <span data-ttu-id="0d401-108">Introduce i concetti generali del controllo <xref:System.Windows.Forms.TableLayoutPanel>, che consente di creare un layout con righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="0d401-108">Introduces the general concepts of the <xref:System.Windows.Forms.TableLayoutPanel> control, which allows you to create a layout with rows and columns.</span></span>  
  
 [<span data-ttu-id="0d401-109">Procedure consigliate per il controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0d401-109">Best Practices for the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="0d401-110">Fornisce suggerimenti per sfruttare al meglio le funzionalità di layout del controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="0d401-110">Outlines recommendations to help you get the most out of the layout features of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="0d401-111">Comportamento di AutoSize nel controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0d401-111">AutoSize Behavior in the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/autosize-behavior-in-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="0d401-112">Vengono illustrati i modi in cui il controllo <xref:System.Windows.Forms.TableLayoutPanel> supporta il ridimensionamento automatico.</span><span class="sxs-lookup"><span data-stu-id="0d401-112">Explains the ways in which the <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior.</span></span>  
  
 [<span data-ttu-id="0d401-113">Procedura: Agganciare e ancorare controlli figlio in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0d401-113">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 <span data-ttu-id="0d401-114">Illustra come agganciare e ancorare controlli figlio in un controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="0d401-114">Shows how to anchor and dock child controls in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="0d401-115">Procedura: Progettare un layout di Windows Form che risponda correttamente alla localizzazione</span><span class="sxs-lookup"><span data-stu-id="0d401-115">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 <span data-ttu-id="0d401-116">Illustra l'uso di un controllo <xref:System.Windows.Forms.TableLayoutPanel> per creare un form che risponda correttamente alla localizzazione.</span><span class="sxs-lookup"><span data-stu-id="0d401-116">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to localization.</span></span>  
  
 [<span data-ttu-id="0d401-117">Procedura: Creare un Windows Form ridimensionabile per immissione dati</span><span class="sxs-lookup"><span data-stu-id="0d401-117">How to: Create a Resizable Windows Form for Data Entry</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-resizable-windows-form-for-data-entry.md)  
 <span data-ttu-id="0d401-118">Illustra l'uso di un controllo <xref:System.Windows.Forms.TableLayoutPanel> per creare un form che risponda correttamente al ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="0d401-118">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to resizing.</span></span>  
  
1.  <span data-ttu-id="0d401-119">[Procedura: Allineare ed estendere un controllo in un controllo TableLayoutPanel](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="0d401-119">[How to: Align and Stretch a Control in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span></span>  
  
2.  <span data-ttu-id="0d401-120">[Procedura: Inserire righe e colonne in un controllo TableLayoutPanel](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="0d401-120">[How to: Span Rows and Columns in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span></span>  
  
3.  <span data-ttu-id="0d401-121">[Procedura: Modificare colonne e righe in un controllo TableLayoutPanel](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="0d401-121">[How to: Edit Columns and Rows in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span></span>  
  
4.  <span data-ttu-id="0d401-122">[Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="0d401-122">[Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0d401-123">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="0d401-123">Reference</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <span data-ttu-id="0d401-124">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="0d401-124">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 <xref:System.Windows.Forms.TableLayoutSettings>  
 <span data-ttu-id="0d401-125">Fornisce la documentazione di riferimento per il tipo <xref:System.Windows.Forms.TableLayoutSettings>.</span><span class="sxs-lookup"><span data-stu-id="0d401-125">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutSettings> type.</span></span>  
  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <span data-ttu-id="0d401-126">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="0d401-126">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0d401-127">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="0d401-127">Related Sections</span></span>  
 [<span data-ttu-id="0d401-128">Localizzazione</span><span class="sxs-lookup"><span data-stu-id="0d401-128">Localization</span></span>](../../../../docs/standard/globalization-localization/localization.md)  
 <span data-ttu-id="0d401-129">Fornisce una panoramica degli argomenti relativi alla localizzazione.</span><span class="sxs-lookup"><span data-stu-id="0d401-129">Provides an overview of topics relating to localization.</span></span>  
  
 <span data-ttu-id="0d401-130">Vedere anche [localizzazione di applicazioni](http://msdn.microsoft.com/library/z68135h5\(v=vs.110\)) o [localizzazione di applicazioni](http://msdn.microsoft.com/library/z68135h5\(v=vs.120\))</span><span class="sxs-lookup"><span data-stu-id="0d401-130">Also see [Localizing Applications](http://msdn.microsoft.com/library/z68135h5\(v=vs.110\)) or [Localizing Applications](http://msdn.microsoft.com/library/z68135h5\(v=vs.120\))</span></span>
