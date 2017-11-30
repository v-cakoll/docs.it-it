---
title: 'Procedura: specificare i valori predefiniti per le nuove righe nel controllo DataGridView di Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], default values for new rows
- DataGridView control [Windows Forms], data entry
- rows [Windows Forms], specifying default values
- DataGridView control [Windows Forms], default values for new rows
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 577d5c3bc4b4afef845cd51b62b7d48fcc9d4a7e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a>Procedura: specificare i valori predefiniti per le nuove righe nel controllo DataGridView di Windows Form
È possibile rendere più semplice immissione dei dati quando l'applicazione predefinita inserisce i valori per le righe appena aggiunte. Con il <xref:System.Windows.Forms.DataGridView> (classe), è possibile inserire i valori predefiniti con il <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> evento. Questo evento viene generato quando l'utente immette la riga per nuovi record. Quando il codice gestisce questo evento, è possibile popolare desiderate celle con valori di propria scelta.  
  
 Esempio di codice riportato di seguito viene illustrato come specificare i valori predefiniti per le nuove righe utilizzando la <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> evento.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
-   Oggetto `NewCustomerId` funzione per la generazione univoco `CustomerID` valori.  
  
-   Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 [Immissione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [Uso della riga per i nuovi record del controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
