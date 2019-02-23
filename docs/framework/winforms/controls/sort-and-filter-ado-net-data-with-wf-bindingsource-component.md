---
title: 'Procedura: Ordinare e filtrare i dati ADO.NET con il Windows Form componente BindingSource'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: 23f0ac8ff2a92fb96fbb7c69d87b01ed02b3b6b1
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "56746325"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>Procedura: Ordinare e filtrare i dati ADO.NET con il Windows Form componente BindingSource
È possibile esporre l'ordinamento e filtro funzionalità del <xref:System.Windows.Forms.BindingSource> controllare tramite il <xref:System.Windows.Forms.BindingSource.Sort%2A> e <xref:System.Windows.Forms.BindingSource.Filter%2A> proprietà. È possibile applicare un ordinamento semplice quando l'origine dati sottostante è un <xref:System.ComponentModel.IBindingList>, ed è possibile applicare il filtro e ordinamento avanzato quando l'origine dati è un <xref:System.ComponentModel.IBindingListView>. Il <xref:System.Windows.Forms.BindingSource.Sort%2A> proprietà richiede standard [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] sintassi: una stringa che rappresenta il nome di una colonna di dati nell'origine dati aggiungendo `ASC` o `DESC` per indicare se deve essere ordinato l'elenco in ordine crescente o decrescente. È possibile impostare l'ordinamento avanzato o più colonne di ordinamento separando ogni colonna con una virgola come separatore. Il <xref:System.Windows.Forms.BindingSource.Filter%2A> proprietà accetta un'espressione stringa.  
  
> [!NOTE]
>  L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
### <a name="to-filter-data-with-the-bindingsource"></a>Per filtrare i dati con BindingSource  
  
-   Impostare il <xref:System.Windows.Forms.BindingSource.Filter%2A> proprietà espressione desiderata.  
  
     Nell'esempio di codice seguente, l'espressione è un nome di colonna seguito dal valore desiderato per la colonna.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>Per ordinare i dati con BindingSource  
  
1.  Impostare il <xref:System.Windows.Forms.BindingSource.Sort%2A> proprietà sul nome di colonna desiderato aggiungendo `ASC` o `DESC` per indicare l'ordine crescente o decrescente.  
  
2.  Separare più colonne con una virgola.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente carica i dati della tabella Customers del database Northwind di esempio in un <xref:System.Windows.Forms.DataGridView> controllare, Filtra e ordina i dati visualizzati.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per eseguire questo esempio, incollare il codice in un form che contiene un <xref:System.Windows.Forms.BindingSource> denominate `BindingSource1` e una <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`. Gestire le <xref:System.Windows.Forms.Form.Load> evento per il form e chiamare `InitializeSortedFilteredBindingSource` nel metodo del gestore eventi load.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- [Procedura: Installare i database di esempio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))
- [Componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)
