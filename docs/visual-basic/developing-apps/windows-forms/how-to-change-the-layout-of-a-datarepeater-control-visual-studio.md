---
title: 'Procedura: Modificare il Layout di un controllo DataRepeater (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, changing layout style
- DataRepeater, changing orientation
ms.assetid: 33aa8fd5-ac63-4bd0-ba13-8c2ab17e7824
ms.openlocfilehash: 3389daa6383444b48faab4c5383b281e44349bce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625601"
---
# <a name="how-to-change-the-layout-of-a-datarepeater-control-visual-studio"></a><span data-ttu-id="5ec26-102">Procedura: Modificare il Layout di un controllo DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="5ec26-102">How to: Change the Layout of a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="5ec26-103">Il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo può essere visualizzato in verticale (elementi di scorrimento verticale) o (elementi orizzontalmente scorrimento) orizzontale orientamento.</span><span class="sxs-lookup"><span data-stu-id="5ec26-103">The <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control can be displayed in either a vertical (items scroll vertically) or horizontal (items scroll horizontally) orientation.</span></span> <span data-ttu-id="5ec26-104">È possibile modificare l'orientamento in fase di progettazione o in fase di esecuzione modificando il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="5ec26-104">You can change the orientation at design time or at run time by changing the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property.</span></span> <span data-ttu-id="5ec26-105">Se si modifica il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> proprietà in fase di esecuzione, è anche possibile ridimensionare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> e riposizionare i controlli figlio.</span><span class="sxs-lookup"><span data-stu-id="5ec26-105">If you change the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property at run time, you may also want to resize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> and reposition the child controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ec26-106">Se si riposiziona i controlli sul <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> in fase di esecuzione, si dovrà chiamare la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> e <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> metodi all'inizio e alla fine del blocco di codice che riposiziona i controlli.</span><span class="sxs-lookup"><span data-stu-id="5ec26-106">If you reposition controls on the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> at run time, you will need to call the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> and <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> methods at the beginning and end of the code block that repositions the controls.</span></span>  
  
### <a name="to-change-the-layout-at-design-time"></a><span data-ttu-id="5ec26-107">Per modificare il layout in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="5ec26-107">To change the layout at design time</span></span>  
  
1.  <span data-ttu-id="5ec26-108">Nella finestra di progettazione Windows Form, selezionare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.</span><span class="sxs-lookup"><span data-stu-id="5ec26-108">In the Windows Forms Designer, select the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5ec26-109">È necessario selezionare il bordo esterno del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo facendo clic nell'area inferiore del controllo, non in alto <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> area.</span><span class="sxs-lookup"><span data-stu-id="5ec26-109">You must select the outer border of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control by clicking in the lower region of the control, not in the upper <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> region.</span></span>  
  
2.  <span data-ttu-id="5ec26-110">Nella finestra Proprietà impostare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> proprietà a una delle due <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> o <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>.</span><span class="sxs-lookup"><span data-stu-id="5ec26-110">In the Properties window, set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property to either <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> or <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>.</span></span>  
  
### <a name="to-change-the-layout-at-run-time"></a><span data-ttu-id="5ec26-111">Per modificare il layout in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="5ec26-111">To change the layout at run time</span></span>  
  
1.  <span data-ttu-id="5ec26-112">Aggiungere il codice seguente a un pulsante o menu `Click` gestore dell'evento:</span><span class="sxs-lookup"><span data-stu-id="5ec26-112">Add the following code to a button or menu `Click` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.vb)]  
  
2.  <span data-ttu-id="5ec26-113">Nella maggior parte dei casi, si dovranno aggiungere codice simile a quello illustrato nella sezione di esempio per ridimensionare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> e ridisporre i controlli per adattarli al nuovo orientamento.</span><span class="sxs-lookup"><span data-stu-id="5ec26-113">In most cases, you will want to add code similar to that shown in the Example section to resize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> and rearrange controls to fit the new orientation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ec26-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="5ec26-114">Example</span></span>  
 <span data-ttu-id="5ec26-115">Nell'esempio seguente illustra come rispondere al <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> evento in un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="5ec26-115">The following example shows how to respond to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> event in an event handler.</span></span> <span data-ttu-id="5ec26-116">In questo esempio è necessario disporre una <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo denominato `DataRepeater1` in un form e che relativo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> contengono due <xref:System.Windows.Forms.TextBox> controlli denominati `TextBox1` e `TextBox2`.</span><span class="sxs-lookup"><span data-stu-id="5ec26-116">This example requires that you have a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control named `DataRepeater1` on a form and that its <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> contain two <xref:System.Windows.Forms.TextBox> controls named `TextBox1` and `TextBox2`.</span></span>  
  
 [!code-csharp[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5ec26-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ec26-117">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>
- [<span data-ttu-id="5ec26-118">Introduzione al controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="5ec26-118">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="5ec26-119">Risoluzione dei problemi relativi al controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="5ec26-119">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="5ec26-120">Procedura: Modificare l'aspetto di un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="5ec26-120">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
