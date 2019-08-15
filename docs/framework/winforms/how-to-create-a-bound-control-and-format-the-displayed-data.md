---
title: 'Procedura: Creare un controllo con associazione e formattare i dati visualizzati'
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: 052e619acb23fb2e25f42daf7b4eaaacb0688f31
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039432"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a><span data-ttu-id="97d6a-102">Procedura: Creare un controllo con associazione e formattare i dati visualizzati</span><span class="sxs-lookup"><span data-stu-id="97d6a-102">How to: Create a Bound Control and Format the Displayed Data</span></span>

<span data-ttu-id="97d6a-103">Con Windows Forms data binding, è possibile formattare i dati visualizzati in un controllo associato a dati utilizzando la finestra di dialogo **formattazione e associazione avanzata** .</span><span class="sxs-lookup"><span data-stu-id="97d6a-103">With Windows Forms data binding, you can format the data displayed in a data-bound control by using the **Formatting and Advanced Binding** dialog box.</span></span>


### <a name="to-bind-a-control-and-format-the-displayed-data"></a><span data-ttu-id="97d6a-104">Per associare un controllo e formattare i dati visualizzati</span><span class="sxs-lookup"><span data-stu-id="97d6a-104">To bind a control and format the displayed data</span></span>

1. <span data-ttu-id="97d6a-105">Effettuare una connessione a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="97d6a-105">Connect to a data source.</span></span>

     <span data-ttu-id="97d6a-106">Per ulteriori informazioni, vedere [connessione a un'origine dati](../data/adonet/connecting-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="97d6a-106">For more information, see [Connecting to a Data Source](../data/adonet/connecting-to-a-data-source.md).</span></span>

2. <span data-ttu-id="97d6a-107">Nel form selezionare il controllo e aprire la finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="97d6a-107">In the form, select the control, and then open the Properties window.</span></span>

3. <span data-ttu-id="97d6a-108">Espandere la proprietà **(DataBindings)** , quindi nella casella **(avanzate)** fare clic sul pulsante con i puntini![di sospensione (pulsante con i puntini di sospensione (...)](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png)nella finestra proprietà di Visual Studio.) per visualizzare la **formattazione e la funzionalità avanzate** Finestra di dialogo Binding, che include un elenco completo delle proprietà per il controllo.</span><span class="sxs-lookup"><span data-stu-id="97d6a-108">Expand the **(DataBindings)** property, and then in the **(Advanced)** box, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png)) to display the **Formatting and Advanced Binding** dialog box, which has a complete list of properties for that control.</span></span>

4. <span data-ttu-id="97d6a-109">Selezionare la proprietà che si desidera associare, quindi fare clic sulla freccia **Binding** .</span><span class="sxs-lookup"><span data-stu-id="97d6a-109">Select the property you want to bind, and then click the **Binding** arrow.</span></span>

     <span data-ttu-id="97d6a-110">Verrà visualizzato un elenco di origini dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="97d6a-110">A list of available data sources is displayed.</span></span>

5. <span data-ttu-id="97d6a-111">Espandere l'origine dati da associare fino a quando non vengono visualizzati i dati desiderati.</span><span class="sxs-lookup"><span data-stu-id="97d6a-111">Expand the data source you want to bind to until you find the single data element you want.</span></span>

     <span data-ttu-id="97d6a-112">Se ad esempio si vuole associare il valore di una colonna in una tabella di set di dati, espandere il nome del set di dati, quindi espandere il nome della tabella per visualizzare i nomi delle colonne.</span><span class="sxs-lookup"><span data-stu-id="97d6a-112">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>

6. <span data-ttu-id="97d6a-113">Fare clic sul nome dell'elemento a cui effettuare il binding.</span><span class="sxs-lookup"><span data-stu-id="97d6a-113">Click the name of an element to bind to.</span></span>

7. <span data-ttu-id="97d6a-114">Nella casella **tipo formato** selezionare il formato che si desidera applicare ai dati visualizzati nel controllo.</span><span class="sxs-lookup"><span data-stu-id="97d6a-114">In the **Format type** box, click the format you want to apply to the data displayed in the control.</span></span>

     <span data-ttu-id="97d6a-115">In ogni caso, è possibile specificare il valore visualizzato nel controllo se l'origine dati contiene <xref:System.DBNull>.</span><span class="sxs-lookup"><span data-stu-id="97d6a-115">In every case, you can specify the value displayed in the control if the data source contains <xref:System.DBNull>.</span></span> <span data-ttu-id="97d6a-116">In caso contrario, le opzioni variano leggermente, a seconda del tipo di formato scelto.</span><span class="sxs-lookup"><span data-stu-id="97d6a-116">Otherwise, the options vary slightly, depending on the format type you choose.</span></span> <span data-ttu-id="97d6a-117">La tabella seguente illustra i tipi di formato e le opzioni.</span><span class="sxs-lookup"><span data-stu-id="97d6a-117">The following table shows the format types and options.</span></span>

    |<span data-ttu-id="97d6a-118">Tipo di formato</span><span class="sxs-lookup"><span data-stu-id="97d6a-118">Format type</span></span>|<span data-ttu-id="97d6a-119">Opzione di formattazione</span><span class="sxs-lookup"><span data-stu-id="97d6a-119">Formatting option</span></span>|
    |-----------------|-----------------------|
    |<span data-ttu-id="97d6a-120">Nessuna formattazione</span><span class="sxs-lookup"><span data-stu-id="97d6a-120">No Formatting</span></span>|<span data-ttu-id="97d6a-121">Nessuna opzione.</span><span class="sxs-lookup"><span data-stu-id="97d6a-121">No options.</span></span>|
    |<span data-ttu-id="97d6a-122">Numeric</span><span class="sxs-lookup"><span data-stu-id="97d6a-122">Numeric</span></span>|<span data-ttu-id="97d6a-123">Specificare il numero di posizioni decimali usando il controllo di scorrimento **posizioni** decimali.</span><span class="sxs-lookup"><span data-stu-id="97d6a-123">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="97d6a-124">Currency</span><span class="sxs-lookup"><span data-stu-id="97d6a-124">Currency</span></span>|<span data-ttu-id="97d6a-125">Specificare il numero di posizioni decimali usando il controllo di scorrimento **posizioni** decimali.</span><span class="sxs-lookup"><span data-stu-id="97d6a-125">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="97d6a-126">Data/Ora</span><span class="sxs-lookup"><span data-stu-id="97d6a-126">Date Time</span></span>|<span data-ttu-id="97d6a-127">Selezionare la modalità di visualizzazione della data e dell'ora selezionando uno degli elementi nella casella di selezione **tipo** .</span><span class="sxs-lookup"><span data-stu-id="97d6a-127">Select how the date and time should be displayed by selecting one of the items in the **Type** selection box.</span></span>|
    |<span data-ttu-id="97d6a-128">Scientifico</span><span class="sxs-lookup"><span data-stu-id="97d6a-128">Scientific</span></span>|<span data-ttu-id="97d6a-129">Specificare il numero di posizioni decimali usando il controllo di scorrimento **posizioni** decimali.</span><span class="sxs-lookup"><span data-stu-id="97d6a-129">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="97d6a-130">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="97d6a-130">Custom</span></span>|<span data-ttu-id="97d6a-131">Specificare una stringa di formato personalizzata.</span><span class="sxs-lookup"><span data-stu-id="97d6a-131">Specify a custom format string using.</span></span><br /><br /> <span data-ttu-id="97d6a-132">Per altre informazioni, vedere [Formattazione di tipi](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="97d6a-132">For more information, see [Formatting Types](../../standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="97d6a-133">**Nota:**  Le stringhe di formato personalizzate non eseguono sempre correttamente il round trip tra l'origine dati e il controllo associato.</span><span class="sxs-lookup"><span data-stu-id="97d6a-133">**Note:**  Custom format strings are not guaranteed to successfully round trip between the data source and bound control.</span></span> <span data-ttu-id="97d6a-134">Gestire invece l'evento <xref:System.Windows.Forms.Binding.Parse> o <xref:System.Windows.Forms.Binding.Format> per l'associazione e applicare la formattazione personalizzata nel codice di gestione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="97d6a-134">Instead handle the <xref:System.Windows.Forms.Binding.Parse> or <xref:System.Windows.Forms.Binding.Format> event for the binding and apply custom formatting in the event-handling code.</span></span>|

8. <span data-ttu-id="97d6a-135">Fare clic su **OK** per chiudere la finestra di dialogo **formattazione e associazione avanzata** e tornare al finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="97d6a-135">Click **OK** to close the **Formatting and Advanced Binding** dialog box and return to the Properties window.</span></span>

## <a name="see-also"></a><span data-ttu-id="97d6a-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97d6a-136">See also</span></span>

- [<span data-ttu-id="97d6a-137">Procedura: Creare un controllo con associazione semplice in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="97d6a-137">How to: Create a Simple-Bound Control on a Windows Form</span></span>](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [<span data-ttu-id="97d6a-138">Convalida dell'input utente in Windows Form</span><span class="sxs-lookup"><span data-stu-id="97d6a-138">User Input Validation in Windows Forms</span></span>](user-input-validation-in-windows-forms.md)
- [<span data-ttu-id="97d6a-139">Data binding in Windows Form</span><span class="sxs-lookup"><span data-stu-id="97d6a-139">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
