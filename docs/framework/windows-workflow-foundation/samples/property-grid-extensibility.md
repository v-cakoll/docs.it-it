---
title: Estendibilità della griglia delle proprietà-esempio WF
ms.date: 03/30/2017
ms.assetid: 3530c3a3-756d-4712-9f10-fb2897414d3a
ms.openlocfilehash: 130d8702795bccf0d5f28b5c0940bd7c25be3556
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715597"
---
# <a name="property-grid-extensibility"></a>Estendibilità della griglia delle proprietà

Uno sviluppatore può personalizzare la griglia delle proprietà visualizzata quando un'attività specificata viene selezionata all'interno della finestra di progettazione. Questa operazione può essere eseguita per creare un'esperienza di modifica dettagliata. In questo esempio viene illustrato come procedere.

## <a name="demonstrates"></a>Dimostrazione

Estensibilità della griglia delle proprietà della finestra di progettazione flussi di lavoro.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`

## <a name="discussion"></a>Discussione

Per estendere la griglia delle proprietà, uno sviluppatore dispone di opzioni per personalizzare l'aspetto inline di un editor della griglia delle proprietà o fornire una finestra di dialogo che viene visualizzata per un'area di modifica più avanzata. In questo esempio vengono illustrati due editor diversi, ovvero un editor inline e un editor della finestra di dialogo.

## <a name="inline-editor"></a>Editor inline

Nell'esempio di editor inline viene illustrato quanto segue:

- Viene creato un tipo che deriva da <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>.

- Nel costruttore, il valore <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> è impostato con un modello di dati Windows Presentation Foundation (WPF). È possibile associarlo a un modello XAML, ma in questo esempio il codice viene usato per inizializzare l'associazione dati.

- Il modello di dati dispone di un contesto dei dati di <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> dell'elemento di cui è stato eseguito il rendering nella griglia delle proprietà. Notare nel codice seguente (da CustomInlineEditor.cs) che questo contesto viene quindi associato alla proprietà `Value`.

    ```csharp
    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));
    FrameworkElementFactory slider = new FrameworkElementFactory(typeof(Slider));
    Binding sliderBinding = new Binding("Value");
    sliderBinding.Mode = BindingMode.TwoWay;
    slider.SetValue(Slider.MinimumProperty, 0.0);
    slider.SetValue(Slider.MaximumProperty, 100.0);
    slider.SetValue(Slider.ValueProperty, sliderBinding);
    stack.AppendChild(slider);
    ```

- Poiché l'attività e la finestra di progettazione sono nello stesso assembly, la registrazione degli attributi di ActivityDesigner viene completata nel costruttore statico dell'attività stessa, come illustrato nell'esempio seguente da SimpleCodeActivity.cs.

    ```csharp
    static SimpleCodeActivity()
    {
        AttributeTableBuilder builder = new AttributeTableBuilder();
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));
        MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

## <a name="dialog-editor"></a>editor finestre

Nell'esempio di editor finestre viene illustrato quanto segue:

1. Viene creato un tipo che deriva da <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>.

2. Imposta il valore <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> nel costruttore con un modello di dati WPF. Può essere creato in XAML, ma in questo esempio viene creato nel codice.

3. Il modello di dati dispone di un contesto dei dati di <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> dell'elemento di cui è stato eseguito il rendering nella griglia delle proprietà. Nel codice seguente viene quindi eseguita l'associazione alla proprietà `Value`. È importante includere inoltre un oggetto <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> per fornire il pulsante che genera la finestra di dialogo in FilePickerEditor.cs.

    ```csharp
    this.InlineEditorTemplate = new DataTemplate();

    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));
    stack.SetValue(StackPanel.OrientationProperty, Orientation.Horizontal);
    FrameworkElementFactory label = new FrameworkElementFactory(typeof(Label));
    Binding labelBinding = new Binding("Value");
    label.SetValue(Label.ContentProperty, labelBinding);
    label.SetValue(Label.MaxWidthProperty, 90.0);

    stack.AppendChild(label);

    FrameworkElementFactory editModeSwitch = new FrameworkElementFactory(typeof(EditModeSwitchButton));

    editModeSwitch.SetValue(EditModeSwitchButton.TargetEditModeProperty, PropertyContainerEditMode.Dialog);

    stack.AppendChild(editModeSwitch);

    this.InlineEditorTemplate.VisualTree = stack;
    ```

4. Viene eseguito l'override del metodo <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor.ShowDialog%2A> nel tipo di finestra di progettazione per gestire la visualizzazione della finestra di dialogo. In questo esempio viene illustrato un oggetto <xref:System.Windows.Forms.FileDialog> di base.

    ```csharp
    public override void ShowDialog(PropertyValue propertyValue, IInputElement commandSource)
    {
        Microsoft.Win32.OpenFileDialog ofd = new Microsoft.Win32.OpenFileDialog();
        if (ofd.ShowDialog() == true)
        {
            propertyValue.Value = ofd.FileName;
        }
    }
    ```

5. Poiché l'attività e la finestra di progettazione sono nello stesso assembly, la registrazione degli attributi di ActivityDesigner viene completata nel costruttore statico dell'attività stessa, come illustrato nell'esempio seguente da SimpleCodeActivity.cs.

    ```csharp
    static SimpleCodeActivity()
    {
        AttributeTableBuilder builder = new AttributeTableBuilder();
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));
        MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

## <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Compilare la soluzione, quindi aprire il file Workflow1.xaml.

2. Trascinare un **SimpleCodeActivity** dalla casella degli strumenti nell'area di disegno della finestra di progettazione.

3. Fare clic su **SimpleCodeActivity** , quindi aprire la griglia delle proprietà in cui è presente un controllo dispositivo di scorrimento e un controllo di selezione file.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`
