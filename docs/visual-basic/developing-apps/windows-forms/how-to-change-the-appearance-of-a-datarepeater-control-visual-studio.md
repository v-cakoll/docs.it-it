---
title: 'Procedura: modificare l''aspetto di un controllo DataRepeater (Visual Studio)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, customizing
- DataRepeater, changing run time appearance
ms.assetid: 2af6dfce-760b-489e-b863-8da967f315c3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 585ff4c942185f3199fe6e9e47a4ebd9f1f0a478
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-appearance-of-a-datarepeater-control-visual-studio"></a>Procedura: modificare l'aspetto di un controllo DataRepeater (Visual Studio)
È possibile modificare l'aspetto di un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo in fase di progettazione impostando le proprietà o in fase di esecuzione mediante la gestione di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> evento.  
  
 Le proprietà impostate in fase di progettazione quando è selezionata la sezione del modello di elemento del controllo verranno ripetute per ogni <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> in fase di esecuzione. Proprietà relative all'aspetto del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo sarà visibile in fase di esecuzione sono stati rilevati solo se una parte del contenitore viene lasciato (ad esempio, se il <xref:System.Windows.Forms.Control.Padding%2A> è impostata su un valore elevato).  
  
 In fase di esecuzione, le proprietà correlate all'aspetto possono essere impostate in base alle condizioni. In un'applicazione di pianificazione, ad esempio, è possibile modificare il colore di sfondo di un elemento per avvisare gli utenti quando un elemento è scaduto. Nel <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> gestore dell'evento, se si imposta una proprietà in un'istruzione condizionale, ad esempio `If…Then`, è necessario utilizzare anche un `Else` clausola per specificare l'aspetto quando non viene soddisfatta la condizione.  
  
### <a name="to-change-the-appearance-at-design-time"></a>Per modificare l'aspetto in fase di progettazione  
  
1.  In Progettazione Windows Form, selezionare l'area del modello (superiore) dell'elemento di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
2.  Nella finestra Proprietà, selezionare una proprietà e modificare il valore. Proprietà comuni che influiscono sull'aspetto includono <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A>, e <xref:System.Windows.Forms.Control.ForeColor%2A>.  
  
### <a name="to-change-the-appearance-at-run-time"></a>Per modificare l'aspetto in fase di esecuzione  
  
1.  Nell'elenco a discesa Event dell'editor di codice, selezionare **DrawItem**.  
  
2.  Nel <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> gestore, aggiungere il codice per impostare le proprietà:  
  
     [!code-csharp[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="example"></a>Esempio  
 Alcune personalizzazioni comuni per la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo include la visualizzazione delle righe in colori alternati e modificare il colore di un campo in base a una condizione. Nell'esempio seguente viene illustrato come eseguire queste personalizzazioni. In questo esempio si presuppone un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo associato alla tabella Products del database Northwind.  
  
 [!code-vb[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.vb)]
 [!code-csharp[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.cs)]  
  
 Si noti che, per entrambe queste personalizzazioni, è necessario fornire il codice per impostare le proprietà per entrambi i lati della condizione. Se non si specifica il `Else` condizione, verranno visualizzati risultati imprevisti in fase di esecuzione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>  
 [Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [Procedura: Visualizzare i dati associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Procedura: Visualizzare i controlli non associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [Procedura: Visualizzare le intestazioni degli elementi in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
