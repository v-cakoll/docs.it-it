---
title: 'Procedura: raggruppare controlli RadioButton Windows Form in modo che funzionino come set'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c92048374941f735568bcd758ed475eba78b81e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a><span data-ttu-id="ab2b7-102">Procedura: raggruppare controlli RadioButton Windows Form in modo che funzionino come set</span><span class="sxs-lookup"><span data-stu-id="ab2b7-102">How to: Group Windows Forms RadioButton Controls to Function as a Set</span></span>
<span data-ttu-id="ab2b7-103">Windows Form <xref:System.Windows.Forms.RadioButton> i controlli sono progettati per consentire agli utenti una scelta tra due o più impostazioni di cui solo uno può essere assegnato a una routine o un oggetto.</span><span class="sxs-lookup"><span data-stu-id="ab2b7-103">Windows Forms <xref:System.Windows.Forms.RadioButton> controls are designed to give users a choice among two or more settings, of which only one can be assigned to a procedure or object.</span></span> <span data-ttu-id="ab2b7-104">Ad esempio, un gruppo di <xref:System.Windows.Forms.RadioButton> controlli che visualizzano dei vettori di pacchetto per un ordine, ma solo uno dei vettori verrà utilizzato.</span><span class="sxs-lookup"><span data-stu-id="ab2b7-104">For example, a group of <xref:System.Windows.Forms.RadioButton> controls may display a choice of package carriers for an order, but only one of the carriers will be used.</span></span> <span data-ttu-id="ab2b7-105">Pertanto un solo <xref:System.Windows.Forms.RadioButton> alla volta può essere selezionato, anche se fa parte di un gruppo funzionale.</span><span class="sxs-lookup"><span data-stu-id="ab2b7-105">Therefore only one <xref:System.Windows.Forms.RadioButton> at a time can be selected, even if it is a part of a functional group.</span></span>  
  
 <span data-ttu-id="ab2b7-106">Gruppo di pulsanti di opzione trascinandoli all'interno di un contenitore, ad esempio un <xref:System.Windows.Forms.Panel> (controllo), un <xref:System.Windows.Forms.GroupBox> controllo o un form.</span><span class="sxs-lookup"><span data-stu-id="ab2b7-106">You group radio buttons by drawing them inside a container such as a <xref:System.Windows.Forms.Panel> control, a <xref:System.Windows.Forms.GroupBox> control, or a form.</span></span> <span data-ttu-id="ab2b7-107">Tutti i pulsanti di opzione che vengono aggiunti direttamente a un form costituiscono un gruppo.</span><span class="sxs-lookup"><span data-stu-id="ab2b7-107">All radio buttons that are added directly to a form become one group.</span></span> <span data-ttu-id="ab2b7-108">Per aggiungere gruppi separati, è necessario inserirli all'interno di pannelli o caselle di gruppo.</span><span class="sxs-lookup"><span data-stu-id="ab2b7-108">To add separate groups, you must place them inside panels or group boxes.</span></span> <span data-ttu-id="ab2b7-109">Per ulteriori informazioni su pannelli o caselle di gruppo, vedere [Cenni preliminari sul controllo Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md) o [Cenni preliminari sul controllo GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ab2b7-109">For more information about panels or group boxes, see [Panel Control Overview](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md) or [GroupBox Control Overview](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a><span data-ttu-id="ab2b7-110">Per raggruppare controlli RadioButton come impostato in modo indipendente da altri set (funzione)</span><span class="sxs-lookup"><span data-stu-id="ab2b7-110">To group RadioButton controls as a set to function independently of other sets</span></span>  
  
1.  <span data-ttu-id="ab2b7-111">Trascinare un <xref:System.Windows.Forms.GroupBox> o <xref:System.Windows.Forms.Panel> controllo il **Windows Form** scheda la **della casella degli strumenti** nel form.</span><span class="sxs-lookup"><span data-stu-id="ab2b7-111">Drag a <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab on the **Toolbox** onto the form.</span></span>  
  
2.  <span data-ttu-id="ab2b7-112">Disegnare <xref:System.Windows.Forms.RadioButton> ai controlli di <xref:System.Windows.Forms.GroupBox> o <xref:System.Windows.Forms.Panel> controllo.</span><span class="sxs-lookup"><span data-stu-id="ab2b7-112">Draw <xref:System.Windows.Forms.RadioButton> controls on the <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab2b7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab2b7-113">See Also</span></span>  
 <xref:System.Windows.Forms.RadioButton>  
 [<span data-ttu-id="ab2b7-114">Panoramica sul controllo RadioButton</span><span class="sxs-lookup"><span data-stu-id="ab2b7-114">RadioButton Control Overview</span></span>](../../../../docs/framework/winforms/controls/radiobutton-control-overview-windows-forms.md)  
 [<span data-ttu-id="ab2b7-115">Panoramica sul controllo Panel</span><span class="sxs-lookup"><span data-stu-id="ab2b7-115">Panel Control Overview</span></span>](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [<span data-ttu-id="ab2b7-116">Panoramica sul controllo GroupBox</span><span class="sxs-lookup"><span data-stu-id="ab2b7-116">GroupBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="ab2b7-117">Panoramica sul controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="ab2b7-117">CheckBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="ab2b7-118">Controllo RadioButton</span><span class="sxs-lookup"><span data-stu-id="ab2b7-118">RadioButton Control</span></span>](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)
