---
title: "Estensibilità della griglia delle proprietà"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3530c3a3-756d-4712-9f10-fb2897414d3a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e3069e97a1696b37d56728eb86161cc2487dfdfa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="property-grid-extensibliity"></a>Estensibilità della griglia delle proprietà
Uno sviluppatore può personalizzare la griglia delle proprietà visualizzata quando un'attività specificata viene selezionata all'interno della finestra di progettazione. Questa operazione può essere eseguita per creare un'esperienza di modifica dettagliata. In questo esempio viene illustrato come procedere.  
  
## <a name="demonstrates"></a>Dimostrazione  
 Estensibilità della griglia delle proprietà della finestra di progettazione flussi di lavoro.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`  
  
## <a name="discussion"></a>Discussione  
 Per estendere la griglia delle proprietà, uno sviluppatore dispone di opzioni per personalizzare l'aspetto inline di un editor della griglia delle proprietà o fornire una finestra di dialogo che viene visualizzata per un'area di modifica più avanzata. In questo esempio vengono illustrati due editor diversi, ovvero un editor inline e un editor della finestra di dialogo.  
  
## <a name="inline-editor"></a>Editor inline  
 Nell'esempio di editor inline viene illustrato quanto segue:  
  
-   Viene creato un tipo che deriva da <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>.  
  
-   Nel costruttore, il valore <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> viene impostato con un modello di dati [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)]. È possibile associarlo a un modello XAML, ma in questo esempio il codice viene usato per inizializzare l'associazione dati.  
  
-   Il modello di dati dispone di un contesto dei dati di <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> dell'elemento di cui è stato eseguito il rendering nella griglia delle proprietà. Notare nel codice seguente (da CustomInlineEditor.cs) che questo contesto viene quindi associato alla proprietà `Value`.  
  
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
  
-   Poiché l'attività e la finestra di progettazione sono nello stesso assembly, la registrazione degli attributi di ActivityDesigner viene completata nel costruttore statico dell'attività stessa, come illustrato nell'esempio seguente da SimpleCodeActivity.cs.  
  
    ```  
    static SimpleCodeActivity()  
    {  
        AttributeTableBuilder builder = new AttributeTableBuilder();  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));  
        MetadataStore.AddAttributeTable(builder.CreateTable());  
    }  
    ```  
  
## <a name="dialog-editor"></a>Editor finestre  
 Nell'esempio di editor finestre viene illustrato quanto segue:  
  
1.  Viene creato un tipo che deriva da <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>.  
  
2.  Viene impostato il valore <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> nel costruttore con un modello di dati [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]. Può essere creato in XAML, ma in questo esempio viene creato nel codice.  
  
3.  Il modello di dati dispone di un contesto dei dati di <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> dell'elemento di cui è stato eseguito il rendering nella griglia delle proprietà. Nel codice seguente viene quindi eseguita l'associazione alla proprietà `Value`. È importante includere inoltre un oggetto <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> per fornire il pulsante che genera la finestra di dialogo in FilePickerEditor.cs.  
  
    ```  
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
  
4.  Esegue l'override di <!--zz <xref:Microsoft.Windows.Design.PropertyEditing.ShowDialog%2A>--> `Microsoft.Windows.Design.PropertyEditing.ShowDialog` metodo nel tipo di finestra di progettazione per gestire la visualizzazione della finestra di dialogo. In questo esempio viene illustrato un oggetto <xref:System.Windows.Forms.FileDialog> di base.  
  
    ```  
    public override void ShowDialog(PropertyValue propertyValue, IInputElement commandSource)  
    {  
        Microsoft.Win32.OpenFileDialog ofd = new Microsoft.Win32.OpenFileDialog();  
        if (ofd.ShowDialog() == true)  
        {  
            propertyValue.Value = ofd.FileName;  
        }  
    }  
    ```  
  
5.  Poiché l'attività e la finestra di progettazione sono nello stesso assembly, la registrazione degli attributi di ActivityDesigner viene completata nel costruttore statico dell'attività stessa, come illustrato nell'esempio seguente da SimpleCodeActivity.cs.  
  
    ```  
    static SimpleCodeActivity()  
    {  
        AttributeTableBuilder builder = new AttributeTableBuilder();  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));  
        MetadataStore.AddAttributeTable(builder.CreateTable());  
    }  
    ```  
  
## <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Compilare la soluzione, quindi aprire il file Workflow1.xaml.  
  
2.  Trascinare un **SimpleCodeActivity** dalla casella degli strumenti nell'area di disegno della finestra di progettazione.  
  
3.  Fare clic su di **SimpleCodeActivity** e quindi aprire la griglia delle proprietà in cui è presente un controllo dispositivo di scorrimento e un file di controllo di selezione.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`
