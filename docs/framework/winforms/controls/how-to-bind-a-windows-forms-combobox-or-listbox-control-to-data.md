---
title: 'Procedura: associare a dati un controllo ComboBox o ListBox Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b671910ac77b7456492cab871ace3abb61ac7fd7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="64c80-102">Procedura: associare a dati un controllo ComboBox o ListBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="64c80-102">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="64c80-103">È possibile associare il <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.ListBox> ai dati per eseguire attività quali l'esplorazione di dati in un database, immettere nuovi dati o la modifica dei dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="64c80-103">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="64c80-104">Per associare un controllo ComboBox o ListBox</span><span class="sxs-lookup"><span data-stu-id="64c80-104">To bind a ComboBox or ListBox control</span></span>  
  
1.  <span data-ttu-id="64c80-105">Impostare il `DataSource` proprietà a un oggetto origine dati.</span><span class="sxs-lookup"><span data-stu-id="64c80-105">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="64c80-106">Origini dati possibili includono un <xref:System.Windows.Forms.BindingSource> associato a dati, una tabella di dati, una visualizzazione dati, un set di dati, un visualizzazione dati manager, una matrice o qualsiasi classe che implementa il <xref:System.Collections.IList> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="64c80-106">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="64c80-107">Per ulteriori informazioni, vedere [origini dati supportate da Windows Form](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="64c80-107">For more information, see [Data Sources Supported by Windows Forms](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="64c80-108">Se si desidera associare a una tabella, impostare il `DisplayMember` proprietà sul nome di una colonna nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="64c80-108">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="64c80-109">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="64c80-109">\- or -</span></span>  
  
     <span data-ttu-id="64c80-110">Se si desidera associare a un <xref:System.Collections.IList>, impostare il membro visualizzato su una proprietà pubblica di tipo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="64c80-110">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
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
    >  <span data-ttu-id="64c80-111">Se si è associati a un'origine dati che non implementa il <xref:System.ComponentModel.IBindingList> interfaccia, ad esempio un <xref:System.Collections.ArrayList>, i dati del controllo associato non essere aggiornati quando viene aggiornata l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="64c80-111">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="64c80-112">Ad esempio, se dispone di una casella combinata associata a un <xref:System.Collections.ArrayList> e si aggiungono dati al <xref:System.Collections.ArrayList>, questi nuovi elementi non verranno visualizzati nella casella combinata.</span><span class="sxs-lookup"><span data-stu-id="64c80-112">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="64c80-113">Tuttavia, è possibile forzare la casella combinata per essere aggiornato chiamando il <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> e <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> metodi nell'istanza del <xref:System.Windows.Forms.BindingContext> classe a cui è associato il controllo.</span><span class="sxs-lookup"><span data-stu-id="64c80-113">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64c80-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64c80-114">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 [<span data-ttu-id="64c80-115">Data binding in Windows Form</span><span class="sxs-lookup"><span data-stu-id="64c80-115">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="64c80-116">Data binding e Windows Forms</span><span class="sxs-lookup"><span data-stu-id="64c80-116">Data Binding and Windows Forms</span></span>](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [<span data-ttu-id="64c80-117">Controlli Windows Form usati per elencare opzioni</span><span class="sxs-lookup"><span data-stu-id="64c80-117">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
