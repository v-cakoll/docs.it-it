---
title: "Procedura: Gestire gli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Forms"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
ms.assetid: 9004e72f-fdec-4264-a37d-2c99764efc13
ms.openlocfilehash: 6297eaea93caea5d19af9740d2b5a1066507ff15
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592065"
---
# <a name="how-to-handle-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="21b87-102">Procedura: Gestire gli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="21b87-102">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="21b87-103">Nell'esempio di codice seguente viene illustrato come usare il controllo <xref:System.Windows.Forms.DataGridView> per segnalare all'utente eventuali errori di immissione dei dati.</span><span class="sxs-lookup"><span data-stu-id="21b87-103">The following code example demonstrates how to use the <xref:System.Windows.Forms.DataGridView> control to report data entry errors to the user.</span></span>  
  
 <span data-ttu-id="21b87-104">Per una spiegazione completa di questo esempio di codice, vedere [procedura dettagliata: Gestione degli errori che si verificano durante l'immissione di dati nella finestra di Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="21b87-104">For a complete explanation of this code example, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="21b87-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="21b87-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.DataError#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.DataError#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="21b87-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="21b87-106">Compiling the Code</span></span>  
 <span data-ttu-id="21b87-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="21b87-107">This example requires:</span></span>  
  
- <span data-ttu-id="21b87-108">Riferimenti agli assembly System, System.Data, System.Windows.Forms e System.XML.</span><span class="sxs-lookup"><span data-stu-id="21b87-108">References to the System, System.Data, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="21b87-109">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="21b87-109">.NET Framework Security</span></span>  
 <span data-ttu-id="21b87-110">L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="21b87-110">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="21b87-111">L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro.</span><span class="sxs-lookup"><span data-stu-id="21b87-111">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="21b87-112">Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="21b87-112">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21b87-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21b87-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="21b87-114">Procedura dettagliata: Gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="21b87-114">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="21b87-115">Immissione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="21b87-115">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="21b87-116">Procedura dettagliata: La convalida dei dati nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="21b87-116">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="21b87-117">Protezione delle informazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="21b87-117">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
