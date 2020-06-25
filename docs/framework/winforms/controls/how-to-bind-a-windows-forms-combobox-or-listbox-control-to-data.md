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
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="8f32e-103">Procedura: associare a dati un controllo ComboBox o ListBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="8f32e-103">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="8f32e-104">È possibile associare <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.ListBox> ai dati per eseguire attività quali l'esplorazione dei dati in un database, l'immissione di nuovi dati o la modifica di dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="8f32e-104">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="8f32e-105">Per associare un controllo ComboBox o ListBox</span><span class="sxs-lookup"><span data-stu-id="8f32e-105">To bind a ComboBox or ListBox control</span></span>  
  
1. <span data-ttu-id="8f32e-106">Impostare la `DataSource` proprietà su un oggetto origine dati.</span><span class="sxs-lookup"><span data-stu-id="8f32e-106">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="8f32e-107">Le origini dati possibili includono un oggetto <xref:System.Windows.Forms.BindingSource> associato a dati, una tabella di dati, una vista dati, un set di dati, un gestore visualizzazione dati, una matrice o qualsiasi classe che implementa l' <xref:System.Collections.IList> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8f32e-107">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="8f32e-108">Per ulteriori informazioni, vedere [origini dati supportate da Windows Forms](../data-sources-supported-by-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="8f32e-108">For more information, see [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="8f32e-109">Se si sta associando a una tabella, impostare la `DisplayMember` proprietà sul nome di una colonna nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="8f32e-109">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="8f32e-110">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="8f32e-110">\- or -</span></span>  
  
     <span data-ttu-id="8f32e-111">Se si sta associando a un <xref:System.Collections.IList> , impostare il membro di visualizzazione su una proprietà pubblica del tipo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8f32e-111">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
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
    > <span data-ttu-id="8f32e-112">Se si è connessi a un'origine dati che non implementa l' <xref:System.ComponentModel.IBindingList> interfaccia, ad esempio <xref:System.Collections.ArrayList> , i dati del controllo associato non verranno aggiornati al momento dell'aggiornamento dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="8f32e-112">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="8f32e-113">Ad esempio, se si dispone di una casella combinata associata a un oggetto <xref:System.Collections.ArrayList> e i dati vengono aggiunti a <xref:System.Collections.ArrayList> , questi nuovi elementi non verranno visualizzati nella casella combinata.</span><span class="sxs-lookup"><span data-stu-id="8f32e-113">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="8f32e-114">Tuttavia, è possibile forzare l'aggiornamento della casella combinata chiamando i <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> metodi e <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> sull'istanza della <xref:System.Windows.Forms.BindingContext> classe a cui è associato il controllo.</span><span class="sxs-lookup"><span data-stu-id="8f32e-114">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f32e-115">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="8f32e-115">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="8f32e-116">Data binding di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8f32e-116">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="8f32e-117">Associazione dati e Windows Form</span><span class="sxs-lookup"><span data-stu-id="8f32e-117">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="8f32e-118">Controlli Windows Form usati per elencare opzioni</span><span class="sxs-lookup"><span data-stu-id="8f32e-118">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
