---
title: Creazione di un form Master-Details con due controlli DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], creating
ms.assetid: 99f6e876-3f7f-4139-9063-e36587c95b02
ms.openlocfilehash: d317f4e592790c9b48b539b1601814569e14529f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737329"
---
# <a name="how-to-create-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a><span data-ttu-id="55953-102">Procedura: creare un form Master-Details mediante due controlli DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="55953-102">How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="55953-103">Nell'esempio di codice riportato di seguito viene creato un form Master-Details usando due controlli <xref:System.Windows.Forms.DataGridView> associati a due componenti <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="55953-103">The following code example creates a master/detail form using two <xref:System.Windows.Forms.DataGridView> controls bound to two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="55953-104">L'origine dati è un <xref:System.Data.DataSet> contenente le tabelle `Customers` e `Orders` del database di esempio SQL Server Northwind insieme a un oggetto <xref:System.Data.DataRelation> che mette in relazione le due tabelle tramite la colonna `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="55953-104">The data source is a <xref:System.Data.DataSet> that contains the `Customers` and `Orders` tables from the Northwind SQL Server sample database along with a <xref:System.Data.DataRelation> that relates the two through the `CustomerID` column.</span></span>  
  
 <span data-ttu-id="55953-105">Un oggetto <xref:System.Windows.Forms.BindingSource> è associato alla tabella `Customers` padre nel DataSet.</span><span class="sxs-lookup"><span data-stu-id="55953-105">One <xref:System.Windows.Forms.BindingSource> is bound to the parent `Customers` table in the data set.</span></span> <span data-ttu-id="55953-106">Questi dati vengono visualizzati nel controllo <xref:System.Windows.Forms.DataGridView> master.</span><span class="sxs-lookup"><span data-stu-id="55953-106">This data is displayed in the master <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="55953-107">L'altro oggetto <xref:System.Windows.Forms.BindingSource> è associato al primo connettore dati.</span><span class="sxs-lookup"><span data-stu-id="55953-107">The other <xref:System.Windows.Forms.BindingSource> is bound to the first data connector.</span></span> <span data-ttu-id="55953-108">Poiché la proprietà <xref:System.Windows.Forms.BindingSource.DataMember%2A> del secondo oggetto <xref:System.Windows.Forms.BindingSource> è impostata sul nome di <xref:System.Data.DataRelation>,</span><span class="sxs-lookup"><span data-stu-id="55953-108">The <xref:System.Windows.Forms.BindingSource.DataMember%2A> property of the second <xref:System.Windows.Forms.BindingSource> is set to the <xref:System.Data.DataRelation> name.</span></span> <span data-ttu-id="55953-109">il controllo dettagli <xref:System.Windows.Forms.DataGridView> associato visualizza le righe della tabella `Orders` figlio corrispondenti alla riga corrente nel controllo <xref:System.Windows.Forms.DataGridView> master.</span><span class="sxs-lookup"><span data-stu-id="55953-109">This causes the associated detail <xref:System.Windows.Forms.DataGridView> control to display the rows of the child `Orders` table that correspond to the current row in the master <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="55953-110">Per una spiegazione completa di questo esempio di codice, vedere [procedura dettagliata: creazione di un form Master-Details con due controlli DataGridView Windows Forms](creating-a-master-detail-form-using-two-datagridviews.md).</span><span class="sxs-lookup"><span data-stu-id="55953-110">For a complete explanation of this code example, see [Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls](creating-a-master-detail-form-using-two-datagridviews.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="55953-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="55953-111">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="55953-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="55953-112">Compiling the Code</span></span>  
 <span data-ttu-id="55953-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="55953-113">This example requires:</span></span>  
  
 <span data-ttu-id="55953-114">Riferimenti agli assembly System, System.Data, System.Windows.Forms e System.XML.</span><span class="sxs-lookup"><span data-stu-id="55953-114">References to the System, System.Data, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="55953-115">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="55953-115">.NET Framework Security</span></span>  
 <span data-ttu-id="55953-116">L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="55953-116">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="55953-117">L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro.</span><span class="sxs-lookup"><span data-stu-id="55953-117">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="55953-118">Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="55953-118">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55953-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55953-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="55953-120">Procedura dettagliata: Creazione di un form Master-Details con due controlli DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="55953-120">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)
- [<span data-ttu-id="55953-121">Visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="55953-121">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="55953-122">Protezione delle informazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="55953-122">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
