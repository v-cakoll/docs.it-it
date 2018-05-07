---
title: 'Procedura: garantire la sincronizzazione di più controlli associati alla stessa origine dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding multiple
- controls [Windows Forms], synchronizing with data source
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
ms.openlocfilehash: 5ab7eebd4f4087502f8709e17dde3f3de448c9aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a>Procedura: garantire la sincronizzazione di più controlli associati alla stessa origine dati
Quando si utilizza l'associazione dati in Windows Form, spesso più controlli associati alla stessa origine dati. In alcuni casi, potrebbe essere necessario effettuare altre azioni per assicurarsi che le proprietà dei controlli associate rimangano sincronizzate tra loro e l'origine dati. Questi passaggi sono necessari in due situazioni:  
  
-   Se l'origine dati non implementa <xref:System.ComponentModel.IBindingList>e quindi generare <xref:System.ComponentModel.IBindingList.ListChanged> gli eventi di tipo <xref:System.ComponentModel.ListChangedType.ItemChanged>.  
  
-   Se l'origine dati implementa <xref:System.ComponentModel.IEditableObject>.  
  
 Nel primo caso, è possibile utilizzare un <xref:System.Windows.Forms.BindingSource> per associare l'origine dati ai controlli. Nel secondo caso, utilizzare un <xref:System.Windows.Forms.BindingSource> e gestire il <xref:System.Windows.Forms.BindingSource.BindingComplete> eventi e chiamate <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> sull'oggetto associato <xref:System.Windows.Forms.BindingManagerBase>.  
  
## <a name="example"></a>Esempio  
 Esempio di codice riportato di seguito viene illustrato come associare tre controlli, due controlli casella di testo e un <xref:System.Windows.Forms.DataGridView> controllo, ovvero alla stessa colonna in un <xref:System.Data.DataSet> utilizzando un <xref:System.Windows.Forms.BindingSource> componente. In questo esempio viene illustrato come gestire il <xref:System.Windows.Forms.BindingSource.BindingComplete> evento e verificare che, quando viene modificato il valore di testo di una casella di testo, la casella di testo aggiuntive e <xref:System.Windows.Forms.DataGridView> controllo vengono aggiornate con il valore corretto.  
  
 Nell'esempio viene utilizzato un <xref:System.Windows.Forms.BindingSource> per associare l'origine dati e i controlli. In alternativa, è possibile associare i controlli direttamente all'origine dati e recuperare il <xref:System.Windows.Forms.BindingManagerBase> per l'associazione del form <xref:System.Windows.Forms.Control.BindingContext%2A> e quindi gestire il <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> evento per il <xref:System.Windows.Forms.BindingManagerBase>. Per un esempio di come eseguire questa operazione, vedere la pagina della Guida <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> evento di <xref:System.Windows.Forms.BindingManagerBase>.  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
-   Questo esempio di codice richiede  
  
-   Riferimenti agli assembly <xref:System>, <xref:System.Windows.Forms> e <xref:System.Drawing>.  
  
-   Un form con il <xref:System.Windows.Forms.Form.Load> evento come gestito e una chiamata al `InitializeControlsAndDataSource` metodo dell'esempio del form <xref:System.Windows.Forms.Form.Load> gestore dell'evento.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: condividere dati associati tra form tramite il componente BindingSource](../../../docs/framework/winforms/controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 [Notifica delle modifiche nel data binding dei Windows Form](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [Interfacce correlate al data binding](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 [Data binding in Windows Form](../../../docs/framework/winforms/windows-forms-data-binding.md)
