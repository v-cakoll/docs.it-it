---
title: 'Procedura: Raggruppare i controlli RadioButton di Windows Forms in modo che funzionino come set'
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: c785b124d0b9efdbd9a1fa85819031cad3c8857c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117897"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a><span data-ttu-id="0e0b2-102">Procedura: Raggruppare i controlli RadioButton di Windows Forms in modo che funzionino come set</span><span class="sxs-lookup"><span data-stu-id="0e0b2-102">How to: Group Windows Forms RadioButton Controls to Function as a Set</span></span>
<span data-ttu-id="0e0b2-103">Windows Form <xref:System.Windows.Forms.RadioButton> controlli sono progettati per consentire agli utenti una scelta tra due o più impostazioni, di cui solo uno può essere assegnato a una routine o un oggetto.</span><span class="sxs-lookup"><span data-stu-id="0e0b2-103">Windows Forms <xref:System.Windows.Forms.RadioButton> controls are designed to give users a choice among two or more settings, of which only one can be assigned to a procedure or object.</span></span> <span data-ttu-id="0e0b2-104">Ad esempio, un gruppo di <xref:System.Windows.Forms.RadioButton> controlli che visualizzano dei vettori di pacchetto per un ordine, ma solo uno dei vettori verrà usato.</span><span class="sxs-lookup"><span data-stu-id="0e0b2-104">For example, a group of <xref:System.Windows.Forms.RadioButton> controls may display a choice of package carriers for an order, but only one of the carriers will be used.</span></span> <span data-ttu-id="0e0b2-105">Pertanto un solo <xref:System.Windows.Forms.RadioButton> alla volta può essere selezionato, anche se è una parte di un gruppo funzionale.</span><span class="sxs-lookup"><span data-stu-id="0e0b2-105">Therefore only one <xref:System.Windows.Forms.RadioButton> at a time can be selected, even if it is a part of a functional group.</span></span>  
  
 <span data-ttu-id="0e0b2-106">Gruppo di pulsanti di opzione trascinandoli all'interno di un contenitore, ad esempio un <xref:System.Windows.Forms.Panel> (controllo), un <xref:System.Windows.Forms.GroupBox> controllo o un modulo.</span><span class="sxs-lookup"><span data-stu-id="0e0b2-106">You group radio buttons by drawing them inside a container such as a <xref:System.Windows.Forms.Panel> control, a <xref:System.Windows.Forms.GroupBox> control, or a form.</span></span> <span data-ttu-id="0e0b2-107">Tutti i pulsanti di opzione che vengono aggiunti direttamente a un form costituiscono un gruppo.</span><span class="sxs-lookup"><span data-stu-id="0e0b2-107">All radio buttons that are added directly to a form become one group.</span></span> <span data-ttu-id="0e0b2-108">Per aggiungere gruppi separati, è necessario inserirli all'interno di pannelli o caselle di gruppo.</span><span class="sxs-lookup"><span data-stu-id="0e0b2-108">To add separate groups, you must place them inside panels or group boxes.</span></span> <span data-ttu-id="0e0b2-109">Per altre informazioni sui riquadri o caselle di gruppo, vedere [Cenni preliminari sul controllo Panel](panel-control-overview-windows-forms.md) oppure [Cenni preliminari sul controllo GroupBox](groupbox-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0e0b2-109">For more information about panels or group boxes, see [Panel Control Overview](panel-control-overview-windows-forms.md) or [GroupBox Control Overview](groupbox-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a><span data-ttu-id="0e0b2-110">Per raggruppare controlli RadioButton come un set a funzione indipendente da altri gruppi</span><span class="sxs-lookup"><span data-stu-id="0e0b2-110">To group RadioButton controls as a set to function independently of other sets</span></span>  
  
1.  <span data-ttu-id="0e0b2-111">Trascinare un <xref:System.Windows.Forms.GroupBox> o <xref:System.Windows.Forms.Panel> controllare dalle **Windows Forms** scheda il **della casella degli strumenti** nel form.</span><span class="sxs-lookup"><span data-stu-id="0e0b2-111">Drag a <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab on the **Toolbox** onto the form.</span></span>  
  
2.  <span data-ttu-id="0e0b2-112">Disegnare <xref:System.Windows.Forms.RadioButton> ai controlli le <xref:System.Windows.Forms.GroupBox> o <xref:System.Windows.Forms.Panel> controllo.</span><span class="sxs-lookup"><span data-stu-id="0e0b2-112">Draw <xref:System.Windows.Forms.RadioButton> controls on the <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e0b2-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e0b2-113">See also</span></span>

- <xref:System.Windows.Forms.RadioButton>
- [<span data-ttu-id="0e0b2-114">Panoramica del controllo RadioButton</span><span class="sxs-lookup"><span data-stu-id="0e0b2-114">RadioButton Control Overview</span></span>](radiobutton-control-overview-windows-forms.md)
- [<span data-ttu-id="0e0b2-115">Panoramica del controllo Panel</span><span class="sxs-lookup"><span data-stu-id="0e0b2-115">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="0e0b2-116">Panoramica del controllo GroupBox</span><span class="sxs-lookup"><span data-stu-id="0e0b2-116">GroupBox Control Overview</span></span>](groupbox-control-overview-windows-forms.md)
- [<span data-ttu-id="0e0b2-117">Panoramica del controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="0e0b2-117">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="0e0b2-118">Controllo RadioButton</span><span class="sxs-lookup"><span data-stu-id="0e0b2-118">RadioButton Control</span></span>](radiobutton-control-windows-forms.md)
