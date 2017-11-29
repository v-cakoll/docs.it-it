---
title: Formattazione di dati nel controllo DataGridView di Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e716dc74946ac6f18ab82c6834518f0bd6bbea76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Formattazione di dati nel controllo DataGridView di Windows Form
Il <xref:System.Windows.Forms.DataGridView> controllo fornisce la conversione automatica tra i valori delle celle e i tipi di dati che consentono di visualizzare le colonne padre. Le colonne di caselle di testo, ad esempio, visualizzare le rappresentazioni di stringa di data, ora, numero e i valori di enumerazione e convertire i valori stringa immessi dall'utente per i tipi necessari per l'archivio dati.  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>La formattazione con la classe DataGridViewCellStyle  
 Il <xref:System.Windows.Forms.DataGridView> controllo fornisce la formattazione di dati di base di valori di cella tramite la <xref:System.Windows.Forms.DataGridViewCellStyle> classe. È possibile utilizzare il <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> proprietà per formattare i valori date, time, numero ed enumerazione per la lingua predefinita corrente usando gli identificatori di formato descritti nella [formattazione dei tipi di](../../../../docs/standard/base-types/formatting-types.md). È anche possibile formattare i valori per impostazioni cultura specifiche utilizzando la <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> proprietà. Per visualizzare i dati e analizzare i dati immessi dall'utente nel formato specificato, viene utilizzato il formato specificato.  
  
 La <xref:System.Windows.Forms.DataGridViewCellStyle> classe fornisce proprietà di formattazione aggiuntive per ritorno a capo automatico, l'allineamento del testo e la visualizzazione personalizzata di valori null del database. Per altre informazioni, vedere [Procedura: Formattare i dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="formatting-with-the-cellformatting-event"></a>La formattazione con l'evento CellFormatting  
 Se la formattazione di base non soddisfa le proprie esigenze, è possibile fornire dati personalizzati, la formattazione in un gestore per il <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> evento. Il <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> passato al gestore è un <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> proprietà che inizialmente contiene il valore della cella. In genere, questo valore viene convertito automaticamente per il tipo di visualizzazione. Per convertire il valore, impostare il <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> su un valore del tipo di visualizzazione.  
  
> [!NOTE]
>  Se una stringa di formato è attiva per la cella, viene eseguito l'override della modifica del <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> valore della proprietà, a meno che non si imposta la <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> proprietà `true`.  
  
 Il <xref:System.Windows.Forms.DataGridView.CellFormatting> evento è utile anche quando si desidera impostare <xref:System.Windows.Forms.DataGridViewCellStyle> in base ai valori delle proprietà per le singole celle. Per ulteriori informazioni, vedere [procedura: personalizzare la formattazione dei dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
 Se l'analisi predefinita dei valori specificati dall'utente non soddisfa le proprie esigenze, è possibile gestire il <xref:System.Windows.Forms.DataGridView.CellParsing> evento del <xref:System.Windows.Forms.DataGridView> controllo per fornire analisi personalizzata.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 [Visualizzazione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Stili delle celle nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Procedura: Formattare i dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 [Procedura: Formattare dati personalizzati in un controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
