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
ms.openlocfilehash: f361526c44f8fbb9ab282fe15ae109b67e8f01dd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922746"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>Procedura: Associare un controllo ComboBox o ListBox di Windows Forms ai dati
È possibile associare e <xref:System.Windows.Forms.ComboBox> <xref:System.Windows.Forms.ListBox> ai dati per eseguire attività quali l'esplorazione dei dati in un database, l'immissione di nuovi dati o la modifica di dati esistenti.  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>Per associare un controllo ComboBox o ListBox  
  
1. Impostare la `DataSource` proprietà su un oggetto origine dati. Le origini dati possibili includono <xref:System.Windows.Forms.BindingSource> un oggetto associato a dati, una tabella di dati, una vista dati, un set di dati, un gestore visualizzazione dati, una matrice o qualsiasi <xref:System.Collections.IList> classe che implementa l'interfaccia. Per ulteriori informazioni, vedere [origini dati supportate da Windows Forms](../data-sources-supported-by-windows-forms.md).  
  
2. Se si sta associando a una tabella, impostare `DisplayMember` la proprietà sul nome di una colonna nell'origine dati.  
  
     \- oppure -  
  
     Se si sta associando a <xref:System.Collections.IList>un, impostare il membro di visualizzazione su una proprietà pubblica del tipo nell'elenco.  
  
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
    > Se si è connessi a un'origine dati che non implementa l' <xref:System.ComponentModel.IBindingList> interfaccia, ad esempio <xref:System.Collections.ArrayList>, i dati del controllo associato non verranno aggiornati al momento dell'aggiornamento dell'origine dati. Ad esempio, se si dispone di una casella combinata associata a <xref:System.Collections.ArrayList> un oggetto e i dati vengono <xref:System.Collections.ArrayList>aggiunti a, questi nuovi elementi non verranno visualizzati nella casella combinata. Tuttavia, è possibile forzare l'aggiornamento della casella combinata chiamando i <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> metodi e <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> <xref:System.Windows.Forms.BindingContext> sull'istanza della classe a cui è associato il controllo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Data binding in Windows Form](../windows-forms-data-binding.md)
- [Data binding e Windows Forms](../data-binding-and-windows-forms.md)
- [Controlli Windows Form usati per elencare opzioni](windows-forms-controls-used-to-list-options.md)
