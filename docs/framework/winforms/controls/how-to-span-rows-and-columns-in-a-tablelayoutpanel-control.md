---
title: 'Procedura: inserire righe e colonne in un controllo TableLayoutPanel'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 24b281e6e1ab56e2c7387435bf2429e7e107c4b8
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a><span data-ttu-id="bfbd3-102">Procedura: inserire righe e colonne in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="bfbd3-102">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>
<span data-ttu-id="bfbd3-103">Controlli in un <xref:System.Windows.Forms.TableLayoutPanel> controllo può estendersi su righe e colonne adiacenti.</span><span class="sxs-lookup"><span data-stu-id="bfbd3-103">Controls in a <xref:System.Windows.Forms.TableLayoutPanel> control can span adjacent rows and columns.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfbd3-104">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="bfbd3-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="bfbd3-105">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="bfbd3-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="bfbd3-106">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="bfbd3-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-span-columns-and-rows"></a><span data-ttu-id="bfbd3-107">Per inserire righe e colonne</span><span class="sxs-lookup"><span data-stu-id="bfbd3-107">To span columns and rows</span></span>  
  
1.  <span data-ttu-id="bfbd3-108">Trascinare un <xref:System.Windows.Forms.TableLayoutPanel> controllo il **della casella degli strumenti** nel form.</span><span class="sxs-lookup"><span data-stu-id="bfbd3-108">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="bfbd3-109">Trascinare un <xref:System.Windows.Forms.Button> controllo il **della casella degli strumenti** nella cella superiore sinistra del <xref:System.Windows.Forms.TableLayoutPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="bfbd3-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
3.  <span data-ttu-id="bfbd3-110">Impostare il <xref:System.Windows.Forms.Button> del controllo **ColumnSpan** proprietà **2**.</span><span class="sxs-lookup"><span data-stu-id="bfbd3-110">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **2**.</span></span> <span data-ttu-id="bfbd3-111">Si noti che il <xref:System.Windows.Forms.Button> controllo si estende la prima e la seconda colonna.</span><span class="sxs-lookup"><span data-stu-id="bfbd3-111">Note that the <xref:System.Windows.Forms.Button> control spans the first and second columns.</span></span>  
  
4.  <span data-ttu-id="bfbd3-112">Impostare il <xref:System.Windows.Forms.Button> del controllo **RowSpan** proprietà **2**.</span><span class="sxs-lookup"><span data-stu-id="bfbd3-112">Set the <xref:System.Windows.Forms.Button> control's **RowSpan** property to **2**.</span></span> <span data-ttu-id="bfbd3-113">Si noti che il <xref:System.Windows.Forms.Button> controllo si estende la prima e seconda riga.</span><span class="sxs-lookup"><span data-stu-id="bfbd3-113">Note that the <xref:System.Windows.Forms.Button> control spans the first and second rows.</span></span>  
  
5.  <span data-ttu-id="bfbd3-114">Impostare il <xref:System.Windows.Forms.Button> del controllo **ColumnSpan** proprietà **1**.</span><span class="sxs-lookup"><span data-stu-id="bfbd3-114">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **1**.</span></span> <span data-ttu-id="bfbd3-115">Si noti che il <xref:System.Windows.Forms.Button> controllo si sposta nella prima colonna e inserisce le righe del prima e seconda.</span><span class="sxs-lookup"><span data-stu-id="bfbd3-115">Note that the <xref:System.Windows.Forms.Button> control moves into the first column and spans the first and second rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfbd3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfbd3-116">See Also</span></span>  
 [<span data-ttu-id="bfbd3-117">Controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="bfbd3-117">TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
