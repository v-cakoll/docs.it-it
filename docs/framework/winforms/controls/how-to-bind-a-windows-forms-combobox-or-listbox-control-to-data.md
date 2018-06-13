---
title: 'Procedura: associare a dati un controllo ComboBox o ListBox Windows Form'
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
ms.openlocfilehash: 270ed1c9fab4013df72b715ce8b074d287616713
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530133"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>Procedura: associare a dati un controllo ComboBox o ListBox Windows Form
È possibile associare il <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.ListBox> ai dati per eseguire attività quali l'esplorazione di dati in un database, immettere nuovi dati o la modifica dei dati esistenti.  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>Per associare un controllo ComboBox o ListBox  
  
1.  Impostare il `DataSource` proprietà a un oggetto origine dati. Origini dati possibili includono un <xref:System.Windows.Forms.BindingSource> associato a dati, una tabella di dati, una visualizzazione dati, un set di dati, un visualizzazione dati manager, una matrice o qualsiasi classe che implementa il <xref:System.Collections.IList> interfaccia. Per ulteriori informazioni, vedere [origini dati supportate da Windows Form](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md).  
  
2.  Se si desidera associare a una tabella, impostare il `DisplayMember` proprietà sul nome di una colonna nell'origine dati.  
  
     \- oppure -  
  
     Se si desidera associare a un <xref:System.Collections.IList>, impostare il membro visualizzato su una proprietà pubblica di tipo nell'elenco.  
  
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
    >  Se si è associati a un'origine dati che non implementa il <xref:System.ComponentModel.IBindingList> interfaccia, ad esempio un <xref:System.Collections.ArrayList>, i dati del controllo associato non essere aggiornati quando viene aggiornata l'origine dati. Ad esempio, se dispone di una casella combinata associata a un <xref:System.Collections.ArrayList> e si aggiungono dati al <xref:System.Collections.ArrayList>, questi nuovi elementi non verranno visualizzati nella casella combinata. Tuttavia, è possibile forzare la casella combinata per essere aggiornato chiamando il <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> e <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> metodi nell'istanza del <xref:System.Windows.Forms.BindingContext> classe a cui è associato il controllo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 [Data binding in Windows Form](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Data binding e Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [Controlli Windows Form usati per elencare opzioni](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
