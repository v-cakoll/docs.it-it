---
title: Ordinare e filtrare i dati di ADO.NET con il componente BindingSource
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
ms.openlocfilehash: cf1da3bb94b26449eb72b0e4930b262236487acc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742971"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>Procedura: Ordinare e filtrare i dati ADO.NET con il componente BindingSource Windows Form
È possibile esporre le funzionalità di ordinamento e filtro del controllo <xref:System.Windows.Forms.BindingSource> tramite le proprietà <xref:System.Windows.Forms.BindingSource.Sort%2A> e <xref:System.Windows.Forms.BindingSource.Filter%2A>. È possibile applicare l'ordinamento semplice quando l'origine dati sottostante è un <xref:System.ComponentModel.IBindingList>ed è possibile applicare il filtro e l'ordinamento avanzato quando l'origine dati è una <xref:System.ComponentModel.IBindingListView>. Per la proprietà <xref:System.Windows.Forms.BindingSource.Sort%2A> è richiesta la sintassi ADO.NET standard: una stringa che rappresenta il nome di una colonna di dati nell'origine dati seguita da `ASC` o `DESC` per indicare se l'elenco deve essere ordinato in ordine crescente o decrescente. È possibile impostare l'ordinamento avanzato o l'ordinamento a più colonne separando ogni colonna con un separatore virgola. La proprietà <xref:System.Windows.Forms.BindingSource.Filter%2A> accetta un'espressione stringa.  
  
> [!NOTE]
> L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md).  
  
### <a name="to-filter-data-with-the-bindingsource"></a>Per filtrare i dati con BindingSource  
  
- Impostare la proprietà <xref:System.Windows.Forms.BindingSource.Filter%2A> su espressione desiderata.  
  
     Nell'esempio di codice seguente, l'espressione è un nome di colonna seguito da un valore che si desidera per la colonna.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>Per ordinare i dati con BindingSource  
  
1. Impostare la proprietà <xref:System.Windows.Forms.BindingSource.Sort%2A> sul nome della colonna che si desidera seguito da `ASC` o `DESC` per indicare l'ordine crescente o decrescente.  
  
2. Separare più colonne con una virgola.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente consente di caricare i dati dalla tabella Customers del database di esempio Northwind in un controllo <xref:System.Windows.Forms.DataGridView> e di filtrare e ordinare i dati visualizzati.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per eseguire questo esempio, incollare il codice in un modulo che contiene un <xref:System.Windows.Forms.BindingSource> denominato `BindingSource1` e un <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`. Gestire l'evento <xref:System.Windows.Forms.Form.Load> per il form e chiamare `InitializeSortedFilteredBindingSource` nel metodo del gestore dell'evento Load.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- [Procedura: Installare database di esempio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))
- [Componente BindingSource](bindingsource-component.md)
