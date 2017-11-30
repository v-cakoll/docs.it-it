---
title: 'Procedura: modificare il layout di un controllo DataRepeater (Visual Studio)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, changing layout style
- DataRepeater, changing orientation
ms.assetid: 33aa8fd5-ac63-4bd0-ba13-8c2ab17e7824
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 94c5f8f5e83578ca0a82b479ef5ef359738df5f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-layout-of-a-datarepeater-control-visual-studio"></a>Procedura: modificare il layout di un controllo DataRepeater (Visual Studio)
Il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo può essere visualizzato in verticale (elementi di scorrimento verticale) o orizzontale (elementi di scorrimento orizzontale) orientamento. È possibile modificare l'orientamento in fase di progettazione o in fase di esecuzione modificando il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> proprietà. Se si modifica il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> proprietà in fase di esecuzione, è anche possibile ridimensionare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> e riposizionare i controlli figlio.  
  
> [!NOTE]
>  Se si riposizionano controlli su di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> in fase di esecuzione, sarà necessario chiamare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> e <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> metodi all'inizio e alla fine del blocco di codice che riposiziona i controlli.  
  
### <a name="to-change-the-layout-at-design-time"></a>Per modificare il layout in fase di progettazione  
  
1.  In Progettazione Windows Form, selezionare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
    > [!NOTE]
    >  È necessario selezionare il bordo esterno del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo facendo clic nell'area inferiore del controllo, non nella parte superiore <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> area.  
  
2.  Nella finestra Proprietà impostare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> una proprietà <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> o <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>.  
  
### <a name="to-change-the-layout-at-run-time"></a>Per modificare il layout in fase di esecuzione  
  
1.  Aggiungere il codice seguente di un pulsante o menu `Click` gestore eventi:  
  
     [!code-csharp[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.vb)]  
  
2.  Nella maggior parte dei casi, è possibile aggiungere codice analogo a quanto illustrato nella sezione di esempio per ridimensionare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> e ridisporre i controlli per adattarli al nuovo orientamento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come rispondere al <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> evento in un gestore eventi. In questo esempio si suppone una <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo denominato `DataRepeater1` in un form e che il relativo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> contengono due <xref:System.Windows.Forms.TextBox> controlli denominati `TextBox1` e `TextBox2`.  
  
 [!code-csharp[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>  
 [Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [Procedura: Modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
