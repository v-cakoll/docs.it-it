---
title: 'Procedura dettagliata: Serializzazione di raccolte di tipi standard tramite DesignerSerializationVisibilityAttribute'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
ms.openlocfilehash: c8321f98b25026e32e7c69f7029f2c589d0567f7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211596"
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a><span data-ttu-id="3a945-102">Procedura dettagliata: Serializzazione di raccolte di tipi standard tramite DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="3a945-102">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>

<span data-ttu-id="3a945-103">I controlli personalizzati a volte esporrà una raccolta come una proprietà.</span><span class="sxs-lookup"><span data-stu-id="3a945-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="3a945-104">Questa procedura dettagliata illustra come usare il <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> classe per controllare la serializzazione di una raccolta in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="3a945-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="3a945-105">Applicando la <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> valore alla proprietà della raccolta assicura che la proprietà sarà serializzata.</span><span class="sxs-lookup"><span data-stu-id="3a945-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>

<span data-ttu-id="3a945-106">Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Serializzare raccolte di tipi Standard tramite DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="3a945-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3a945-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3a945-107">Prerequisites</span></span>

<span data-ttu-id="3a945-108">Per completare la procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3a945-108">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-a-control-with-a-serializable-collection"></a><span data-ttu-id="3a945-109">Creare un controllo con una raccolta serializzabile</span><span class="sxs-lookup"><span data-stu-id="3a945-109">Create a control with a serializable collection</span></span>

<span data-ttu-id="3a945-110">Il primo passaggio consiste nel creare un controllo dotato di una raccolta serializzabile come una proprietà.</span><span class="sxs-lookup"><span data-stu-id="3a945-110">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="3a945-111">È possibile modificare il contenuto di questa raccolta usando il **Editor della raccolta**, che è possibile accedere dalle **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="3a945-111">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>

1. <span data-ttu-id="3a945-112">In Visual Studio, creare un progetto libreria di controlli di Windows denominato `SerializationDemoControlLib`.</span><span class="sxs-lookup"><span data-stu-id="3a945-112">In Visual Studio, create a Windows Control Library project called `SerializationDemoControlLib`.</span></span> <span data-ttu-id="3a945-113">Per altre informazioni, vedere [modello di libreria di controllo di Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="3a945-113">For more information, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>

2. <span data-ttu-id="3a945-114">Rinominare `UserControl1` a `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="3a945-114">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="3a945-115">Per altre informazioni, vedere [rinominare un simbolo di codice e refactoring](/visualstudio/ide/reference/rename).</span><span class="sxs-lookup"><span data-stu-id="3a945-115">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

3. <span data-ttu-id="3a945-116">Nel **delle proprietà** finestra, impostare il valore della <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> proprietà `10`.</span><span class="sxs-lookup"><span data-stu-id="3a945-116">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to `10`.</span></span>

4. <span data-ttu-id="3a945-117">Sul posto un <xref:System.Windows.Forms.TextBox> controllare il `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="3a945-117">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>

5. <span data-ttu-id="3a945-118">Selezionare il controllo <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="3a945-118">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="3a945-119">Nel **proprietà** finestra, impostare le proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="3a945-119">In the **Properties** window, set the following properties.</span></span>

    |<span data-ttu-id="3a945-120">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3a945-120">Property</span></span>|<span data-ttu-id="3a945-121">Modificare in</span><span class="sxs-lookup"><span data-stu-id="3a945-121">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="3a945-122">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="3a945-122">**Multiline**</span></span>|`true`|
    |<span data-ttu-id="3a945-123">**Dock**</span><span class="sxs-lookup"><span data-stu-id="3a945-123">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|
    |<span data-ttu-id="3a945-124">**ScrollBars**</span><span class="sxs-lookup"><span data-stu-id="3a945-124">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |<span data-ttu-id="3a945-125">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="3a945-125">**ReadOnly**</span></span>|`true`|

6. <span data-ttu-id="3a945-126">Nel **Editor di codice**, dichiarare un campo di matrice di stringhe denominato `stringsValue` in `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="3a945-126">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. <span data-ttu-id="3a945-127">Definire le `Strings` proprietà di `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="3a945-127">Define the `Strings` property on the `SerializationDemoControl`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3a945-128">Il <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> valore viene usato per abilitare la serializzazione della raccolta.</span><span class="sxs-lookup"><span data-stu-id="3a945-128">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. <span data-ttu-id="3a945-129">Premere **F5** per compilare il progetto ed eseguire il controllo nel **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="3a945-129">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

9. <span data-ttu-id="3a945-130">Trovare il `Strings` proprietà nel <xref:System.Windows.Forms.PropertyGrid> delle **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="3a945-130">Find the `Strings` property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="3a945-131">Fare clic sui `Strings` proprietà, quindi fare clic sui puntini di sospensione (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) per aprire la **Editor della raccolta String**.</span><span class="sxs-lookup"><span data-stu-id="3a945-131">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>

10. <span data-ttu-id="3a945-132">Immettere più stringhe nel **Editor della raccolta String**.</span><span class="sxs-lookup"><span data-stu-id="3a945-132">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="3a945-133">È necessario separarli premendo la **invio** chiave alla fine di ogni stringa.</span><span class="sxs-lookup"><span data-stu-id="3a945-133">Separate them by pressing the **Enter** key at the end of each string.</span></span> <span data-ttu-id="3a945-134">Fare clic su **OK** dopo aver immesso le stringhe.</span><span class="sxs-lookup"><span data-stu-id="3a945-134">Click **OK** when you are finished entering strings.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3a945-135">Vengono visualizzate le stringhe immesse nella <xref:System.Windows.Forms.TextBox> del `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="3a945-135">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

## <a name="serializing-a-collection-property"></a><span data-ttu-id="3a945-136">La serializzazione di una proprietà di raccolta</span><span class="sxs-lookup"><span data-stu-id="3a945-136">Serializing a Collection Property</span></span>

<span data-ttu-id="3a945-137">Per testare il comportamento di serializzazione del controllo, si verrà posizionarlo in un form e modificare il contenuto della raccolta con il **Editor della raccolta**.</span><span class="sxs-lookup"><span data-stu-id="3a945-137">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="3a945-138">È possibile visualizzare lo stato della raccolta serializzata esaminando un file di progettazione speciale in cui il **finestra di progettazione Windows Form** emette il codice.</span><span class="sxs-lookup"><span data-stu-id="3a945-138">You can see the serialized collection state by looking at a special designer file into which the **Windows Forms Designer** emits code.</span></span>

### <a name="to-serialize-a-collection"></a><span data-ttu-id="3a945-139">Per serializzare una raccolta</span><span class="sxs-lookup"><span data-stu-id="3a945-139">To serialize a collection</span></span>

1. <span data-ttu-id="3a945-140">Aggiungere un progetto di applicazione di Windows per la soluzione.</span><span class="sxs-lookup"><span data-stu-id="3a945-140">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="3a945-141">Denominare il progetto `SerializationDemoControlTest`.</span><span class="sxs-lookup"><span data-stu-id="3a945-141">Name the project `SerializationDemoControlTest`.</span></span>

2. <span data-ttu-id="3a945-142">Nel **casella degli strumenti**, individuare la scheda denominata **Componenti SerializationDemoControlLib**.</span><span class="sxs-lookup"><span data-stu-id="3a945-142">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="3a945-143">In questa scheda, si noterà il `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="3a945-143">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="3a945-144">Per altre informazioni, vedere [Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="3a945-144">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

3. <span data-ttu-id="3a945-145">Sul posto un `SerializationDemoControl` sul form.</span><span class="sxs-lookup"><span data-stu-id="3a945-145">Place a `SerializationDemoControl` on your form.</span></span>

4. <span data-ttu-id="3a945-146">Trovare il `Strings` proprietà il **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="3a945-146">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="3a945-147">Fare clic sui `Strings` proprietà, quindi fare clic sui puntini di sospensione (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) per aprire la **Editor della raccolta String**.</span><span class="sxs-lookup"><span data-stu-id="3a945-147">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>

5. <span data-ttu-id="3a945-148">Digitare più stringhe nel **Editor della raccolta String**.</span><span class="sxs-lookup"><span data-stu-id="3a945-148">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="3a945-149">È necessario separarli premendo il tasto INVIO alla fine di ogni stringa.</span><span class="sxs-lookup"><span data-stu-id="3a945-149">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="3a945-150">Fare clic su **OK** dopo aver immesso le stringhe.</span><span class="sxs-lookup"><span data-stu-id="3a945-150">Click **OK** when you are finished entering strings.</span></span>

> [!NOTE]
> <span data-ttu-id="3a945-151">Vengono visualizzate le stringhe immesse nella <xref:System.Windows.Forms.TextBox> del `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="3a945-151">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

1. <span data-ttu-id="3a945-152">In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**.</span><span class="sxs-lookup"><span data-stu-id="3a945-152">In **Solution Explorer**, click the **Show All Files** button.</span></span>

2. <span data-ttu-id="3a945-153">Aprire il **Form1** nodo.</span><span class="sxs-lookup"><span data-stu-id="3a945-153">Open the **Form1** node.</span></span> <span data-ttu-id="3a945-154">In cui è presente un file denominato **Form1.Designer.cs** oppure **Form1**.</span><span class="sxs-lookup"><span data-stu-id="3a945-154">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="3a945-155">Si tratta del file in cui il **finestra di progettazione Windows Form** genera codice che rappresenta lo stato della fase di progettazione del form e i relativi controlli figlio.</span><span class="sxs-lookup"><span data-stu-id="3a945-155">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="3a945-156">Aprire il file nell'**editor di codice**.</span><span class="sxs-lookup"><span data-stu-id="3a945-156">Open this file in the **Code Editor**.</span></span>

3. <span data-ttu-id="3a945-157">Aprire l'area denominata **codice generato da Progettazione Form di Windows** e individuare la sezione **serializationDemoControl1**.</span><span class="sxs-lookup"><span data-stu-id="3a945-157">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="3a945-158">Di sotto di questa etichetta è il codice che rappresenta lo stato serializzato del controllo.</span><span class="sxs-lookup"><span data-stu-id="3a945-158">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="3a945-159">Le stringhe digitato nel passaggio 5 vengono visualizzate in un'assegnazione al `Strings` proprietà.</span><span class="sxs-lookup"><span data-stu-id="3a945-159">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="3a945-160">Gli esempi di codice seguente in c# e Visual Basic, visualizzare codice simile a ciò che viene visualizzato se digitato le stringhe "rosso", "arancione" e "giallo".</span><span class="sxs-lookup"><span data-stu-id="3a945-160">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

4. <span data-ttu-id="3a945-161">Nel **Editor di codice**, modificare il valore della <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> sul `Strings` proprietà <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span><span class="sxs-lookup"><span data-stu-id="3a945-161">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

5. <span data-ttu-id="3a945-162">Ricompilare la soluzione e ripetere i passaggi 3 e 4.</span><span class="sxs-lookup"><span data-stu-id="3a945-162">Rebuild the solution and repeat steps 3 and 4.</span></span>

> [!NOTE]
> <span data-ttu-id="3a945-163">In questo caso, il **finestra di progettazione Windows Form** alcuna assegnazione genera la `Strings` proprietà.</span><span class="sxs-lookup"><span data-stu-id="3a945-163">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3a945-164">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3a945-164">Next Steps</span></span>

<span data-ttu-id="3a945-165">Dopo che in grado di serializzare una raccolta di tipi standard, è consigliabile integrare un livello più profondo i controlli personalizzati nell'ambiente della fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="3a945-165">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="3a945-166">Gli argomenti seguenti descrivono come migliorare l'integrazione in fase di progettazione di controlli personalizzati:</span><span class="sxs-lookup"><span data-stu-id="3a945-166">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>

- <span data-ttu-id="3a945-167">[Architettura della fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="3a945-167">[Design-Time Architecture](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span></span>

- [<span data-ttu-id="3a945-168">Attributi nei controlli Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3a945-168">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)

- <span data-ttu-id="3a945-169">[Cenni preliminari sulla serializzazione della finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="3a945-169">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>

- [<span data-ttu-id="3a945-170">Procedura dettagliata: Creazione di un controllo di Windows Form che consente di sfruttare le funzionalità in fase di progettazione di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3a945-170">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a><span data-ttu-id="3a945-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a945-171">See also</span></span>

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- <span data-ttu-id="3a945-172">[Cenni preliminari sulla serializzazione della finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="3a945-172">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>
- <span data-ttu-id="3a945-173">[Procedura: Serializzare raccolte di tipi Standard tramite DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="3a945-173">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
- [<span data-ttu-id="3a945-174">Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="3a945-174">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
