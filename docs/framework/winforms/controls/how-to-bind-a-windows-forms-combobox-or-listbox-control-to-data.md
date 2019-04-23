---
title: 'Procedura: Associare un controllo ComboBox o ListBox di Windows Forms ai dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], binding to controls
- list boxes [Windows Forms], data binding
- ComboBox control [Windows Forms], data binding
- data binding [Windows Forms], combo boxes
- ListBox control [Windows Forms], data binding
- combo boxes [Windows Forms], data binding
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- data-bound controls [Windows Forms], Windows Forms
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
ms.openlocfilehash: b869898a20008343b6c6cbe4bc7e399fc86fb232
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59306053"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>Procedura: Associare un controllo ComboBox o ListBox di Windows Forms ai dati
È possibile associare il <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.ListBox> ai dati per eseguire attività come l'esplorazione dei dati in un database, immissione di nuovi dati o la modifica dei dati esistenti.  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>Per associare un controllo ComboBox o ListBox  
  
1. Impostare il `DataSource` proprietà a un oggetto origine dati. Origini dati possibili includono una <xref:System.Windows.Forms.BindingSource> associato a dati, una tabella di dati, una vista dati, un set di dati, un vista dati manager, una matrice o qualsiasi classe che implementa il <xref:System.Collections.IList> interfaccia. Per altre informazioni, vedere [origini dati supportate da Windows Form](../data-sources-supported-by-windows-forms.md).  
  
2. Se esegue il binding a una tabella, impostare il `DisplayMember` proprietà sul nome di una colonna nell'origine dati.  
  
     \- oppure -  
  
     Se si associa a un <xref:System.Collections.IList>, impostare il membro visualizzato su una proprietà pubblica di tipo nell'elenco.  
  
    ```vb  
    Private Sub BindComboBox()  
      ComboBox1.DataSource = DataSet1.Tables("Suppliers")  
      ComboBox1.DisplayMember = "ProductName"  
    End Sub  
    ```  
  
    ```csharp  
    private void BindComboBox()  
    {  
      comboBox1.DataSource = dataSet1.Tables["Suppliers"];  
      comboBox1.DisplayMember = "ProductName";  
    }  
    ```  
  
    > [!NOTE]
    >  Se sono associati a un'origine dati che non implementa il <xref:System.ComponentModel.IBindingList> dell'interfaccia, ad esempio un <xref:System.Collections.ArrayList>, dati del controllo associato non essere aggiornati quando viene aggiornata l'origine dati. Ad esempio, se si dispone di una casella combinata associata a un <xref:System.Collections.ArrayList> e si aggiungono dati al <xref:System.Collections.ArrayList>, i nuovi elementi non verranno visualizzati nella casella combinata. Tuttavia, è possibile forzare la casella combinata per essere aggiornato chiamando il <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> e <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> metodi nell'istanza del <xref:System.Windows.Forms.BindingContext> classe a cui è associato il controllo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Data binding in Windows Form](../windows-forms-data-binding.md)
- [Data binding e Windows Forms](../data-binding-and-windows-forms.md)
- [Controlli Windows Form usati per elencare opzioni](windows-forms-controls-used-to-list-options.md)
