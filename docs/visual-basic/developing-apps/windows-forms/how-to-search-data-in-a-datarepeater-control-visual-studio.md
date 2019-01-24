---
title: 'Procedura: Dati di ricerca in un controllo DataRepeater (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, implementing search
- DataRepeater, searching data
ms.assetid: a8ab5d17-b94f-43c4-8dd7-d0450226d73f
ms.openlocfilehash: 514e72afc9570071f57e385574456ff7d716bad7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654386"
---
# <a name="how-to-search-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="78373-102">Procedura: Dati di ricerca in un controllo DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="78373-102">How to: Search Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="78373-103">Quando si utilizza un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo contenente più record, è possibile consentire agli utenti di cercare un record specifico.</span><span class="sxs-lookup"><span data-stu-id="78373-103">When you are using a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control that contains many records, you may want to let users search for a specific record.</span></span> <span data-ttu-id="78373-104">Invece di cercare i dati nel controllo stesso, è possibile implementare una ricerca tramite l'esecuzione di query sottostante <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="78373-104">Rather than searching the data in the control itself, you can implement a search by querying the underlying <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="78373-105">Se l'elemento viene trovato, è quindi possibile usare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> proprietà utilizzata per selezionare l'elemento e scorrerlo nella visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="78373-105">If the item is found, you can then use the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> property to select the item and scroll it into view.</span></span>  
  
### <a name="to-implement-search"></a><span data-ttu-id="78373-106">Per implementare la ricerca</span><span class="sxs-lookup"><span data-stu-id="78373-106">To implement search</span></span>  
  
1.  <span data-ttu-id="78373-107">Trascinare il controllo <xref:System.Windows.Forms.TextBox> dalla **casella degli strumenti** al form che contiene il controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="78373-107">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="78373-108">Nella finestra Proprietà modificare la proprietà **Name** in **SearchTextBox**.</span><span class="sxs-lookup"><span data-stu-id="78373-108">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="78373-109">Trascinare il controllo <xref:System.Windows.Forms.Button> dalla **casella degli strumenti** al form che contiene il controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="78373-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="78373-110">Nella finestra Proprietà modificare la proprietà **Name** in **SearchButton**.</span><span class="sxs-lookup"><span data-stu-id="78373-110">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="78373-111">Impostare la proprietà **Text** su **Search**.</span><span class="sxs-lookup"><span data-stu-id="78373-111">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="78373-112">Fare doppio clic sul controllo <xref:System.Windows.Forms.Button> per aprire l'editor di codice e aggiungere il codice seguente al gestore dell'evento `SearchButton_Click` .</span><span class="sxs-lookup"><span data-stu-id="78373-112">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     [!code-vb[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-search-data-in-a-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-search-data-in-a-datarepeater-control-visual-studio_1.cs)]  
  
     <span data-ttu-id="78373-113">Sostituire *ProductsBindingSource* con il nome del <xref:System.Windows.Forms.BindingSource> per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>e sostituire *ProductID* con il nome del campo che si desidera eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="78373-113">Replace *ProductsBindingSource* with the name of the <xref:System.Windows.Forms.BindingSource> for your <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and replace *ProductID* with the name of the field that you want to search.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78373-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78373-114">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [<span data-ttu-id="78373-115">Introduzione al controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="78373-115">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="78373-116">Risoluzione dei problemi relativi al controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="78373-116">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="78373-117">Procedura: Modificare l'aspetto di un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="78373-117">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
