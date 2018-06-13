---
title: 'Procedura: cercare dati in un controllo DataRepeater (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, implementing search
- DataRepeater, searching data
ms.assetid: a8ab5d17-b94f-43c4-8dd7-d0450226d73f
ms.openlocfilehash: 689990ee125c85c3151a4e965b619fde068d220e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588054"
---
# <a name="how-to-search-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="e251b-102">Procedura: cercare dati in un controllo DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="e251b-102">How to: Search Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="e251b-103">Quando si utilizza un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo contenente molti record, è possibile consentire agli utenti di ricerca per un record specifico.</span><span class="sxs-lookup"><span data-stu-id="e251b-103">When you are using a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control that contains many records, you may want to let users search for a specific record.</span></span> <span data-ttu-id="e251b-104">Invece di cercare i dati nel controllo stesso, è possibile implementare una ricerca eseguendo una query sottostante <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="e251b-104">Rather than searching the data in the control itself, you can implement a search by querying the underlying <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="e251b-105">Se l'elemento viene trovato, è possibile utilizzare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> proprietà selezionare l'elemento e scorrerlo nella visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="e251b-105">If the item is found, you can then use the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> property to select the item and scroll it into view.</span></span>  
  
### <a name="to-implement-search"></a><span data-ttu-id="e251b-106">Per implementare la ricerca</span><span class="sxs-lookup"><span data-stu-id="e251b-106">To implement search</span></span>  
  
1.  <span data-ttu-id="e251b-107">Trascinare il controllo <xref:System.Windows.Forms.TextBox> dalla **casella degli strumenti** al form che contiene il controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="e251b-107">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="e251b-108">Nella finestra Proprietà modificare la proprietà **Name** in **SearchTextBox**.</span><span class="sxs-lookup"><span data-stu-id="e251b-108">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="e251b-109">Trascinare il controllo <xref:System.Windows.Forms.Button> dalla **casella degli strumenti** al form che contiene il controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="e251b-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="e251b-110">Nella finestra Proprietà modificare la proprietà **Name** in **SearchButton**.</span><span class="sxs-lookup"><span data-stu-id="e251b-110">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="e251b-111">Impostare la proprietà **Text** su **Search**.</span><span class="sxs-lookup"><span data-stu-id="e251b-111">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="e251b-112">Fare doppio clic sul controllo <xref:System.Windows.Forms.Button> per aprire l'editor di codice e aggiungere il codice seguente al gestore dell'evento `SearchButton_Click` .</span><span class="sxs-lookup"><span data-stu-id="e251b-112">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     [!code-vb[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-search-data-in-a-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-search-data-in-a-datarepeater-control-visual-studio_1.cs)]  
  
     <span data-ttu-id="e251b-113">Sostituire *ProductsBindingSource* con il nome del <xref:System.Windows.Forms.BindingSource> per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>e sostituire *ProductID* con il nome del campo che si desidera cercare.</span><span class="sxs-lookup"><span data-stu-id="e251b-113">Replace *ProductsBindingSource* with the name of the <xref:System.Windows.Forms.BindingSource> for your <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and replace *ProductID* with the name of the field that you want to search.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e251b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e251b-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="e251b-115">Introduzione al controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="e251b-115">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="e251b-116">Risoluzione dei problemi relativi al controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="e251b-116">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="e251b-117">Procedura: Modificare l'aspetto di un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="e251b-117">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
