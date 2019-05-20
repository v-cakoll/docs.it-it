---
title: 'Procedura: Ordinare e filtrare i dati ADO.NET con il componente BindingSource di Windows Forms'
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
ms.openlocfilehash: d270155fa1e6b61d8537096a07a4b93fa3b79b35
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882202"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="b2ff0-102">Procedura: Ordinare e filtrare i dati ADO.NET con il componente BindingSource di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b2ff0-102">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="b2ff0-103">È possibile esporre l'ordinamento e filtro funzionalità del <xref:System.Windows.Forms.BindingSource> controllare tramite il <xref:System.Windows.Forms.BindingSource.Sort%2A> e <xref:System.Windows.Forms.BindingSource.Filter%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b2ff0-103">You can expose the sorting and filtering capability of <xref:System.Windows.Forms.BindingSource> control through the <xref:System.Windows.Forms.BindingSource.Sort%2A> and <xref:System.Windows.Forms.BindingSource.Filter%2A> properties.</span></span> <span data-ttu-id="b2ff0-104">È possibile applicare un ordinamento semplice quando l'origine dati sottostante è un <xref:System.ComponentModel.IBindingList>, ed è possibile applicare il filtro e ordinamento avanzato quando l'origine dati è un <xref:System.ComponentModel.IBindingListView>.</span><span class="sxs-lookup"><span data-stu-id="b2ff0-104">You can apply simple sorting when the underlying data source is an <xref:System.ComponentModel.IBindingList>, and you can apply filtering and advanced sorting when the data source is an <xref:System.ComponentModel.IBindingListView>.</span></span> <span data-ttu-id="b2ff0-105">Il <xref:System.Windows.Forms.BindingSource.Sort%2A> proprietà richiede la sintassi ADO.NET standard: una stringa che rappresenta il nome di una colonna di dati nell'origine dati aggiungendo `ASC` o `DESC` per indicare se deve essere ordinato l'elenco in ordine crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="b2ff0-105">The <xref:System.Windows.Forms.BindingSource.Sort%2A> property requires standard ADO.NET syntax: a string representing the name of a column of data in the data source followed by `ASC` or `DESC` to indicate whether the list should be sorted in ascending or descending order.</span></span> <span data-ttu-id="b2ff0-106">È possibile impostare l'ordinamento avanzato o più colonne di ordinamento separando ogni colonna con una virgola come separatore.</span><span class="sxs-lookup"><span data-stu-id="b2ff0-106">You can set advanced sorting or multiple-column sorting by separating each column with a comma separator.</span></span> <span data-ttu-id="b2ff0-107">Il <xref:System.Windows.Forms.BindingSource.Filter%2A> proprietà accetta un'espressione stringa.</span><span class="sxs-lookup"><span data-stu-id="b2ff0-107">The <xref:System.Windows.Forms.BindingSource.Filter%2A> property takes a string expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2ff0-108">L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b2ff0-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="b2ff0-109">L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro.</span><span class="sxs-lookup"><span data-stu-id="b2ff0-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="b2ff0-110">Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="b2ff0-110">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
### <a name="to-filter-data-with-the-bindingsource"></a><span data-ttu-id="b2ff0-111">Per filtrare i dati con BindingSource</span><span class="sxs-lookup"><span data-stu-id="b2ff0-111">To filter data with the BindingSource</span></span>  
  
- <span data-ttu-id="b2ff0-112">Impostare il <xref:System.Windows.Forms.BindingSource.Filter%2A> proprietà espressione desiderata.</span><span class="sxs-lookup"><span data-stu-id="b2ff0-112">Set the <xref:System.Windows.Forms.BindingSource.Filter%2A> property to expression that you want.</span></span>  
  
     <span data-ttu-id="b2ff0-113">Nell'esempio di codice seguente, l'espressione è un nome di colonna seguito dal valore desiderato per la colonna.</span><span class="sxs-lookup"><span data-stu-id="b2ff0-113">In the following code example, the expression is a column name followed by value that you want for the column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a><span data-ttu-id="b2ff0-114">Per ordinare i dati con BindingSource</span><span class="sxs-lookup"><span data-stu-id="b2ff0-114">To sort data with the BindingSource</span></span>  
  
1. <span data-ttu-id="b2ff0-115">Impostare il <xref:System.Windows.Forms.BindingSource.Sort%2A> proprietà sul nome di colonna desiderato aggiungendo `ASC` o `DESC` per indicare l'ordine crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="b2ff0-115">Set the <xref:System.Windows.Forms.BindingSource.Sort%2A> property to the column name that you want followed by `ASC` or `DESC` to indicate the ascending or descending order.</span></span>  
  
2. <span data-ttu-id="b2ff0-116">Separare più colonne con una virgola.</span><span class="sxs-lookup"><span data-stu-id="b2ff0-116">Separate multiple columns with a comma.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="b2ff0-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="b2ff0-117">Example</span></span>  
 <span data-ttu-id="b2ff0-118">Esempio di codice seguente carica i dati della tabella Customers del database Northwind di esempio in un <xref:System.Windows.Forms.DataGridView> controllare, Filtra e ordina i dati visualizzati.</span><span class="sxs-lookup"><span data-stu-id="b2ff0-118">The following code example loads data from the Customers table of the Northwind sample database into a <xref:System.Windows.Forms.DataGridView> control, and filters and sorts the displayed data.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b2ff0-119">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b2ff0-119">Compiling the Code</span></span>  
 <span data-ttu-id="b2ff0-120">Per eseguire questo esempio, incollare il codice in un form che contiene un <xref:System.Windows.Forms.BindingSource> denominate `BindingSource1` e una <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="b2ff0-120">To run this example, paste the code into a form that contains a <xref:System.Windows.Forms.BindingSource> named `BindingSource1` and a <xref:System.Windows.Forms.DataGridView> named `dataGridView1`.</span></span> <span data-ttu-id="b2ff0-121">Gestire le <xref:System.Windows.Forms.Form.Load> evento per il form e chiamare `InitializeSortedFilteredBindingSource` nel metodo del gestore eventi load.</span><span class="sxs-lookup"><span data-stu-id="b2ff0-121">Handle the <xref:System.Windows.Forms.Form.Load> event for the form and call `InitializeSortedFilteredBindingSource` in the load event handler method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2ff0-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2ff0-122">See also</span></span>

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- <span data-ttu-id="b2ff0-123">[Procedura: Installare i database di esempio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="b2ff0-123">[How to: Install Sample Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span></span>
- [<span data-ttu-id="b2ff0-124">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="b2ff0-124">BindingSource Component</span></span>](bindingsource-component.md)
