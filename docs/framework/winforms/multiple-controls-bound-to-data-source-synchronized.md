---
title: 'Procedura: Garantire la sincronizzazione di più controlli associati alla stessa origine dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding multiple
- controls [Windows Forms], synchronizing with data source
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
ms.openlocfilehash: 8a39c50bfc452c807a18a9bf0a65e56cb75d20aa
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64655634"
---
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a>Procedura: Garantire la sincronizzazione di più controlli associati alla stessa origine dati
Quando si lavora con data binding in Windows Form, spesso più controlli associati alla stessa origine dati. In alcuni casi, è necessario eseguire passaggi aggiuntivi per garantire che le proprietà associate dei controlli restino sincronizzate tra loro e l'origine dati. Questi passaggi sono necessari in due situazioni:  
  
- Se l'origine dati non implementa <xref:System.ComponentModel.IBindingList>e quindi generare <xref:System.ComponentModel.IBindingList.ListChanged> eventi di tipo <xref:System.ComponentModel.ListChangedType.ItemChanged>.  
  
- Se l'origine dati implementa <xref:System.ComponentModel.IEditableObject>.  
  
 Nel primo caso, è possibile usare un <xref:System.Windows.Forms.BindingSource> per associare l'origine dati ai controlli. Nel secondo caso, si utilizza un <xref:System.Windows.Forms.BindingSource> e gestire i <xref:System.Windows.Forms.BindingSource.BindingComplete> eventi e chiamate <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> sull'oggetto associato <xref:System.Windows.Forms.BindingManagerBase>.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come associare tre controlli: due controlli casella di testo e un <xref:System.Windows.Forms.DataGridView> controllo, ovvero alla stessa colonna in una <xref:System.Data.DataSet> usando un <xref:System.Windows.Forms.BindingSource> componente. In questo esempio viene illustrato come gestire le <xref:System.Windows.Forms.BindingSource.BindingComplete> eventi e verificare che, quando viene modificato il valore di testo di una casella di testo, la casella di testo aggiuntive e <xref:System.Windows.Forms.DataGridView> controllo vengono aggiornate con il valore corretto.  
  
 Nell'esempio viene usato un <xref:System.Windows.Forms.BindingSource> per associare l'origine dati e i controlli. In alternativa, è possibile associare i controlli direttamente all'origine dati e recuperare il <xref:System.Windows.Forms.BindingManagerBase> per l'associazione del form <xref:System.Windows.Forms.Control.BindingContext%2A> e quindi gestire le <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> evento per il <xref:System.Windows.Forms.BindingManagerBase>. Per un esempio di come eseguire questa operazione, vedere la pagina della Guida <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> eventi di <xref:System.Windows.Forms.BindingManagerBase>.  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- Questo esempio di codice necessaria  
  
- Riferimenti agli assembly <xref:System>, <xref:System.Windows.Forms> e <xref:System.Drawing>.  
  
- Un form con il <xref:System.Windows.Forms.Form.Load> evento come gestito e una chiamata per il `InitializeControlsAndDataSource` metodo nell'esempio del form <xref:System.Windows.Forms.Form.Load> gestore dell'evento.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Condividere dati associati tra form tramite il componente BindingSource](./controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)
- [Notifica delle modifiche nel data binding dei Windows Form](change-notification-in-windows-forms-data-binding.md)
- [Interfacce correlate al data binding](interfaces-related-to-data-binding.md)
- [Data binding in Windows Form](windows-forms-data-binding.md)
