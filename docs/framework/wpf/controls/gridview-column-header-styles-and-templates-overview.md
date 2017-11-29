---
title: Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- column headers [WPF], customizing
- ListView controls [WPF], GridView column header styles
- controls [WPF], ListView
- headers [WPF], customizing
- GridView view mode [WPF], customizing column headers
ms.assetid: 74835674-a39e-4ab5-9418-ad7f6ab7b956
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ad0f7cacc8256e060bb12611bd1818b694e1e6dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="gridview-column-header-styles-and-templates-overview"></a><span data-ttu-id="2e441-102">Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView</span><span class="sxs-lookup"><span data-stu-id="2e441-102">GridView Column Header Styles and Templates Overview</span></span>
<span data-ttu-id="2e441-103">Questa panoramica illustra l'ordine di precedenza per le proprietà che consentono di personalizzare in un'intestazione di colonna il <xref:System.Windows.Controls.GridView> modalità di visualizzazione di un <xref:System.Windows.Controls.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="2e441-103">This overview discusses the order of precedence for properties that you use to customize a column header in the <xref:System.Windows.Controls.GridView> view mode of a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="customizing-a-column-header-in-a-gridview"></a><span data-ttu-id="2e441-104">Personalizzazione di un'intestazione di colonna in un controllo GridView.</span><span class="sxs-lookup"><span data-stu-id="2e441-104">Customizing a Column Header in a GridView</span></span>  
 <span data-ttu-id="2e441-105">Le proprietà che definiscono il contenuto, layout e lo stile di un'intestazione di colonna in un <xref:System.Windows.Controls.GridView> sono disponibili in molte classi correlate.</span><span class="sxs-lookup"><span data-stu-id="2e441-105">The properties that define the content, layout, and style of a column header in a <xref:System.Windows.Controls.GridView> are found on many related classes.</span></span> <span data-ttu-id="2e441-106">Alcune di queste proprietà presentano funzionalità simili o uguali.</span><span class="sxs-lookup"><span data-stu-id="2e441-106">Some of these properties have functionality that is similar or the same.</span></span>  
  
 <span data-ttu-id="2e441-107">Le righe nella tabella seguente mostrano i gruppi di proprietà che eseguono la stessa funzione.</span><span class="sxs-lookup"><span data-stu-id="2e441-107">The rows in the following table show groups of properties that perform the same function.</span></span> <span data-ttu-id="2e441-108">È possibile utilizzare queste proprietà per personalizzare le intestazioni di colonna in un <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="2e441-108">You can use these properties to customize the column headers in a <xref:System.Windows.Controls.GridView>.</span></span> <span data-ttu-id="2e441-109">L'ordine di precedenza per le proprietà correlate è da destra a sinistra, in cui la proprietà nella colonna all'estrema destra ha la precedenza più alta.</span><span class="sxs-lookup"><span data-stu-id="2e441-109">The order of precedence for related properties is from right to left where the property in the farthest right column has the highest precedence.</span></span> <span data-ttu-id="2e441-110">Ad esempio, se un <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> è impostato sul <xref:System.Windows.Controls.GridViewColumnHeader> oggetto e <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> è impostata sull'oggetto associato <xref:System.Windows.Controls.GridViewColumn>, il <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="2e441-110">For example, if a <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> is set on the <xref:System.Windows.Controls.GridViewColumnHeader> object and the <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> is set on the associated <xref:System.Windows.Controls.GridViewColumn>, the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> takes precedence.</span></span> <span data-ttu-id="2e441-111">In questo scenario, il <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="2e441-111">In this scenario, the <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> has no effect.</span></span>  
  
 <span data-ttu-id="2e441-112">**Proprietà correlate per le intestazioni di colonna in un controllo GridView.**</span><span class="sxs-lookup"><span data-stu-id="2e441-112">**Related properties for column headers in a GridView**</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="2e441-113">**Classi**</span><span class="sxs-lookup"><span data-stu-id="2e441-113">**Classes**</span></span>|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|<span data-ttu-id="2e441-114">**Proprietà di contesto di Menu**</span><span class="sxs-lookup"><span data-stu-id="2e441-114">**Context Menu Properties**</span></span>|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|<span data-ttu-id="2e441-115">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="2e441-115">Not applicable</span></span>|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|<span data-ttu-id="2e441-116">**ToolTip**</span><span class="sxs-lookup"><span data-stu-id="2e441-116">**ToolTip**</span></span><br /><br /> <span data-ttu-id="2e441-117">**Proprietà**</span><span class="sxs-lookup"><span data-stu-id="2e441-117">**Properties**</span></span>|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|<span data-ttu-id="2e441-118">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="2e441-118">Not applicable</span></span>|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|<span data-ttu-id="2e441-119">**Modello di intestazione**</span><span class="sxs-lookup"><span data-stu-id="2e441-119">**Header Template**</span></span><br /><br /> <span data-ttu-id="2e441-120">**Proprietà**</span><span class="sxs-lookup"><span data-stu-id="2e441-120">**Properties**</span></span>|<span data-ttu-id="2e441-121"><xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>/</span><span class="sxs-lookup"><span data-stu-id="2e441-121"><xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>/</span></span><br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<span data-ttu-id="2e441-122"><xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>/</span><span class="sxs-lookup"><span data-stu-id="2e441-122"><xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>/</span></span><br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<span data-ttu-id="2e441-123"><xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>/</span><span class="sxs-lookup"><span data-stu-id="2e441-123"><xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>/</span></span><br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|<span data-ttu-id="2e441-124">**Proprietà di stile**</span><span class="sxs-lookup"><span data-stu-id="2e441-124">**Style Properties**</span></span>|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <span data-ttu-id="2e441-125"><sup>1</sup>per **proprietà modello di intestazione**, se si imposta sia il modello e proprietà del selettore di modello, la proprietà di modello ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="2e441-125"><sup>1</sup>For **Header Template Properties**, if you set both the template and template selector properties, the template property takes precedence.</span></span> <span data-ttu-id="2e441-126">Ad esempio, se si impostano entrambe le <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> e <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> proprietà, il <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> proprietà ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="2e441-126">For example, if you set both the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> and <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> properties, the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> property takes precedence.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e441-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e441-127">See Also</span></span>  
 [<span data-ttu-id="2e441-128">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="2e441-128">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="2e441-129">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="2e441-129">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="2e441-130">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="2e441-130">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
