---
title: "Associazione di una proprietà di attività personalizzata a un controllo di progettazione"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e8061ea-10f5-407c-a31f-d0d74ce12f27
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e9edc168dc6e4111e5f2d58a62c2b0341f74aa04
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="binding-a-custom-activity-property-to-a-designer-control"></a><span data-ttu-id="5ed4f-102">Associazione di una proprietà di attività personalizzata a un controllo di progettazione</span><span class="sxs-lookup"><span data-stu-id="5ed4f-102">Binding a custom activity property to a designer control</span></span>
<span data-ttu-id="5ed4f-103">L'associazione di un controllo di progettazione casella di testo a un argomento di un'attività è abbastanza semplice; d'altra parte, l'associazione di un controllo di progettazione complesso (quale una casella combinata) a un argomento di un'attività può risultare problematica.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-103">Binding a text box designer control to an activity argument is fairly straightforward; binding a complex designer control (such as a combo box) to an activity argument may present challenges, however.</span></span> <span data-ttu-id="5ed4f-104">In questo argomento viene illustrato come associare un argomento di un'attività a un controllo casella combinata in un ActivityDesigner personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-104">This topic discusses how to bind an activity argument to a combo box control on a custom activity designer.</span></span>  
  
#### <a name="creating-the-combo-box-item-converter"></a><span data-ttu-id="5ed4f-105">Creazione del convertitore dell'elemento casella combinata</span><span class="sxs-lookup"><span data-stu-id="5ed4f-105">Creating the combo box item converter</span></span>  
  
1.  <span data-ttu-id="5ed4f-106">Creare una nuova soluzione vuota in Visual Studio 2010 denominata CustomProperty.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-106">Create a new empty solution in Visual Studio called CustomProperty.</span></span>  
  
2.  <span data-ttu-id="5ed4f-107">Creare una nuova classe denominata ComboBoxItemConverter.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-107">Create a new class called ComboBoxItemConverter.</span></span> <span data-ttu-id="5ed4f-108">Aggiungere un riferimento a System.Windows.Data e fare in modo che la classe esegua la derivazione da <xref:System.Windows.Data.IValueConverter>.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-108">Add a reference to System.Windows.Data, and have the class derive from <xref:System.Windows.Data.IValueConverter>.</span></span> <span data-ttu-id="5ed4f-109">Impostare Visual Studio in modo che implementi l'interfaccia per generare stub per `Convert` e `ConvertBack`.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-109">Have Visual Studio implement the interface to generate stubs for `Convert` and `ConvertBack`.</span></span>  
  
3.  <span data-ttu-id="5ed4f-110">Aggiungere al metodo `Convert` il seguente codice.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-110">Add the following code to the `Convert` method.</span></span> <span data-ttu-id="5ed4f-111">Questo codice converte l'oggetto <xref:System.Activities.InArgument%601> di tipo <xref:System.String> dell'attività nel valore da posizionare nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-111">This code converts the activity's <xref:System.Activities.InArgument%601> of type <xref:System.String> to the value to be placed in the designer.</span></span>  
  
    ```  
    ModelItem modelItem = value as ModelItem;  
    if (value != null)  
    {  
        InArgument<string> inArgument = modelItem.GetCurrentValue() as InArgument<string>;  
  
        if (inArgument != null)  
        {  
            Activity<string> expression = inArgument.Expression;  
            VisualBasicValue<string> vbexpression = expression as VisualBasicValue<string>;  
            Literal<string> literal = expression as Literal<string>;  
  
            if (literal != null)  
            {  
                return "\"" + literal.Value + "\"";  
            }  
            else if (vbexpression != null)  
            {  
                return vbexpression.ExpressionText;  
            }  
        }  
    }  
    return null;  
    ```  
  
     <span data-ttu-id="5ed4f-112">L'espressione nell'esempio di codice precedente può essere creata anche usando <xref:Microsoft.CSharp.Activities.CSharpValue%601> anziché <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-112">The expression in the above code snippet can also be created using <xref:Microsoft.CSharp.Activities.CSharpValue%601> instead of <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.</span></span>  
  
    ```  
    ModelItem modelItem = value as ModelItem;  
    if (value != null)  
    {  
        InArgument<string> inArgument = modelItem.GetCurrentValue() as InArgument<string>;  
  
        if (inArgument != null)  
        {  
            Activity<string> expression = inArgument.Expression;  
            CSharpValue<string> csexpression = expression as CSharpValue<string>;  
            Literal<string> literal = expression as Literal<string>;  
  
            if (literal != null)  
            {  
                return "\"" + literal.Value + "\"";  
            }  
            else if (csexpression != null)  
            {  
                return csexpression.ExpressionText;  
            }  
        }  
    }  
    return null;  
    ```  
  
4.  <span data-ttu-id="5ed4f-113">Aggiungere al metodo `ConvertBack` il seguente codice.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-113">Add the following code to the `ConvertBack` method.</span></span> <span data-ttu-id="5ed4f-114">Questo codice converte l'elemento casella combinata in ingresso nuovamente in <xref:System.Activities.InArgument%601>.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-114">This code converts the incoming combo box item back to an <xref:System.Activities.InArgument%601>.</span></span>  
  
    ```  
    // Convert combo box value to InArgument<string>  
                string itemContent = (string)((ComboBoxItem)value).Content;  
                VisualBasicValue<string> vbArgument = new VisualBasicValue<string>(itemContent);  
                InArgument<string> inArgument = new InArgument<string>(vbArgument);  
                return inArgument;  
    ```  
  
     <span data-ttu-id="5ed4f-115">L'espressione nell'esempio di codice precedente può essere creata anche usando <xref:Microsoft.CSharp.Activities.CSharpValue%601> anziché <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-115">The expression in the above code snippet can also be created using <xref:Microsoft.CSharp.Activities.CSharpValue%601> instead of <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.</span></span>  
  
    ```  
    // Convert combo box value to InArgument<string>  
                string itemContent = (string)((ComboBoxItem)value).Content;  
                CSharpValue<string> csArgument = new CSharpValue<string>(itemContent);  
                InArgument<string> inArgument = new InArgument<string>(csArgument);  
                return inArgument;  
    ```  
  
#### <a name="adding-the-comboboxitemconverter-to-the-custom-designer-of-an-activity"></a><span data-ttu-id="5ed4f-116">Aggiunta di ComboBoxItemConverter all'ActivityDesigner personalizzato</span><span class="sxs-lookup"><span data-stu-id="5ed4f-116">Adding the ComboBoxItemConverter to the custom designer of an activity</span></span>  
  
1.  <span data-ttu-id="5ed4f-117">Aggiungere un nuovo elemento al progetto.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-117">Add a new item to the project.</span></span> <span data-ttu-id="5ed4f-118">Nella finestra di dialogo Nuovo elemento, selezionare il nodo Flusso di lavoro, quindi selezionare ActivityDesigner come tipo del nuovo elemento.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-118">In the New Item dialog, select the Workflow node and select Activity Designer as the type of the new item.</span></span> <span data-ttu-id="5ed4f-119">Denominare l'elemento CustomPropertyDesigner.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-119">Name the item CustomPropertyDesigner.</span></span>  
  
2.  <span data-ttu-id="5ed4f-120">Aggiungere una casella combinata alla nuova finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-120">Add a Combo Box to the new designer.</span></span> <span data-ttu-id="5ed4f-121">Nella proprietà Items aggiungere un paio di elementi alla casella combinata, con i valori di contenuto di "Item1" e 'Item2."</span><span class="sxs-lookup"><span data-stu-id="5ed4f-121">In the Items property, add a couple of items to the combo box, with Content values of "Item1" and 'Item2".</span></span>  
  
3.  <span data-ttu-id="5ed4f-122">Modificare il codice XAML della casella combinata in modo da aggiungere il nuovo convertitore di elementi come convertitore di elementi da usare per la casella combinata.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-122">Modify the XAML of the combo box to add the new item converter as the item converter to be used for the combo box.</span></span> <span data-ttu-id="5ed4f-123">Il convertitore viene aggiunto come risorsa nel segmento ActivityDesigner.Resources e specifica il convertitore nell'attributo Converter di <xref:System.Windows.Controls.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-123">The converter is added as a resource in the ActivityDesigner.Resources segment, and specifies the converter in the Converter attribute for the <xref:System.Windows.Controls.ComboBox>.</span></span> <span data-ttu-id="5ed4f-124">Notare che lo spazio dei nomi del progetto viene specificato negli attributi degli spazi dei nomi di ActivityDesigner; se la finestra di progettazione deve essere usata in un progetto diverso, questo spazio dei nomi dovrà essere modificato.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-124">Note that the namespace of the project is specified in the namespaces attributes for the activity designer; if the designer is to be used in a different project, this namespace will need to be changed.</span></span>  
  
    ```  
    <sap:ActivityDesigner x:Class="CustomProperty.CustomPropertyDesigner"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:c="clr-namespace:CustomProperty"  
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"  
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">  
  
        <sap:ActivityDesigner.Resources>  
            <ResourceDictionary>  
                <c:ComboBoxItemConverter x:Key="comboBoxItemConverter"/>  
            </ResourceDictionary>  
        </sap:ActivityDesigner.Resources>  
        <Grid>  
            <ComboBox SelectedValue="{Binding Path=ModelItem.Text, Mode=TwoWay, Converter={StaticResource comboBoxItemConverter}}"  Height="23" HorizontalAlignment="Left" Margin="132,5,0,0" Name="comboBox1" VerticalAlignment="Top" Width="120" ItemsSource="{Binding}">  
                <ComboBoxItem>item1</ComboBoxItem>  
                <ComboBoxItem>item2</ComboBoxItem>  
            </ComboBox>  
        </Grid>  
    </sap:ActivityDesigner>  
    ```  
  
4.  <span data-ttu-id="5ed4f-125">Creare un nuovo elemento di tipo <xref:System.Activities.CodeActivity>.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-125">Create a new item of type <xref:System.Activities.CodeActivity>.</span></span> <span data-ttu-id="5ed4f-126">Il codice predefinito creato dall'IDE per l'attività sarà sufficiente per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-126">The default code created by the IDE for the activity will be sufficient for this example.</span></span>  
  
5.  <span data-ttu-id="5ed4f-127">Aggiungere l'attributo seguente alla definizione di classe:</span><span class="sxs-lookup"><span data-stu-id="5ed4f-127">Add the following attribute to the class definition:</span></span>  
  
    ```  
    [Designer(typeof(CustomPropertyDesigner))]  
    ```  
  
     <span data-ttu-id="5ed4f-128">Con questa riga si associa la nuova finestra di progettazione alla nuova classe.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-128">This line associates the new designer with the new class.</span></span>  
  
 <span data-ttu-id="5ed4f-129">La nuova attività dovrebbe ora essere associata alla finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-129">The new activity should now be associated with the designer.</span></span> <span data-ttu-id="5ed4f-130">Per testare la nuova attività, aggiungerla a un flusso di lavoro e impostare la casella combinata sui due valori.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-130">To test the new activity, add it to a workflow, and set the combo box to the two values.</span></span> <span data-ttu-id="5ed4f-131">La finestra delle proprietà dovrebbe essere aggiornata per riflettere il valore della casella combinata.</span><span class="sxs-lookup"><span data-stu-id="5ed4f-131">The properties window should update to reflect the combo box value.</span></span>
