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
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="c969f-102">Procedura: Associare un controllo ComboBox o ListBox di Windows Forms ai dati</span><span class="sxs-lookup"><span data-stu-id="c969f-102">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="c969f-103">È possibile associare e <xref:System.Windows.Forms.ComboBox> <xref:System.Windows.Forms.ListBox> ai dati per eseguire attività quali l'esplorazione dei dati in un database, l'immissione di nuovi dati o la modifica di dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="c969f-103">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="c969f-104">Per associare un controllo ComboBox o ListBox</span><span class="sxs-lookup"><span data-stu-id="c969f-104">To bind a ComboBox or ListBox control</span></span>  
  
1. <span data-ttu-id="c969f-105">Impostare la `DataSource` proprietà su un oggetto origine dati.</span><span class="sxs-lookup"><span data-stu-id="c969f-105">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="c969f-106">Le origini dati possibili includono <xref:System.Windows.Forms.BindingSource> un oggetto associato a dati, una tabella di dati, una vista dati, un set di dati, un gestore visualizzazione dati, una matrice o qualsiasi <xref:System.Collections.IList> classe che implementa l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c969f-106">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="c969f-107">Per ulteriori informazioni, vedere [origini dati supportate da Windows Forms](../data-sources-supported-by-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c969f-107">For more information, see [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="c969f-108">Se si sta associando a una tabella, impostare `DisplayMember` la proprietà sul nome di una colonna nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="c969f-108">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="c969f-109">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="c969f-109">\- or -</span></span>  
  
     <span data-ttu-id="c969f-110">Se si sta associando a <xref:System.Collections.IList>un, impostare il membro di visualizzazione su una proprietà pubblica del tipo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c969f-110">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
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
    > <span data-ttu-id="c969f-111">Se si è connessi a un'origine dati che non implementa l' <xref:System.ComponentModel.IBindingList> interfaccia, ad esempio <xref:System.Collections.ArrayList>, i dati del controllo associato non verranno aggiornati al momento dell'aggiornamento dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="c969f-111">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="c969f-112">Ad esempio, se si dispone di una casella combinata associata a <xref:System.Collections.ArrayList> un oggetto e i dati vengono <xref:System.Collections.ArrayList>aggiunti a, questi nuovi elementi non verranno visualizzati nella casella combinata.</span><span class="sxs-lookup"><span data-stu-id="c969f-112">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="c969f-113">Tuttavia, è possibile forzare l'aggiornamento della casella combinata chiamando i <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> metodi e <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> <xref:System.Windows.Forms.BindingContext> sull'istanza della classe a cui è associato il controllo.</span><span class="sxs-lookup"><span data-stu-id="c969f-113">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c969f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c969f-114">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="c969f-115">Data binding in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c969f-115">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="c969f-116">Data binding e Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c969f-116">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="c969f-117">Controlli Windows Form usati per elencare opzioni</span><span class="sxs-lookup"><span data-stu-id="c969f-117">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
