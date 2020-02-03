---
title: Raggruppare i controlli RadioButton per funzionare come set
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: c4b37c84bf0f93837b91c743c7681d39fd83a659
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732946"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a><span data-ttu-id="88874-102">Procedura: raggruppare controlli RadioButton Windows Form in modo che funzionino come set</span><span class="sxs-lookup"><span data-stu-id="88874-102">How to: Group Windows Forms RadioButton Controls to Function as a Set</span></span>
<span data-ttu-id="88874-103">Windows Forms controlli <xref:System.Windows.Forms.RadioButton> sono progettati per fornire agli utenti una scelta tra due o più impostazioni, di cui solo una può essere assegnata a una procedura o a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="88874-103">Windows Forms <xref:System.Windows.Forms.RadioButton> controls are designed to give users a choice among two or more settings, of which only one can be assigned to a procedure or object.</span></span> <span data-ttu-id="88874-104">Ad esempio, un gruppo di controlli di <xref:System.Windows.Forms.RadioButton> può visualizzare una scelta di gestori di pacchetti per un ordine, ma solo uno dei vettori verrà usato.</span><span class="sxs-lookup"><span data-stu-id="88874-104">For example, a group of <xref:System.Windows.Forms.RadioButton> controls may display a choice of package carriers for an order, but only one of the carriers will be used.</span></span> <span data-ttu-id="88874-105">È pertanto possibile selezionare un solo <xref:System.Windows.Forms.RadioButton> alla volta, anche se fa parte di un gruppo funzionale.</span><span class="sxs-lookup"><span data-stu-id="88874-105">Therefore only one <xref:System.Windows.Forms.RadioButton> at a time can be selected, even if it is a part of a functional group.</span></span>  
  
 <span data-ttu-id="88874-106">Per raggruppare i pulsanti di opzione, è possibile disegnarli all'interno di un contenitore, ad esempio un controllo <xref:System.Windows.Forms.Panel>, un controllo <xref:System.Windows.Forms.GroupBox> o un form.</span><span class="sxs-lookup"><span data-stu-id="88874-106">You group radio buttons by drawing them inside a container such as a <xref:System.Windows.Forms.Panel> control, a <xref:System.Windows.Forms.GroupBox> control, or a form.</span></span> <span data-ttu-id="88874-107">Tutti i pulsanti di opzione aggiunti direttamente a un modulo diventano un gruppo.</span><span class="sxs-lookup"><span data-stu-id="88874-107">All radio buttons that are added directly to a form become one group.</span></span> <span data-ttu-id="88874-108">Per aggiungere gruppi distinti, è necessario inserirli nei pannelli o nelle caselle di gruppo.</span><span class="sxs-lookup"><span data-stu-id="88874-108">To add separate groups, you must place them inside panels or group boxes.</span></span> <span data-ttu-id="88874-109">Per ulteriori informazioni sui pannelli o sulle caselle di gruppo, vedere [Cenni preliminari sul controllo Panel](panel-control-overview-windows-forms.md) o [Cenni preliminari sul controllo GroupBox](groupbox-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="88874-109">For more information about panels or group boxes, see [Panel Control Overview](panel-control-overview-windows-forms.md) or [GroupBox Control Overview](groupbox-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a><span data-ttu-id="88874-110">Per raggruppare i controlli RadioButton come set per funzionare indipendentemente da altri set</span><span class="sxs-lookup"><span data-stu-id="88874-110">To group RadioButton controls as a set to function independently of other sets</span></span>  
  
1. <span data-ttu-id="88874-111">Trascinare un controllo <xref:System.Windows.Forms.GroupBox> o <xref:System.Windows.Forms.Panel> dalla scheda **Windows Forms** della **casella degli strumenti** nel form.</span><span class="sxs-lookup"><span data-stu-id="88874-111">Drag a <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab on the **Toolbox** onto the form.</span></span>  
  
2. <span data-ttu-id="88874-112">Consente di creare <xref:System.Windows.Forms.RadioButton> controlli sul controllo <xref:System.Windows.Forms.GroupBox> o <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="88874-112">Draw <xref:System.Windows.Forms.RadioButton> controls on the <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88874-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88874-113">See also</span></span>

- <xref:System.Windows.Forms.RadioButton>
- [<span data-ttu-id="88874-114">Panoramica sul controllo RadioButton</span><span class="sxs-lookup"><span data-stu-id="88874-114">RadioButton Control Overview</span></span>](radiobutton-control-overview-windows-forms.md)
- [<span data-ttu-id="88874-115">Panoramica sul controllo Panel</span><span class="sxs-lookup"><span data-stu-id="88874-115">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="88874-116">Panoramica sul controllo GroupBox</span><span class="sxs-lookup"><span data-stu-id="88874-116">GroupBox Control Overview</span></span>](groupbox-control-overview-windows-forms.md)
- [<span data-ttu-id="88874-117">Panoramica sul controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="88874-117">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="88874-118">Controllo RadioButton</span><span class="sxs-lookup"><span data-stu-id="88874-118">RadioButton Control</span></span>](radiobutton-control-windows-forms.md)
