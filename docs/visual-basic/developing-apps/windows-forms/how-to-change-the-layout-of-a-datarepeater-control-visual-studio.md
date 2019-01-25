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
# <a name="how-to-change-the-layout-of-a-datarepeater-control-visual-studio"></a>Procedura: Modificare il Layout di un controllo DataRepeater (Visual Studio)
Il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo può essere visualizzato in verticale (elementi di scorrimento verticale) o (elementi orizzontalmente scorrimento) orizzontale orientamento. È possibile modificare l'orientamento in fase di progettazione o in fase di esecuzione modificando il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> proprietà. Se si modifica il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> proprietà in fase di esecuzione, è anche possibile ridimensionare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> e riposizionare i controlli figlio.  
  
> [!NOTE]
>  Se si riposiziona i controlli sul <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> in fase di esecuzione, si dovrà chiamare la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> e <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> metodi all'inizio e alla fine del blocco di codice che riposiziona i controlli.  
  
### <a name="to-change-the-layout-at-design-time"></a>Per modificare il layout in fase di progettazione  
  
1.  Nella finestra di progettazione Windows Form, selezionare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
    > [!NOTE]
    >  È necessario selezionare il bordo esterno del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo facendo clic nell'area inferiore del controllo, non in alto <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> area.  
  
2.  Nella finestra Proprietà impostare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> proprietà a una delle due <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> o <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>.  
  
### <a name="to-change-the-layout-at-run-time"></a>Per modificare il layout in fase di esecuzione  
  
1.  Aggiungere il codice seguente a un pulsante o menu `Click` gestore dell'evento:  
  
     [!code-csharp[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.vb)]  
  
2.  Nella maggior parte dei casi, si dovranno aggiungere codice simile a quello illustrato nella sezione di esempio per ridimensionare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> e ridisporre i controlli per adattarli al nuovo orientamento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente illustra come rispondere al <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> evento in un gestore eventi. In questo esempio è necessario disporre una <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo denominato `DataRepeater1` in un form e che relativo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> contengono due <xref:System.Windows.Forms.TextBox> controlli denominati `TextBox1` e `TextBox2`.  
  
 [!code-csharp[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.vb)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>
- [Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [Risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [Procedura: Modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
