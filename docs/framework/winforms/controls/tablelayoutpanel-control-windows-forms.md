---
title: Controllo TableLayoutPanel
ms.date: 03/30/2017
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms]
- controls [Windows Forms], sizing
- sizing [Windows Forms], automatic
- layout [Windows Forms], TableLayoutPanel control
- automatic sizing
ms.assetid: f55175c6-424e-4782-a86e-3f79c1550235
ms.openlocfilehash: 12b40d4ce47770b3ffe9bfdebca74eca4afd3dd1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735515"
---
# <a name="tablelayoutpanel-control-windows-forms"></a><span data-ttu-id="9e0ee-102">Controllo TableLayoutPanel (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="9e0ee-102">TableLayoutPanel Control (Windows Forms)</span></span>
<span data-ttu-id="9e0ee-103">Il controllo <xref:System.Windows.Forms.TableLayoutPanel> dispone il contenuto in una griglia.</span><span class="sxs-lookup"><span data-stu-id="9e0ee-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="9e0ee-104">Poiché il layout viene effettuato sia in fase di progettazione che in fase di esecuzione, può cambiare dinamicamente in base alle modifiche dell'ambiente di applicazione,</span><span class="sxs-lookup"><span data-stu-id="9e0ee-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="9e0ee-105">consentendo il ridimensionamento proporzionale dei controlli presenti nel pannello in risposta a modifiche quali il ridimensionamento del controllo padre o la variazione della lunghezza del testo dovuta alla localizzazione.</span><span class="sxs-lookup"><span data-stu-id="9e0ee-105">This gives the controls in the panel the ability to proportionally resize, so it can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e0ee-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="9e0ee-106">In This Section</span></span>  
 [<span data-ttu-id="9e0ee-107">Panoramica del controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="9e0ee-107">TableLayoutPanel Control Overview</span></span>](tablelayoutpanel-control-overview.md)  
 <span data-ttu-id="9e0ee-108">Introduce i concetti generali del controllo <xref:System.Windows.Forms.TableLayoutPanel>, che consente di creare un layout con righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="9e0ee-108">Introduces the general concepts of the <xref:System.Windows.Forms.TableLayoutPanel> control, which allows you to create a layout with rows and columns.</span></span>  
  
 [<span data-ttu-id="9e0ee-109">Procedure consigliate per il controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="9e0ee-109">Best Practices for the TableLayoutPanel Control</span></span>](best-practices-for-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="9e0ee-110">Fornisce suggerimenti per sfruttare al meglio le funzionalità di layout del controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="9e0ee-110">Outlines recommendations to help you get the most out of the layout features of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="9e0ee-111">Comportamento di AutoSize nel controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="9e0ee-111">AutoSize Behavior in the TableLayoutPanel Control</span></span>](autosize-behavior-in-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="9e0ee-112">Vengono illustrati i modi in cui il controllo <xref:System.Windows.Forms.TableLayoutPanel> supporta il ridimensionamento automatico.</span><span class="sxs-lookup"><span data-stu-id="9e0ee-112">Explains the ways in which the <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior.</span></span>  
  
 [<span data-ttu-id="9e0ee-113">Procedura: Agganciare e ancorare controlli figlio in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="9e0ee-113">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 <span data-ttu-id="9e0ee-114">Illustra come agganciare e ancorare controlli figlio in un controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="9e0ee-114">Shows how to anchor and dock child controls in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="9e0ee-115">Procedura: Progettare un layout di Windows Form che risponda correttamente alla localizzazione</span><span class="sxs-lookup"><span data-stu-id="9e0ee-115">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 <span data-ttu-id="9e0ee-116">Illustra l'uso di un controllo <xref:System.Windows.Forms.TableLayoutPanel> per creare un form che risponda correttamente alla localizzazione.</span><span class="sxs-lookup"><span data-stu-id="9e0ee-116">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to localization.</span></span>  
  
 [<span data-ttu-id="9e0ee-117">Procedura: Creare un Windows Form ridimensionabile per immissione dati</span><span class="sxs-lookup"><span data-stu-id="9e0ee-117">How to: Create a Resizable Windows Form for Data Entry</span></span>](how-to-create-a-resizable-windows-form-for-data-entry.md)  
 <span data-ttu-id="9e0ee-118">Illustra l'uso di un controllo <xref:System.Windows.Forms.TableLayoutPanel> per creare un form che risponda correttamente al ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="9e0ee-118">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to resizing.</span></span>  
  
1. [<span data-ttu-id="9e0ee-119">Procedura: Allineare ed estendere un controllo in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="9e0ee-119">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2. [<span data-ttu-id="9e0ee-120">Procedura: Inserire righe e colonne in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="9e0ee-120">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
3. [<span data-ttu-id="9e0ee-121">Procedura: Modificare colonne e righe in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="9e0ee-121">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
4. [<span data-ttu-id="9e0ee-122">Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="9e0ee-122">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
  
## <a name="reference"></a><span data-ttu-id="9e0ee-123">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="9e0ee-123">Reference</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <span data-ttu-id="9e0ee-124">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="9e0ee-124">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 <xref:System.Windows.Forms.TableLayoutSettings>  
 <span data-ttu-id="9e0ee-125">Fornisce la documentazione di riferimento per il tipo <xref:System.Windows.Forms.TableLayoutSettings>.</span><span class="sxs-lookup"><span data-stu-id="9e0ee-125">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutSettings> type.</span></span>  
  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <span data-ttu-id="9e0ee-126">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="9e0ee-126">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9e0ee-127">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="9e0ee-127">Related Sections</span></span>  
 [<span data-ttu-id="9e0ee-128">Localizzazione</span><span class="sxs-lookup"><span data-stu-id="9e0ee-128">Localization</span></span>](../../../standard/globalization-localization/localization.md)  
 <span data-ttu-id="9e0ee-129">Fornisce una panoramica degli argomenti relativi alla localizzazione.</span><span class="sxs-lookup"><span data-stu-id="9e0ee-129">Provides an overview of topics relating to localization.</span></span>  
  
 <span data-ttu-id="9e0ee-130">Vedere anche [applicazioni localizzate](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/z68135h5(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="9e0ee-130">Also see [Localizing Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/z68135h5(v=vs.120)).</span></span>
