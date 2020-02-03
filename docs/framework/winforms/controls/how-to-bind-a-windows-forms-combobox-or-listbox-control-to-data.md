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
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="014a1-102">Procedura: associare a dati un controllo ComboBox o ListBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="014a1-102">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="014a1-103">È possibile associare il <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.ListBox> ai dati per eseguire attività quali l'esplorazione dei dati in un database, l'immissione di nuovi dati o la modifica di dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="014a1-103">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="014a1-104">Per associare un controllo ComboBox o ListBox</span><span class="sxs-lookup"><span data-stu-id="014a1-104">To bind a ComboBox or ListBox control</span></span>  
  
1. <span data-ttu-id="014a1-105">Impostare la proprietà `DataSource` su un oggetto origine dati.</span><span class="sxs-lookup"><span data-stu-id="014a1-105">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="014a1-106">Le origini dati possibili includono un <xref:System.Windows.Forms.BindingSource> associato ai dati, una tabella di dati, una vista dati, un set di dati, un gestore visualizzazione dati, una matrice o qualsiasi classe che implementi l'interfaccia <xref:System.Collections.IList>.</span><span class="sxs-lookup"><span data-stu-id="014a1-106">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="014a1-107">Per ulteriori informazioni, vedere [origini dati supportate da Windows Forms](../data-sources-supported-by-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="014a1-107">For more information, see [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="014a1-108">Se si sta associando a una tabella, impostare la proprietà `DisplayMember` sul nome di una colonna nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="014a1-108">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="014a1-109">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="014a1-109">\- or -</span></span>  
  
     <span data-ttu-id="014a1-110">Se si sta associando a una <xref:System.Collections.IList>, impostare il membro di visualizzazione su una proprietà pubblica del tipo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="014a1-110">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
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
    > <span data-ttu-id="014a1-111">Se si è connessi a un'origine dati che non implementa l'interfaccia <xref:System.ComponentModel.IBindingList>, ad esempio un <xref:System.Collections.ArrayList>, i dati del controllo associato non verranno aggiornati al momento dell'aggiornamento dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="014a1-111">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="014a1-112">Ad esempio, se si dispone di una casella combinata associata a una <xref:System.Collections.ArrayList> e i dati vengono aggiunti al <xref:System.Collections.ArrayList>, questi nuovi elementi non verranno visualizzati nella casella combinata.</span><span class="sxs-lookup"><span data-stu-id="014a1-112">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="014a1-113">Tuttavia, è possibile forzare l'aggiornamento della casella combinata chiamando il <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> e <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> metodi sull'istanza della classe <xref:System.Windows.Forms.BindingContext> a cui è associato il controllo.</span><span class="sxs-lookup"><span data-stu-id="014a1-113">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="014a1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="014a1-114">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="014a1-115">Associazione ai dati di Windows Form</span><span class="sxs-lookup"><span data-stu-id="014a1-115">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="014a1-116">Data binding e Windows Forms</span><span class="sxs-lookup"><span data-stu-id="014a1-116">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="014a1-117">Controlli Windows Form usati per elencare opzioni</span><span class="sxs-lookup"><span data-stu-id="014a1-117">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
