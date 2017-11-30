---
title: 'Procedura: creare un controllo con associazione e formattare i dati visualizzati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a8c2836d841215ed3ca8e04461b1298cd41287de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a><span data-ttu-id="0e7fb-102">Procedura: creare un controllo con associazione e formattare i dati visualizzati</span><span class="sxs-lookup"><span data-stu-id="0e7fb-102">How to: Create a Bound Control and Format the Displayed Data</span></span>
<span data-ttu-id="0e7fb-103">Con l'associazione di dati di Windows Form, è possibile formattare i dati visualizzati in un controllo con associazione a dati mediante il **formattazione e associazione avanzata** la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-103">With Windows Forms data binding, you can format the data displayed in a data-bound control by using the **Formatting and Advanced Binding** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e7fb-104">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0e7fb-105">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="0e7fb-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0e7fb-106">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="0e7fb-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-bind-a-control-and-format-the-displayed-data"></a><span data-ttu-id="0e7fb-107">Per associare un controllo e formattare i dati visualizzati</span><span class="sxs-lookup"><span data-stu-id="0e7fb-107">To bind a control and format the displayed data</span></span>  
  
1.  <span data-ttu-id="0e7fb-108">Effettuare una connessione a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-108">Connect to a data source.</span></span>  
  
     <span data-ttu-id="0e7fb-109">Per ulteriori informazioni, vedere [la connessione a un'origine dati](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="0e7fb-109">For more information, see [Connecting to a Data Source](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span></span>  
  
2.  <span data-ttu-id="0e7fb-110">Nel form selezionare il controllo e aprire la finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-110">In the form, select the control, and then open the Properties window.</span></span>  
  
3.  <span data-ttu-id="0e7fb-111">Espandere il **(DataBindings)** proprietà e quindi la **(avanzate)** fare clic sul pulsante con i puntini di sospensione (![schermata VisualStudioEllipsesButton] (../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) per visualizzare il **formattazione e associazione avanzata** nella finestra di dialogo dispone di un elenco completo delle proprietà per tale controllo.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-111">Expand the **(DataBindings)** property, and then in the **(Advanced)** box, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) to display the **Formatting and Advanced Binding** dialog box, which has a complete list of properties for that control.</span></span>  
  
4.  <span data-ttu-id="0e7fb-112">Selezionare la proprietà che si desidera associare e quindi fare clic su di **associazione** freccia.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-112">Select the property you want to bind, and then click the **Binding** arrow.</span></span>  
  
     <span data-ttu-id="0e7fb-113">Verrà visualizzato un elenco di origini dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-113">A list of available data sources is displayed.</span></span>  
  
5.  <span data-ttu-id="0e7fb-114">Espandere l'origine dati da associare fino a quando non vengono visualizzati i dati desiderati.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-114">Expand the data source you want to bind to until you find the single data element you want.</span></span>  
  
     <span data-ttu-id="0e7fb-115">Se ad esempio si vuole associare il valore di una colonna in una tabella di set di dati, espandere il nome del set di dati, quindi espandere il nome della tabella per visualizzare i nomi delle colonne.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-115">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>  
  
6.  <span data-ttu-id="0e7fb-116">Fare clic sul nome dell'elemento a cui effettuare il binding.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-116">Click the name of an element to bind to.</span></span>  
  
7.  <span data-ttu-id="0e7fb-117">Nel **il tipo di formato** fare clic sul formato da applicare ai dati visualizzati nel controllo.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-117">In the **Format type** box, click the format you want to apply to the data displayed in the control.</span></span>  
  
     <span data-ttu-id="0e7fb-118">In ogni caso, è possibile specificare il valore visualizzato nel controllo se l'origine dati contiene <xref:System.DBNull>.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-118">In every case, you can specify the value displayed in the control if the data source contains <xref:System.DBNull>.</span></span> <span data-ttu-id="0e7fb-119">In caso contrario, le opzioni variano leggermente, a seconda del tipo di formato scelto.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-119">Otherwise, the options vary slightly, depending on the format type you choose.</span></span> <span data-ttu-id="0e7fb-120">La tabella seguente illustra i tipi di formato e le opzioni.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-120">The following table shows the format types and options.</span></span>  
  
    |<span data-ttu-id="0e7fb-121">Tipo di formato</span><span class="sxs-lookup"><span data-stu-id="0e7fb-121">Format type</span></span>|<span data-ttu-id="0e7fb-122">Opzione di formattazione</span><span class="sxs-lookup"><span data-stu-id="0e7fb-122">Formatting option</span></span>|  
    |-----------------|-----------------------|  
    |<span data-ttu-id="0e7fb-123">Nessuna formattazione</span><span class="sxs-lookup"><span data-stu-id="0e7fb-123">No Formatting</span></span>|<span data-ttu-id="0e7fb-124">Nessuna opzione.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-124">No options.</span></span>|  
    |<span data-ttu-id="0e7fb-125">Numerico</span><span class="sxs-lookup"><span data-stu-id="0e7fb-125">Numeric</span></span>|<span data-ttu-id="0e7fb-126">Specificare il numero di posizioni decimali utilizzando **decimali** controllo di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-126">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="0e7fb-127">Valuta</span><span class="sxs-lookup"><span data-stu-id="0e7fb-127">Currency</span></span>|<span data-ttu-id="0e7fb-128">Specificare il numero di posizioni decimali utilizzando **decimali** controllo di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-128">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="0e7fb-129">Data/Ora</span><span class="sxs-lookup"><span data-stu-id="0e7fb-129">Date Time</span></span>|<span data-ttu-id="0e7fb-130">Selezionare come data e ora deve essere visualizzate selezionando uno degli elementi di **tipo** nella casella di selezione.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-130">Select how the date and time should be displayed by selecting one of the items in the **Type** selection box.</span></span>|  
    |<span data-ttu-id="0e7fb-131">Scientifico</span><span class="sxs-lookup"><span data-stu-id="0e7fb-131">Scientific</span></span>|<span data-ttu-id="0e7fb-132">Specificare il numero di posizioni decimali utilizzando **decimali** controllo di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-132">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="0e7fb-133">Custom (Personalizzati)</span><span class="sxs-lookup"><span data-stu-id="0e7fb-133">Custom</span></span>|<span data-ttu-id="0e7fb-134">Specificare una stringa di formato personalizzata.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-134">Specify a custom format string using.</span></span><br /><br /> <span data-ttu-id="0e7fb-135">Per ulteriori informazioni, vedere [formattazione dei tipi di](../../../docs/standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="0e7fb-135">For more information, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="0e7fb-136">**Nota:** stringhe di formato personalizzate non sono garantite correttamente il round trip tra l'origine dati e il controllo associato.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-136">**Note:**  Custom format strings are not guaranteed to successfully round trip between the data source and bound control.</span></span> <span data-ttu-id="0e7fb-137">Gestire invece l'evento <xref:System.Windows.Forms.Binding.Parse> o <xref:System.Windows.Forms.Binding.Format> per il binding e applicare la formattazione personalizzata nel codice di gestione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-137">Instead handle the <xref:System.Windows.Forms.Binding.Parse> or <xref:System.Windows.Forms.Binding.Format> event for the binding and apply custom formatting in the event-handling code.</span></span>|  
  
8.  <span data-ttu-id="0e7fb-138">Fare clic su **OK** per chiudere la **formattazione e associazione avanzata** la finestra di dialogo e tornare alla finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="0e7fb-138">Click **OK** to close the **Formatting and Advanced Binding** dialog box and return to the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e7fb-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e7fb-139">See Also</span></span>  
 [<span data-ttu-id="0e7fb-140">Procedura: Creare un controllo con associazione semplice in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="0e7fb-140">How to: Create a Simple-Bound Control on a Windows Form</span></span>](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)  
 [<span data-ttu-id="0e7fb-141">Convalida dell'input utente in Windows Form</span><span class="sxs-lookup"><span data-stu-id="0e7fb-141">User Input Validation in Windows Forms</span></span>](../../../docs/framework/winforms/user-input-validation-in-windows-forms.md)  
 [<span data-ttu-id="0e7fb-142">Data binding in Windows Form</span><span class="sxs-lookup"><span data-stu-id="0e7fb-142">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
