---
title: 'Procedura: Estendere un controllo su righe e colonne in un controllo TableLayoutPanel'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: 02db78b07930676235e55e535fb24f6ff618d823
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59339021"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a><span data-ttu-id="66a06-102">Procedura: Estendere un controllo su righe e colonne in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="66a06-102">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>
<span data-ttu-id="66a06-103">Controlli in un <xref:System.Windows.Forms.TableLayoutPanel> controllo può estendersi su righe e colonne adiacenti.</span><span class="sxs-lookup"><span data-stu-id="66a06-103">Controls in a <xref:System.Windows.Forms.TableLayoutPanel> control can span adjacent rows and columns.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66a06-104">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="66a06-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="66a06-105">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="66a06-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="66a06-106">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="66a06-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-span-columns-and-rows"></a><span data-ttu-id="66a06-107">Per inserire righe e colonne</span><span class="sxs-lookup"><span data-stu-id="66a06-107">To span columns and rows</span></span>  
  
1. <span data-ttu-id="66a06-108">Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="66a06-108">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2. <span data-ttu-id="66a06-109">Trascinare un <xref:System.Windows.Forms.Button> controllare dal **casella degli strumenti** alla cella superiore sinistra del <xref:System.Windows.Forms.TableLayoutPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="66a06-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
3. <span data-ttu-id="66a06-110">Impostare il <xref:System.Windows.Forms.Button> del controllo **ColumnSpan** proprietà **2**.</span><span class="sxs-lookup"><span data-stu-id="66a06-110">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **2**.</span></span> <span data-ttu-id="66a06-111">Si noti che il <xref:System.Windows.Forms.Button> controllo si estende la prima e seconda colonna.</span><span class="sxs-lookup"><span data-stu-id="66a06-111">Note that the <xref:System.Windows.Forms.Button> control spans the first and second columns.</span></span>  
  
4. <span data-ttu-id="66a06-112">Impostare il <xref:System.Windows.Forms.Button> del controllo **RowSpan** proprietà **2**.</span><span class="sxs-lookup"><span data-stu-id="66a06-112">Set the <xref:System.Windows.Forms.Button> control's **RowSpan** property to **2**.</span></span> <span data-ttu-id="66a06-113">Si noti che il <xref:System.Windows.Forms.Button> controllo si estende la prima e seconda riga.</span><span class="sxs-lookup"><span data-stu-id="66a06-113">Note that the <xref:System.Windows.Forms.Button> control spans the first and second rows.</span></span>  
  
5. <span data-ttu-id="66a06-114">Impostare il <xref:System.Windows.Forms.Button> del controllo **ColumnSpan** proprietà **1**.</span><span class="sxs-lookup"><span data-stu-id="66a06-114">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **1**.</span></span> <span data-ttu-id="66a06-115">Si noti che il <xref:System.Windows.Forms.Button> controllo si sposta nella prima colonna e si estende la prima e seconda riga.</span><span class="sxs-lookup"><span data-stu-id="66a06-115">Note that the <xref:System.Windows.Forms.Button> control moves into the first column and spans the first and second rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66a06-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66a06-116">See also</span></span>

- [<span data-ttu-id="66a06-117">Controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="66a06-117">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
