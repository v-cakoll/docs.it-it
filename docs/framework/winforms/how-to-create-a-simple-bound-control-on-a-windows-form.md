---
title: 'Procedura: creare un controllo con associazione semplice in un Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 887f5cd89e52cf91c4e18fab5c97f82cba9a5b85
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a><span data-ttu-id="efc74-102">Procedura: creare un controllo con associazione semplice in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="efc74-102">How to: Create a Simple-Bound Control on a Windows Form</span></span>
<span data-ttu-id="efc74-103">Con *associazione semplice*, è possibile visualizzare un singolo elemento dati, ad esempio un valore di colonna da una tabella di set di dati, in un controllo.</span><span class="sxs-lookup"><span data-stu-id="efc74-103">With *simple binding*, you can display a single data element, such as a column value from a dataset table, in a control.</span></span> <span data-ttu-id="efc74-104">È possibile un'associazione semplice di qualsiasi proprietà di un controllo a un valore di dati.</span><span class="sxs-lookup"><span data-stu-id="efc74-104">You can simple-bind any property of a control to a data value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="efc74-105">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="efc74-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="efc74-106">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="efc74-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="efc74-107">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="efc74-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-simple-bind-a-control"></a><span data-ttu-id="efc74-108">Per un controllo con associazione a semplice</span><span class="sxs-lookup"><span data-stu-id="efc74-108">To simple-bind a control</span></span>  
  
1.  <span data-ttu-id="efc74-109">Effettuare una connessione a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="efc74-109">Connect to a data source.</span></span> <span data-ttu-id="efc74-110">Per ulteriori informazioni, vedere [la connessione a un'origine dati](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="efc74-110">For more information, see [Connecting to a Data Source](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span></span>  
  
2.  <span data-ttu-id="efc74-111">Selezionare il controllo nel form e visualizzare il **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="efc74-111">In the form, select the control and display the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="efc74-112">Espandere il **(DataBindings)** proprietà.</span><span class="sxs-lookup"><span data-stu-id="efc74-112">Expand the **(DataBindings)** property.</span></span>  
  
     <span data-ttu-id="efc74-113">Le proprietà più frequentemente associate vengono visualizzate sotto il **(DataBindings)** proprietà.</span><span class="sxs-lookup"><span data-stu-id="efc74-113">The properties most often bound are displayed underneath the **(DataBindings)** property.</span></span> <span data-ttu-id="efc74-114">Ad esempio, nella maggior parte dei controlli, la **testo** proprietà è associata più di frequente.</span><span class="sxs-lookup"><span data-stu-id="efc74-114">For example, in most controls, the **Text** property is most frequently bound.</span></span>  
  
4.  <span data-ttu-id="efc74-115">Se la proprietà che si desidera associare non fa parte di più comunemente associate, fare clic su di **i puntini di sospensione** pulsante (![schermata VisualStudioEllipsesButton](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton") ) nei **(avanzate)** casella per visualizzare il **formattazione e associazione avanzata** la finestra di dialogo con un elenco completo delle proprietà per tale controllo.</span><span class="sxs-lookup"><span data-stu-id="efc74-115">If the property you want to bind is not one of the commonly bound properties, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) in the **(Advanced)** box to display the **Formatting and Advanced Binding** dialog box with a complete list of properties for that control.</span></span>  
  
5.  <span data-ttu-id="efc74-116">Selezionare la proprietà che si desidera associare e fare clic sulla freccia a discesa sotto **associazione**.</span><span class="sxs-lookup"><span data-stu-id="efc74-116">Select the property you want to bind and click the drop-down arrow under **Binding**.</span></span>  
  
     <span data-ttu-id="efc74-117">Verrà visualizzato un elenco di origini dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="efc74-117">A list of available data sources is displayed.</span></span>  
  
6.  <span data-ttu-id="efc74-118">Espandere l'origine dati da associare fino a quando non vengono visualizzati i dati desiderati.</span><span class="sxs-lookup"><span data-stu-id="efc74-118">Expand the data source you want to bind to until you find the single data element you want.</span></span> <span data-ttu-id="efc74-119">Se ad esempio si vuole associare il valore di una colonna in una tabella di set di dati, espandere il nome del set di dati, quindi espandere il nome della tabella per visualizzare i nomi delle colonne.</span><span class="sxs-lookup"><span data-stu-id="efc74-119">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>  
  
7.  <span data-ttu-id="efc74-120">Fare clic sul nome dell'elemento a cui effettuare il binding.</span><span class="sxs-lookup"><span data-stu-id="efc74-120">Click the name of an element to bind to.</span></span>  
  
8.  <span data-ttu-id="efc74-121">Se si utilizza il **formattazione e associazione avanzata** la finestra di dialogo, fare clic su **OK** per tornare al **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="efc74-121">If you were working in the **Formatting and Advanced Binding** dialog box, click **OK** to return to the **Properties** window.</span></span>  
  
9. <span data-ttu-id="efc74-122">Se si desidera associare proprietà aggiuntive del controllo, ripetere i passaggi da 3 a 7.</span><span class="sxs-lookup"><span data-stu-id="efc74-122">If you want to bind additional properties of the control, repeat steps 3 through 7.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="efc74-123">Poiché i controlli con associazione semplice visualizzare solo un singolo elemento dati, viene in genere includere logica di spostamento in un Windows Form con controlli con associazione semplice.</span><span class="sxs-lookup"><span data-stu-id="efc74-123">Because simple-bound controls show only a single data element, it is very typical to include navigation logic in a Windows Form with simple-bound controls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efc74-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efc74-124">See Also</span></span>  
 <xref:System.Windows.Forms.Binding>  
 [<span data-ttu-id="efc74-125">Data binding in Windows Form</span><span class="sxs-lookup"><span data-stu-id="efc74-125">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="efc74-126">Data binding e Windows Forms</span><span class="sxs-lookup"><span data-stu-id="efc74-126">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
