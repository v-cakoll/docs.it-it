---
title: Funzionalità predefinite nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: b695883ac7ec3fb0c459adb66214b0eceab3a128
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746129"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="25124-102">Funzionalità predefinite nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="25124-102">Default Functionality in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="25124-103">Il controllo Windows Forms <xref:System.Windows.Forms.DataGridView> fornisce agli utenti una quantità significativa di funzionalità predefinite.</span><span class="sxs-lookup"><span data-stu-id="25124-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control provides users with a significant amount of default functionality.</span></span>  
  
## <a name="default-functionality"></a><span data-ttu-id="25124-104">Funzionalità predefinite</span><span class="sxs-lookup"><span data-stu-id="25124-104">Default Functionality</span></span>  
 <span data-ttu-id="25124-105">Per impostazione predefinita, un controllo <xref:System.Windows.Forms.DataGridView>:</span><span class="sxs-lookup"><span data-stu-id="25124-105">By default, a <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
- <span data-ttu-id="25124-106">Visualizza automaticamente le intestazioni di colonna e le intestazioni di riga che rimangono visibili quando la tabella scorre verticalmente.</span><span class="sxs-lookup"><span data-stu-id="25124-106">Automatically displays column headers and row headers that remain visible as the table scrolls vertically.</span></span>  
  
- <span data-ttu-id="25124-107">Dispone di un'intestazione di riga che contiene un indicatore di selezione per la riga corrente.</span><span class="sxs-lookup"><span data-stu-id="25124-107">Has a row header that contains a selection indicator for the current row.</span></span>  
  
- <span data-ttu-id="25124-108">Dispone di un rettangolo di selezione nella prima cella.</span><span class="sxs-lookup"><span data-stu-id="25124-108">Has a selection rectangle in the first cell.</span></span>  
  
- <span data-ttu-id="25124-109">Include colonne che possono essere ridimensionate automaticamente quando l'utente fa doppio clic sui divisori di colonna.</span><span class="sxs-lookup"><span data-stu-id="25124-109">Has columns that can be automatically resized when the user double-clicks the column dividers.</span></span>  
  
- <span data-ttu-id="25124-110">Supporta automaticamente gli stili di visualizzazione in Windows XP e la famiglia Windows Server 2003 quando il metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> viene chiamato dal metodo `Main` dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="25124-110">Automatically supports visual styles on Windows XP and the Windows Server 2003 family when the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method is called from the application's `Main` method.</span></span>  
  
 <span data-ttu-id="25124-111">Inoltre, è possibile modificare il contenuto di un controllo <xref:System.Windows.Forms.DataGridView> per impostazione predefinita:</span><span class="sxs-lookup"><span data-stu-id="25124-111">Additionally, the contents of a <xref:System.Windows.Forms.DataGridView> control can be edited by default:</span></span>  
  
- <span data-ttu-id="25124-112">Se l'utente fa doppio clic o preme F2 in una cella, il controllo inserisce automaticamente la cella in modalità di modifica e aggiorna il contenuto della cella come tipi di utente.</span><span class="sxs-lookup"><span data-stu-id="25124-112">If the user double-clicks or presses F2 in a cell, the control automatically puts the cell into edit mode and updates the contents of the cell as the user types.</span></span>  
  
- <span data-ttu-id="25124-113">Se l'utente scorre fino alla fine della griglia, l'utente noterà che è presente una riga per l'aggiunta di nuovi record.</span><span class="sxs-lookup"><span data-stu-id="25124-113">If the user scrolls to the end of the grid, the user will see that a row for adding new records is present.</span></span> <span data-ttu-id="25124-114">Quando l'utente fa clic su questa riga, viene aggiunta una nuova riga al controllo <xref:System.Windows.Forms.DataGridView> con i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="25124-114">When the user clicks this row, a new row is added to the <xref:System.Windows.Forms.DataGridView> control, with default values.</span></span> <span data-ttu-id="25124-115">Quando l'utente preme ESC, la nuova riga scompare.</span><span class="sxs-lookup"><span data-stu-id="25124-115">When the user presses ESC, this new row disappears.</span></span>  
  
- <span data-ttu-id="25124-116">Se l'utente fa clic su un'intestazione di riga, viene selezionata l'intera riga.</span><span class="sxs-lookup"><span data-stu-id="25124-116">If the user clicks a row header, the whole row is selected.</span></span>  
  
 <span data-ttu-id="25124-117">Quando si associa un controllo <xref:System.Windows.Forms.DataGridView> a un'origine dati impostando la relativa proprietà <xref:System.Windows.Forms.DataGridView.DataSource%2A>, il controllo:</span><span class="sxs-lookup"><span data-stu-id="25124-117">When you bind a <xref:System.Windows.Forms.DataGridView> control to a data source by setting its <xref:System.Windows.Forms.DataGridView.DataSource%2A> property, the control:</span></span>  
  
- <span data-ttu-id="25124-118">Usa automaticamente i nomi delle colonne dell'origine dati come testo dell'intestazione di colonna.</span><span class="sxs-lookup"><span data-stu-id="25124-118">Automatically uses the names of the data source's columns as the column header text.</span></span>  
  
- <span data-ttu-id="25124-119">Viene popolato con il contenuto dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="25124-119">Is populated with the contents of the data source.</span></span> <span data-ttu-id="25124-120"><xref:System.Windows.Forms.DataGridView> colonne vengono create automaticamente per ogni colonna nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="25124-120"><xref:System.Windows.Forms.DataGridView> columns are automatically created for each column in the data source.</span></span>  
  
- <span data-ttu-id="25124-121">Crea una riga per ogni riga visibile della tabella.</span><span class="sxs-lookup"><span data-stu-id="25124-121">Creates a row for each visible row in the table.</span></span>  
  
- <span data-ttu-id="25124-122">Ordina automaticamente le righe in base ai dati sottostanti quando l'utente fa clic su un'intestazione di colonna.</span><span class="sxs-lookup"><span data-stu-id="25124-122">Automatically sorts the rows based on the underlying data when the user clicks a column header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25124-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25124-123">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="25124-124">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="25124-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
