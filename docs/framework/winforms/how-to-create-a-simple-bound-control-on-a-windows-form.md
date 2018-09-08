---
title: 'Procedura: creare un controllo con associazione semplice in un Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: 26bc136ea2b7e5bda4a57c5dad65ec3522efcd3d
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44197663"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a><span data-ttu-id="eb6e3-102">Procedura: creare un controllo con associazione semplice in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="eb6e3-102">How to: Create a Simple-Bound Control on a Windows Form</span></span>
<span data-ttu-id="eb6e3-103">Con *associazione semplice*, è possibile visualizzare un singolo elemento di dati, ad esempio un valore di colonna da una tabella di set di dati, in un controllo.</span><span class="sxs-lookup"><span data-stu-id="eb6e3-103">With *simple binding*, you can display a single data element, such as a column value from a dataset table, in a control.</span></span> <span data-ttu-id="eb6e3-104">È possibile un'associazione semplice di qualsiasi proprietà di un controllo a un valore di dati.</span><span class="sxs-lookup"><span data-stu-id="eb6e3-104">You can simple-bind any property of a control to a data value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb6e3-105">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="eb6e3-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="eb6e3-106">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="eb6e3-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="eb6e3-107">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="eb6e3-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-simple-bind-a-control"></a><span data-ttu-id="eb6e3-108">Per un controllo di un'associazione semplice</span><span class="sxs-lookup"><span data-stu-id="eb6e3-108">To simple-bind a control</span></span>  
  
1.  <span data-ttu-id="eb6e3-109">Effettuare una connessione a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="eb6e3-109">Connect to a data source.</span></span> <span data-ttu-id="eb6e3-110">Per altre informazioni, vedere [ci si connette a un'origine dati](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="eb6e3-110">For more information, see [Connecting to a Data Source](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span></span>  
  
2.  <span data-ttu-id="eb6e3-111">Selezionare il controllo nel form e visualizzare il **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="eb6e3-111">In the form, select the control and display the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="eb6e3-112">Espandere la **(DataBindings)** proprietà.</span><span class="sxs-lookup"><span data-stu-id="eb6e3-112">Expand the **(DataBindings)** property.</span></span>  
  
     <span data-ttu-id="eb6e3-113">Le proprietà associate in genere sono visualizzate sotto le **(DataBindings)** proprietà.</span><span class="sxs-lookup"><span data-stu-id="eb6e3-113">The properties most often bound are displayed underneath the **(DataBindings)** property.</span></span> <span data-ttu-id="eb6e3-114">Ad esempio, nella maggior parte dei controlli, il **testo** più di frequente è associata la proprietà.</span><span class="sxs-lookup"><span data-stu-id="eb6e3-114">For example, in most controls, the **Text** property is most frequently bound.</span></span>  
  
4.  <span data-ttu-id="eb6e3-115">Se la proprietà si desidera binding non è uno dei più comunemente associate, selezionare la **puntini di sospensione** pulsante (![schermata di VisualStudioEllipsesButton](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton") ) nei **(avanzate)** casella per visualizzare i **formattazione e associazione avanzata** finestra di dialogo contenente un elenco completo delle proprietà per il controllo.</span><span class="sxs-lookup"><span data-stu-id="eb6e3-115">If the property you want to bind is not one of the commonly bound properties, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) in the **(Advanced)** box to display the **Formatting and Advanced Binding** dialog box with a complete list of properties for that control.</span></span>  
  
5.  <span data-ttu-id="eb6e3-116">Selezionare la proprietà si desidera eseguire il binding e fare clic sulla freccia a discesa sotto **Binding**.</span><span class="sxs-lookup"><span data-stu-id="eb6e3-116">Select the property you want to bind and click the drop-down arrow under **Binding**.</span></span>  
  
     <span data-ttu-id="eb6e3-117">Verrà visualizzato un elenco di origini dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="eb6e3-117">A list of available data sources is displayed.</span></span>  
  
6.  <span data-ttu-id="eb6e3-118">Espandere l'origine dati da associare fino a quando non vengono visualizzati i dati desiderati.</span><span class="sxs-lookup"><span data-stu-id="eb6e3-118">Expand the data source you want to bind to until you find the single data element you want.</span></span> <span data-ttu-id="eb6e3-119">Se ad esempio si vuole associare il valore di una colonna in una tabella di set di dati, espandere il nome del set di dati, quindi espandere il nome della tabella per visualizzare i nomi delle colonne.</span><span class="sxs-lookup"><span data-stu-id="eb6e3-119">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>  
  
7.  <span data-ttu-id="eb6e3-120">Fare clic sul nome dell'elemento a cui effettuare il binding.</span><span class="sxs-lookup"><span data-stu-id="eb6e3-120">Click the name of an element to bind to.</span></span>  
  
8.  <span data-ttu-id="eb6e3-121">Se si utilizza il **formattazione e associazione avanzata** della finestra di dialogo fare clic su **OK** per tornare al **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="eb6e3-121">If you were working in the **Formatting and Advanced Binding** dialog box, click **OK** to return to the **Properties** window.</span></span>  
  
9. <span data-ttu-id="eb6e3-122">Se si desidera associare proprietà aggiuntive del controllo, ripetere i passaggi da 3 a 7.</span><span class="sxs-lookup"><span data-stu-id="eb6e3-122">If you want to bind additional properties of the control, repeat steps 3 through 7.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eb6e3-123">Poiché i controlli con associazione semplice visualizzare solo un singolo elemento di dati, viene in genere includere logica di navigazione in un Windows Form con controlli con associazione semplice.</span><span class="sxs-lookup"><span data-stu-id="eb6e3-123">Because simple-bound controls show only a single data element, it is very typical to include navigation logic in a Windows Form with simple-bound controls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb6e3-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb6e3-124">See Also</span></span>  
 <xref:System.Windows.Forms.Binding>  
 [<span data-ttu-id="eb6e3-125">Data binding in Windows Form</span><span class="sxs-lookup"><span data-stu-id="eb6e3-125">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="eb6e3-126">Data binding e Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eb6e3-126">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
