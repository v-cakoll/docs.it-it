---
title: Visualizzazione degli errori in un set di dati tramite il componente ErrorProvider
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: 8c2155bf288db89b5d53567738fd399b915d50b6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745460"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a>Procedura: visualizzare errori in un dataset tramite il componente ErrorProvider di Windows Form
È possibile utilizzare il componente Windows Forms <xref:System.Windows.Forms.ErrorProvider> per visualizzare gli errori di colonna all'interno di un set di dati o di un'altra origine dati. Affinché un componente <xref:System.Windows.Forms.ErrorProvider> visualizzi errori di dati in un form, non è necessario che sia associato direttamente a un controllo. Una volta associato a un'origine dati, è possibile che venga visualizzata un'icona di errore accanto a qualsiasi controllo associato alla stessa origine dati.  
  
> [!NOTE]
> Se si modificano le proprietà <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> e <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> del provider di errori in fase di esecuzione, è necessario utilizzare il metodo <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> per evitare conflitti.  
  
### <a name="to-display-data-errors"></a>Per visualizzare gli errori relativi ai dati  
  
1. Associare il componente a una colonna specifica in una tabella di dati.  
  
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
  
2. Impostare la proprietà <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> sul form.  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3. Consente di impostare la posizione del record corrente su una riga contenente un errore di colonna.  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul componente ErrorProvider](errorprovider-component-overview-windows-forms.md)
- [Procedura: Visualizzare le icone di errori per la convalida dei form con il componente ErrorProvider di Windows Form](display-error-icons-for-form-validation-with-wf-errorprovider.md)
