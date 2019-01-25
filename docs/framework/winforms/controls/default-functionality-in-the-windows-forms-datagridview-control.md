---
title: Funzionalità predefinite nel controllo DataGridView Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: 1b67fa4da987778b08bad59d2e2829d0a974512a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710560"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="ac056-102">Funzionalità predefinite nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="ac056-102">Default Functionality in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="ac056-103">I moduli di Windows <xref:System.Windows.Forms.DataGridView> controllo offre agli utenti con una quantità significativa di funzionalità predefinite.</span><span class="sxs-lookup"><span data-stu-id="ac056-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control provides users with a significant amount of default functionality.</span></span>  
  
## <a name="default-functionality"></a><span data-ttu-id="ac056-104">Funzionalità predefinite</span><span class="sxs-lookup"><span data-stu-id="ac056-104">Default Functionality</span></span>  
 <span data-ttu-id="ac056-105">Per impostazione predefinita, un <xref:System.Windows.Forms.DataGridView> controllo:</span><span class="sxs-lookup"><span data-stu-id="ac056-105">By default, a <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
-   <span data-ttu-id="ac056-106">Visualizza automaticamente le intestazioni di colonna e le intestazioni di riga che restano visibili durante lo scorrimento verticale della tabella.</span><span class="sxs-lookup"><span data-stu-id="ac056-106">Automatically displays column headers and row headers that remain visible as the table scrolls vertically.</span></span>  
  
-   <span data-ttu-id="ac056-107">Include un'intestazione di riga che contiene un indicatore di selezione per la riga corrente.</span><span class="sxs-lookup"><span data-stu-id="ac056-107">Has a row header that contains a selection indicator for the current row.</span></span>  
  
-   <span data-ttu-id="ac056-108">Dispone di un rettangolo di selezione nella prima cella.</span><span class="sxs-lookup"><span data-stu-id="ac056-108">Has a selection rectangle in the first cell.</span></span>  
  
-   <span data-ttu-id="ac056-109">Include colonne che possono essere ridimensionate automaticamente quando l'utente fa doppio clic sui separatori di colonna.</span><span class="sxs-lookup"><span data-stu-id="ac056-109">Has columns that can be automatically resized when the user double-clicks the column dividers.</span></span>  
  
-   <span data-ttu-id="ac056-110">Supporta automaticamente gli stili famiglia di prodotti Windows Server 2003 e Windows XP quando la <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> viene chiamato dall'oggetto dell'applicazione `Main` (metodo).</span><span class="sxs-lookup"><span data-stu-id="ac056-110">Automatically supports visual styles on Windows XP and the Windows Server 2003 family when the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method is called from the application's `Main` method.</span></span>  
  
 <span data-ttu-id="ac056-111">Inoltre, il contenuto di un <xref:System.Windows.Forms.DataGridView> controllo può essere modificato per impostazione predefinita:</span><span class="sxs-lookup"><span data-stu-id="ac056-111">Additionally, the contents of a <xref:System.Windows.Forms.DataGridView> control can be edited by default:</span></span>  
  
-   <span data-ttu-id="ac056-112">Se l'utente fa doppio clic o preme F2 in una cella, il controllo viene automaticamente inserisce la cella in modalità di modifica e aggiorna il contenuto della cella mentre l'utente digita.</span><span class="sxs-lookup"><span data-stu-id="ac056-112">If the user double-clicks or presses F2 in a cell, the control automatically puts the cell into edit mode and updates the contents of the cell as the user types.</span></span>  
  
-   <span data-ttu-id="ac056-113">Se l'utente scorre alla fine della griglia, verrà visualizzato l'utente che sia presente una riga per l'aggiunta di nuovi record.</span><span class="sxs-lookup"><span data-stu-id="ac056-113">If the user scrolls to the end of the grid, the user will see that a row for adding new records is present.</span></span> <span data-ttu-id="ac056-114">Quando l'utente fa clic su questa riga, viene aggiunta una nuova riga per il <xref:System.Windows.Forms.DataGridView> controllo, con i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="ac056-114">When the user clicks this row, a new row is added to the <xref:System.Windows.Forms.DataGridView> control, with default values.</span></span> <span data-ttu-id="ac056-115">Quando l'utente preme ESC, questa nuova riga viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="ac056-115">When the user presses ESC, this new row disappears.</span></span>  
  
-   <span data-ttu-id="ac056-116">Se l'utente fa clic su un'intestazione di riga, viene selezionata l'intera riga.</span><span class="sxs-lookup"><span data-stu-id="ac056-116">If the user clicks a row header, the whole row is selected.</span></span>  
  
 <span data-ttu-id="ac056-117">Quando si associa un <xref:System.Windows.Forms.DataGridView> controllo a un'origine dati tramite l'impostazione relativa <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà, il controllo:</span><span class="sxs-lookup"><span data-stu-id="ac056-117">When you bind a <xref:System.Windows.Forms.DataGridView> control to a data source by setting its <xref:System.Windows.Forms.DataGridView.DataSource%2A> property, the control:</span></span>  
  
-   <span data-ttu-id="ac056-118">Usa automaticamente i nomi delle colonne dell'origine dati come testo dell'intestazione di colonna.</span><span class="sxs-lookup"><span data-stu-id="ac056-118">Automatically uses the names of the data source's columns as the column header text.</span></span>  
  
-   <span data-ttu-id="ac056-119">Viene popolato con il contenuto dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ac056-119">Is populated with the contents of the data source.</span></span> <span data-ttu-id="ac056-120"><xref:System.Windows.Forms.DataGridView> le colonne vengono create automaticamente per ogni colonna nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ac056-120"><xref:System.Windows.Forms.DataGridView> columns are automatically created for each column in the data source.</span></span>  
  
-   <span data-ttu-id="ac056-121">Crea una riga per ogni riga visibile nella tabella.</span><span class="sxs-lookup"><span data-stu-id="ac056-121">Creates a row for each visible row in the table.</span></span>  
  
-   <span data-ttu-id="ac056-122">Ordina automaticamente le righe basate sui dati sottostanti quando l'utente fa clic su un'intestazione di colonna.</span><span class="sxs-lookup"><span data-stu-id="ac056-122">Automatically sorts the rows based on the underlying data when the user clicks a column header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac056-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac056-123">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="ac056-124">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="ac056-124">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
