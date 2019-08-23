---
title: "Procedura: Visualizzare gli errori all'interno di un set di dati con il componente ErrorProvider di Windows Forms"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: 3dbd2ccca607869a6f28bc5b3bd1c9f0769db9f5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950075"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a>Procedura: Visualizzare gli errori all'interno di un set di dati con il componente ErrorProvider di Windows Forms
È possibile utilizzare il componente <xref:System.Windows.Forms.ErrorProvider> Windows Forms per visualizzare gli errori di colonna all'interno di un set di dati o di un'altra origine dati. Per visualizzare <xref:System.Windows.Forms.ErrorProvider> gli errori relativi ai dati in un form, un componente non deve essere direttamente associato a un controllo. Una volta associato a un'origine dati, è possibile che venga visualizzata un'icona di errore accanto a qualsiasi controllo associato alla stessa origine dati.  
  
> [!NOTE]
> Se si modificano le proprietà <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> e <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> del provider di errori in fase di esecuzione, è <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> necessario utilizzare il metodo per evitare conflitti.  
  
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
  
2. Impostare la <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> proprietà sul form.  
  
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
- [Procedura: Visualizza le icone di errore per la convalida dei form con il componente Windows Forms ErrorProvider](display-error-icons-for-form-validation-with-wf-errorprovider.md)
