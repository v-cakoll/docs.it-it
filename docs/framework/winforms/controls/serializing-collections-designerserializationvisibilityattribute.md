---
title: 'Procedura dettagliata: serializzazione di raccolte di tipi standard tramite DesignerSerializationVisibilityAttribute'
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
ms.openlocfilehash: 54859b3065e8e9bb9680d8b6bf7946b393f73b9f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402586"
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a><span data-ttu-id="d3691-102">Procedura dettagliata: serializzazione di raccolte di tipi standard tramite DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="d3691-102">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>
<span data-ttu-id="d3691-103">I controlli personalizzati a volte esporrà una raccolta come una proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3691-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="d3691-104">Questa procedura dettagliata illustra come usare il <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> classe per controllare la serializzazione di una raccolta in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d3691-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="d3691-105">Applicando la <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> valore alla proprietà della raccolta assicura che la proprietà sarà serializzata.</span><span class="sxs-lookup"><span data-stu-id="d3691-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>  
  
 <span data-ttu-id="d3691-106">Per copiare il codice in questo argomento come singolo listato, vedere [procedura: serializzare raccolte di tipi Standard DesignerSerializationVisibilityAttribute](https://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9).</span><span class="sxs-lookup"><span data-stu-id="d3691-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3691-107">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="d3691-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d3691-108">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="d3691-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d3691-109">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="d3691-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d3691-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d3691-110">Prerequisites</span></span>  
 <span data-ttu-id="d3691-111">Per completare questa procedura dettagliata, è necessario:</span><span class="sxs-lookup"><span data-stu-id="d3691-111">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="d3691-112">Autorizzazioni sufficienti per essere in grado di creare ed eseguire progetti di applicazione Windows Form nel computer in cui è installato Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3691-112">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-a-control-that-has-a-serializable-collection"></a><span data-ttu-id="d3691-113">Creazione di un controllo dispone di una raccolta serializzabile</span><span class="sxs-lookup"><span data-stu-id="d3691-113">Creating a Control That Has a Serializable Collection</span></span>  
 <span data-ttu-id="d3691-114">Il primo passaggio consiste nel creare un controllo dotato di una raccolta serializzabile come una proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3691-114">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="d3691-115">È possibile modificare il contenuto di questa raccolta usando il **Editor della raccolta**, che è possibile accedere dalle **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="d3691-115">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>  
  
#### <a name="to-create-a-control-with-a-serializable-collection"></a><span data-ttu-id="d3691-116">Per creare un controllo con una raccolta serializzabile</span><span class="sxs-lookup"><span data-stu-id="d3691-116">To create a control with a serializable collection</span></span>  
  
1.  <span data-ttu-id="d3691-117">Creare un progetto libreria di controlli di Windows denominato `SerializationDemoControlLib`.</span><span class="sxs-lookup"><span data-stu-id="d3691-117">Create a Windows Control Library project called `SerializationDemoControlLib`.</span></span> <span data-ttu-id="d3691-118">Per altre informazioni, vedere [modello di libreria di controllo di Windows](https://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span><span class="sxs-lookup"><span data-stu-id="d3691-118">For more information, see [Windows Control Library Template](https://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span></span>  
  
2.  <span data-ttu-id="d3691-119">Rinominare `UserControl1` a `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="d3691-119">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="d3691-120">Per altre informazioni, vedere [procedura: rinominare gli identificatori](https://msdn.microsoft.com/library/2430f732-2b70-4516-8cf6-a7bb71cc9724).</span><span class="sxs-lookup"><span data-stu-id="d3691-120">For more information, see [How to: Rename Identifiers](https://msdn.microsoft.com/library/2430f732-2b70-4516-8cf6-a7bb71cc9724).</span></span>  
  
3.  <span data-ttu-id="d3691-121">Nel **delle proprietà** finestra, impostare il valore della <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> proprietà `10`.</span><span class="sxs-lookup"><span data-stu-id="d3691-121">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to `10`.</span></span>  
  
4.  <span data-ttu-id="d3691-122">Sul posto un <xref:System.Windows.Forms.TextBox> controllare il `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="d3691-122">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>  
  
5.  <span data-ttu-id="d3691-123">Selezionare il controllo <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d3691-123">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="d3691-124">Nel **proprietà** finestra, impostare le proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="d3691-124">In the **Properties** window, set the following properties.</span></span>  
  
    |<span data-ttu-id="d3691-125">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d3691-125">Property</span></span>|<span data-ttu-id="d3691-126">Modificare in</span><span class="sxs-lookup"><span data-stu-id="d3691-126">Change to</span></span>|  
    |--------------|---------------|  
    |<span data-ttu-id="d3691-127">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="d3691-127">**Multiline**</span></span>|`true`|  
    |<span data-ttu-id="d3691-128">**Dock**</span><span class="sxs-lookup"><span data-stu-id="d3691-128">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|  
    |<span data-ttu-id="d3691-129">**Barre di scorrimento**</span><span class="sxs-lookup"><span data-stu-id="d3691-129">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|  
    |<span data-ttu-id="d3691-130">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="d3691-130">**ReadOnly**</span></span>|`true`|  
  
6.  <span data-ttu-id="d3691-131">Nel **Editor di codice**, dichiarare un campo di matrice di stringhe denominato `stringsValue` in `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="d3691-131">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>  
  
     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]  
  
7.  <span data-ttu-id="d3691-132">Definire le `Strings` proprietà di `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="d3691-132">Define the `Strings` property on the `SerializationDemoControl`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3691-133">Il <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> valore viene usato per abilitare la serializzazione della raccolta.</span><span class="sxs-lookup"><span data-stu-id="d3691-133">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>  
  
 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]  
  
1.  <span data-ttu-id="d3691-134">Per compilare il progetto ed eseguire il controllo in **UserControl Test Container**, premere F5.</span><span class="sxs-lookup"><span data-stu-id="d3691-134">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span>  
  
2.  <span data-ttu-id="d3691-135">Trovare il `Strings` proprietà nel <xref:System.Windows.Forms.PropertyGrid> delle **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="d3691-135">Find the `Strings` property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="d3691-136">Fare clic sui `Strings` proprietà, quindi fare clic sui puntini di sospensione (![schermata di VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) per aprire la **Editor della raccolta String**.</span><span class="sxs-lookup"><span data-stu-id="d3691-136">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>  
  
3.  <span data-ttu-id="d3691-137">Immettere più stringhe nel **Editor della raccolta String**.</span><span class="sxs-lookup"><span data-stu-id="d3691-137">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="d3691-138">È necessario separarli premendo il tasto INVIO alla fine di ogni stringa.</span><span class="sxs-lookup"><span data-stu-id="d3691-138">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="d3691-139">Fare clic su **OK** dopo aver immesso le stringhe.</span><span class="sxs-lookup"><span data-stu-id="d3691-139">Click **OK** when you are finished entering strings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3691-140">Vengono visualizzate le stringhe immesse nella <xref:System.Windows.Forms.TextBox> del `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="d3691-140">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>  
  
## <a name="serializing-a-collection-property"></a><span data-ttu-id="d3691-141">La serializzazione di una proprietà di raccolta</span><span class="sxs-lookup"><span data-stu-id="d3691-141">Serializing a Collection Property</span></span>  
 <span data-ttu-id="d3691-142">Per testare il comportamento di serializzazione del controllo, si verrà posizionarlo in un form e modificare il contenuto della raccolta con il **Editor della raccolta**.</span><span class="sxs-lookup"><span data-stu-id="d3691-142">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="d3691-143">È possibile visualizzare lo stato della raccolta serializzata esaminando un file di progettazione speciale, in cui il **finestra di progettazione Windows Form** emette il codice.</span><span class="sxs-lookup"><span data-stu-id="d3691-143">You can see the serialized collection state by looking at a special designer file, into which the **Windows Forms Designer** emits code.</span></span>  
  
#### <a name="to-serialize-a-collection"></a><span data-ttu-id="d3691-144">Per serializzare una raccolta</span><span class="sxs-lookup"><span data-stu-id="d3691-144">To serialize a collection</span></span>  
  
1.  <span data-ttu-id="d3691-145">Aggiungere un progetto di applicazione di Windows per la soluzione.</span><span class="sxs-lookup"><span data-stu-id="d3691-145">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="d3691-146">Denominare il progetto `SerializationDemoControlTest`.</span><span class="sxs-lookup"><span data-stu-id="d3691-146">Name the project `SerializationDemoControlTest`.</span></span>  
  
2.  <span data-ttu-id="d3691-147">Nel **casella degli strumenti**, individuare la scheda denominata **Componenti SerializationDemoControlLib**.</span><span class="sxs-lookup"><span data-stu-id="d3691-147">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="d3691-148">In questa scheda, si noterà il `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="d3691-148">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="d3691-149">Per altre informazioni, vedere [Procedura dettagliata: compilare automaticamente la casella degli strumenti con componenti personalizzati](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="d3691-149">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
3.  <span data-ttu-id="d3691-150">Sul posto un `SerializationDemoControl` sul form.</span><span class="sxs-lookup"><span data-stu-id="d3691-150">Place a `SerializationDemoControl` on your form.</span></span>  
  
4.  <span data-ttu-id="d3691-151">Trovare il `Strings` proprietà il **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="d3691-151">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="d3691-152">Fare clic sui `Strings` proprietà, quindi fare clic sui puntini di sospensione (![schermata di VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) per aprire la **Editor della raccolta String**.</span><span class="sxs-lookup"><span data-stu-id="d3691-152">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>  
  
5.  <span data-ttu-id="d3691-153">Digitare più stringhe nel **Editor della raccolta String**.</span><span class="sxs-lookup"><span data-stu-id="d3691-153">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="d3691-154">È necessario separarli premendo il tasto INVIO alla fine di ogni stringa.</span><span class="sxs-lookup"><span data-stu-id="d3691-154">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="d3691-155">Fare clic su **OK** dopo aver immesso le stringhe.</span><span class="sxs-lookup"><span data-stu-id="d3691-155">Click **OK** when you are finished entering strings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3691-156">Vengono visualizzate le stringhe immesse nella <xref:System.Windows.Forms.TextBox> del `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="d3691-156">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>  
  
1.  <span data-ttu-id="d3691-157">In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**.</span><span class="sxs-lookup"><span data-stu-id="d3691-157">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
2.  <span data-ttu-id="d3691-158">Aprire il **Form1** nodo.</span><span class="sxs-lookup"><span data-stu-id="d3691-158">Open the **Form1** node.</span></span> <span data-ttu-id="d3691-159">In cui è presente un file denominato **Form1.Designer.cs** oppure **Form1**.</span><span class="sxs-lookup"><span data-stu-id="d3691-159">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="d3691-160">Si tratta del file in cui il **finestra di progettazione Windows Form** genera codice che rappresenta lo stato della fase di progettazione del form e i relativi controlli figlio.</span><span class="sxs-lookup"><span data-stu-id="d3691-160">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="d3691-161">Aprire il file nell'**editor di codice**.</span><span class="sxs-lookup"><span data-stu-id="d3691-161">Open this file in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="d3691-162">Aprire l'area denominata **codice generato da Progettazione Form di Windows** e individuare la sezione **serializationDemoControl1**.</span><span class="sxs-lookup"><span data-stu-id="d3691-162">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="d3691-163">Di sotto di questa etichetta è il codice che rappresenta lo stato serializzato del controllo.</span><span class="sxs-lookup"><span data-stu-id="d3691-163">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="d3691-164">Le stringhe digitato nel passaggio 5 vengono visualizzate in un'assegnazione al `Strings` proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3691-164">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="d3691-165">Gli esempi di codice seguente in c# e Visual Basic, visualizzare codice simile a ciò che viene visualizzato se digitato le stringhe "rosso", "arancione" e "giallo".</span><span class="sxs-lookup"><span data-stu-id="d3691-165">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>  
  
    ```csharp  
    this.serializationDemoControl1.Strings = new string[] {  
            "red",  
            "orange",  
            "yellow"};  
    ```  
    
    ```vb  
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}  
    ```
  
4.  <span data-ttu-id="d3691-166">Nel **Editor di codice**, modificare il valore della <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> sul `Strings` proprietà <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span><span class="sxs-lookup"><span data-stu-id="d3691-166">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>  
  
    ```csharp  
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]  
    ```  
    ```vb  
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _  
    ```  
  
5. <span data-ttu-id="d3691-167">Ricompilare la soluzione e ripetere i passaggi 3 e 4.</span><span class="sxs-lookup"><span data-stu-id="d3691-167">Rebuild the solution and repeat steps 3 and 4.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3691-168">In questo caso, il **finestra di progettazione Windows Form** alcuna assegnazione genera la `Strings` proprietà.</span><span class="sxs-lookup"><span data-stu-id="d3691-168">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d3691-169">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d3691-169">Next Steps</span></span>  
 <span data-ttu-id="d3691-170">Dopo che in grado di serializzare una raccolta di tipi standard, è consigliabile integrare un livello più profondo i controlli personalizzati nell'ambiente della fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d3691-170">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="d3691-171">Gli argomenti seguenti descrivono come migliorare l'integrazione in fase di progettazione di controlli personalizzati:</span><span class="sxs-lookup"><span data-stu-id="d3691-171">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>  
  
-   [<span data-ttu-id="d3691-172">Architettura della fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="d3691-172">Design-Time Architecture</span></span>](https://msdn.microsoft.com/library/4881917b-628f-4689-b872-472e4f8a4e3a)  
  
-   [<span data-ttu-id="d3691-173">Attributi nei controlli Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d3691-173">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
  
-   [<span data-ttu-id="d3691-174">Cenni preliminari sulla serializzazione della finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="d3691-174">Designer Serialization Overview</span></span>](https://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
  
-   [<span data-ttu-id="d3691-175">Procedura dettagliata: Creazione di un controllo Windows Form che usufruisca delle funzionalità offerte da Visual Studio in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="d3691-175">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
  
## <a name="see-also"></a><span data-ttu-id="d3691-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3691-176">See Also</span></span>  
 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>  
 [<span data-ttu-id="d3691-177">Cenni preliminari sulla serializzazione della finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="d3691-177">Designer Serialization Overview</span></span>](https://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
 [<span data-ttu-id="d3691-178">Procedura: serializzare raccolte di tipi Standard tramite DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="d3691-178">How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](https://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)  
 [<span data-ttu-id="d3691-179">Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="d3691-179">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
