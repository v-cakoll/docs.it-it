---
title: Associare il controllo ComboBox o ListBox ai dati
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
ms.openlocfilehash: 99d9b53b32d6faae888b134d4ed486980c05a75b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742041"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>Procedura: associare a dati un controllo ComboBox o ListBox Windows Form
È possibile associare il <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.ListBox> ai dati per eseguire attività quali l'esplorazione dei dati in un database, l'immissione di nuovi dati o la modifica di dati esistenti.  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>Per associare un controllo ComboBox o ListBox  
  
1. Impostare la proprietà `DataSource` su un oggetto origine dati. Le origini dati possibili includono un <xref:System.Windows.Forms.BindingSource> associato ai dati, una tabella di dati, una vista dati, un set di dati, un gestore visualizzazione dati, una matrice o qualsiasi classe che implementi l'interfaccia <xref:System.Collections.IList>. Per ulteriori informazioni, vedere [origini dati supportate da Windows Forms](../data-sources-supported-by-windows-forms.md).  
  
2. Se si sta associando a una tabella, impostare la proprietà `DisplayMember` sul nome di una colonna nell'origine dati.  
  
     \- oppure -  
  
     Se si sta associando a una <xref:System.Collections.IList>, impostare il membro di visualizzazione su una proprietà pubblica del tipo nell'elenco.  
  
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
    > Se si è connessi a un'origine dati che non implementa l'interfaccia <xref:System.ComponentModel.IBindingList>, ad esempio un <xref:System.Collections.ArrayList>, i dati del controllo associato non verranno aggiornati al momento dell'aggiornamento dell'origine dati. Ad esempio, se si dispone di una casella combinata associata a una <xref:System.Collections.ArrayList> e i dati vengono aggiunti al <xref:System.Collections.ArrayList>, questi nuovi elementi non verranno visualizzati nella casella combinata. Tuttavia, è possibile forzare l'aggiornamento della casella combinata chiamando il <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> e <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> metodi sull'istanza della classe <xref:System.Windows.Forms.BindingContext> a cui è associato il controllo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Associazione ai dati di Windows Form](../windows-forms-data-binding.md)
- [Data binding e Windows Forms](../data-binding-and-windows-forms.md)
- [Controlli Windows Form usati per elencare opzioni](windows-forms-controls-used-to-list-options.md)
