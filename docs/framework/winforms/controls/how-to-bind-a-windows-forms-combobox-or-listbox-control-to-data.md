---
title: Associare il controllo ComboBox o ListBox ai dati
description: Informazioni su come associare il Windows Forms ComboBox e la casella di riepilogo ai dati per eseguire attività quali l'esplorazione dei dati in un database, l'immissione di nuovi dati o la modifica di dati esistenti.
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
ms.openlocfilehash: 0c07dc90ddc91061c5f34b5a237082cb444e89d9
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324078"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>Procedura: associare a dati un controllo ComboBox o ListBox Windows Form
È possibile associare <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.ListBox> ai dati per eseguire attività quali l'esplorazione dei dati in un database, l'immissione di nuovi dati o la modifica di dati esistenti.  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>Per associare un controllo ComboBox o ListBox  
  
1. Impostare la `DataSource` proprietà su un oggetto origine dati. Le origini dati possibili includono un oggetto <xref:System.Windows.Forms.BindingSource> associato a dati, una tabella di dati, una vista dati, un set di dati, un gestore visualizzazione dati, una matrice o qualsiasi classe che implementa l' <xref:System.Collections.IList> interfaccia. Per ulteriori informazioni, vedere [origini dati supportate da Windows Forms](../data-sources-supported-by-windows-forms.md).  
  
2. Se si sta associando a una tabella, impostare la `DisplayMember` proprietà sul nome di una colonna nell'origine dati.  
  
     \- - oppure -  
  
     Se si sta associando a un <xref:System.Collections.IList> , impostare il membro di visualizzazione su una proprietà pubblica del tipo nell'elenco.  
  
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
    > Se si è connessi a un'origine dati che non implementa l' <xref:System.ComponentModel.IBindingList> interfaccia, ad esempio <xref:System.Collections.ArrayList> , i dati del controllo associato non verranno aggiornati al momento dell'aggiornamento dell'origine dati. Ad esempio, se si dispone di una casella combinata associata a un oggetto <xref:System.Collections.ArrayList> e i dati vengono aggiunti a <xref:System.Collections.ArrayList> , questi nuovi elementi non verranno visualizzati nella casella combinata. Tuttavia, è possibile forzare l'aggiornamento della casella combinata chiamando i <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> metodi e <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> sull'istanza della <xref:System.Windows.Forms.BindingContext> classe a cui è associato il controllo.  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Data binding di Windows Form](../windows-forms-data-binding.md)
- [Associazione dati e Windows Form](../data-binding-and-windows-forms.md)
- [Controlli Windows Form usati per elencare opzioni](windows-forms-controls-used-to-list-options.md)
