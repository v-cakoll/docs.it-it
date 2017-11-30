---
title: 'Procedura: visualizzare errori in un dataset tramite il componente ErrorProvider di Windows Form'
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
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 28c90df258db8480f68eea05f922b36f30d81a3f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="4958c-102">Procedura: visualizzare errori in un dataset tramite il componente ErrorProvider di Windows Form</span><span class="sxs-lookup"><span data-stu-id="4958c-102">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="4958c-103">È possibile utilizzare Windows Form <xref:System.Windows.Forms.ErrorProvider> componente per visualizzare gli errori di colonna all'interno di un set di dati o un'altra origine dati.</span><span class="sxs-lookup"><span data-stu-id="4958c-103">You can use the Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to view column errors within a dataset or other data source.</span></span> <span data-ttu-id="4958c-104">Per un <xref:System.Windows.Forms.ErrorProvider> componente per visualizzare gli errori di dati in un form, non deve essere associata direttamente a un controllo.</span><span class="sxs-lookup"><span data-stu-id="4958c-104">For an <xref:System.Windows.Forms.ErrorProvider> component to display data errors on a form, it does not have to be directly associated with a control.</span></span> <span data-ttu-id="4958c-105">Una volta è associato a un'origine dati, è possibile visualizzare un'icona di errore accanto a qualsiasi controllo associato alla stessa origine dati.</span><span class="sxs-lookup"><span data-stu-id="4958c-105">Once it is bound to a data source, it can display an error icon next to any control that is bound to the same data source.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4958c-106">Se si modifica il provider di errore <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> e <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> proprietà in fase di esecuzione, è consigliabile utilizzare il <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> metodo per evitare conflitti.</span><span class="sxs-lookup"><span data-stu-id="4958c-106">If you change the error provider's <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> and <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> properties at run time, you should use the <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> method to avoid conflicts.</span></span>  
  
### <a name="to-display-data-errors"></a><span data-ttu-id="4958c-107">Per visualizzare gli errori di dati</span><span class="sxs-lookup"><span data-stu-id="4958c-107">To display data errors</span></span>  
  
1.  <span data-ttu-id="4958c-108">Associare il componente a una colonna specifica all'interno di una tabella di dati.</span><span class="sxs-lookup"><span data-stu-id="4958c-108">Bind the component to a specific column within a data table.</span></span>  
  
    ```vb  
    ' Assumes existence of DataSet1, DataTable1  
    TextBox1.DataBindings.Add("Text", DataSet1, "Customers.Name")  
    ErrorProvider1.DataSource = DataSet1  
    ErrorProvider1.DataMember = "Customers"  
    ```  
  
    ```csharp  
    // Assumes existence of DataSet1, DataTable1  
    textBox1.DataBindings.Add("Text", DataSet1, "Customers.Name");  
    errorProvider1.DataSource = DataSet1;  
    errorProvider1.DataMember = "Customers";  
    ```  
  
2.  <span data-ttu-id="4958c-109">Impostare il <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> proprietà al form.</span><span class="sxs-lookup"><span data-stu-id="4958c-109">Set the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property to the form.</span></span>  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3.  <span data-ttu-id="4958c-110">Impostare la posizione del record corrente a una riga che contiene un errore di colonna.</span><span class="sxs-lookup"><span data-stu-id="4958c-110">Set the position of the current record to a row that contains a column error.</span></span>  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4958c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4958c-111">See Also</span></span>  
 [<span data-ttu-id="4958c-112">Panoramica sul componente ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="4958c-112">ErrorProvider Component Overview</span></span>](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [<span data-ttu-id="4958c-113">Procedura: Visualizzare le icone di errori per la convalida dei form con il componente ErrorProvider di Windows Form</span><span class="sxs-lookup"><span data-stu-id="4958c-113">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
