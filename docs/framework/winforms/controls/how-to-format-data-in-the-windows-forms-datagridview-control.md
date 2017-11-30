---
title: 'Procedura: formattare i dati nel controllo DataGridView di Windows Form'
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
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in DataGridView control
- data grids [Windows Forms], enabling wordwrap
- currency values [Windows Forms], formatting in data grids
- data grids [Windows Forms], currency values
- data grids [Windows Forms], formatting data
- data grids [Windows Forms], text alignment
- data grids [Windows Forms], date values
- cells [Windows Forms], text alignment
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 49d5172b2638a7ac3a6a7bf005932ba4b3f9aba3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a>Procedura: formattare i dati nel controllo DataGridView di Windows Form
Le procedure seguenti illustrano la formattazione di base di valori di cella utilizzando il <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> proprietà di un <xref:System.Windows.Forms.DataGridView> controllo e di colonne specifiche in un controllo. Per informazioni sulla formattazione di dati avanzati, vedere [procedura: personalizzare la formattazione dei dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
### <a name="to-format-currency-and-date-values"></a>Per la formattazione della valuta e i valori di data  
  
-   Impostare la proprietà <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> di un oggetto <xref:System.Windows.Forms.DataGridViewCellStyle>. Esempio di codice seguente imposta il formato per colonne specifiche utilizzando la <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> proprietà delle colonne. I valori di `UnitPrice` colonna vengono visualizzate in formato di valuta specifico delle impostazioni cultura correnti, con i valori negativi racchiusi tra parentesi. I valori di `ShipDate` colonna vengono visualizzati nel formato data breve specifiche delle impostazioni cultura correnti. Per ulteriori informazioni su <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> valori, vedere [formattazione dei tipi di](../../../../docs/standard/base-types/formatting-types.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a>Per personalizzare la visualizzazione di valori null del database  
  
-   Impostare la proprietà <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> di un oggetto <xref:System.Windows.Forms.DataGridViewCellStyle>. Nell'esempio di codice viene illustrato come utilizzare il <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> proprietà da non visualizzare "Nessuna voce" in tutte le celle contenenti valori uguali a <xref:System.DBNull.Value?displayProperty=nameWithType>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a>Per consentire di ritorno a capo automatico nelle celle basate su testo  
  
-   Impostare il <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> proprietà di un <xref:System.Windows.Forms.DataGridViewCellStyle> a uno del <xref:System.Windows.Forms.DataGridViewTriState> valori di enumerazione. Nell'esempio di codice viene illustrato come utilizzare il <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> proprietà per impostare la modalità di disposizione per l'intero controllo.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a>Per specificare l'allineamento del testo delle celle DataGridView  
  
-   Impostare il <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> proprietà di un <xref:System.Windows.Forms.DataGridViewCellStyle> a uno del <xref:System.Windows.Forms.DataGridViewContentAlignment> valori di enumerazione. Esempio di codice seguente imposta l'allineamento di una colonna specifica utilizzando il <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> proprietà della colonna.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Gli esempi presentano i requisiti seguenti:  
  
-   Oggetto <xref:System.Windows.Forms.DataGridView> controllo denominato `dataGridView1` che contiene una colonna denominata `UnitPrice`, una colonna denominata `ShipDate`e una colonna denominata `CustomerName`.  
  
-   Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Per ottenere la massima scalabilità, è opportuno condividere <xref:System.Windows.Forms.DataGridViewCellStyle> oggetti tra più righe, colonne o celle che usano lo stesso stile anziché impostare separatamente le proprietà di stile per ogni elemento. Per ulteriori informazioni, vedere [procedure consigliate per ridimensionare il controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 [Formattazione e stile di base nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [Stili delle celle nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Formattazione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)  
 [Procedura: Formattare dati personalizzati in un controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 [Formattazione di tipi](../../../../docs/standard/base-types/formatting-types.md)
