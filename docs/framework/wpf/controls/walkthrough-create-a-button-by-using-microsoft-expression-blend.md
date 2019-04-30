---
title: 'Procedura dettagliata: Creare un pulsante usando Microsoft Expression Blend'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
- converting [WPF], shape to button
- Expression Blend [WPF Designer]
ms.assetid: ff5037c2-bba7-4cae-8abb-6475b686c48e
ms.openlocfilehash: 3cf9d133aee5a2c3d93c1a464c96fdaebcf230f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018260"
---
# <a name="walkthrough-create-a-button-by-using-microsoft-expression-blend"></a>Procedura dettagliata: Creare un pulsante usando Microsoft Expression Blend
Questa procedura dettagliata viene illustrato il processo di creazione di un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] pulsante personalizzato usando Microsoft Expression Blend.  
  
> [!IMPORTANT]
>  Microsoft Expression Blend funziona generando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] che viene quindi compilata per rendere il programma eseguibile. Se si preferisce lavorare con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] direttamente, è disponibile un'altra procedura dettagliata che consente di creare la stessa applicazione come questa usando uno [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] con Visual Studio anziché di Blend. Visualizzare [creare un pulsante usando XAML](walkthrough-create-a-button-by-using-xaml.md) per altre informazioni.  
  
 La figura seguente mostra il pulsante personalizzato che verrà creato.  
  
 ![Pulsante personalizzato che si creeranno](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")  
  
## <a name="convert-a-shape-to-a-button"></a>Convertire una forma in un pulsante  
 Nella prima parte di questa procedura dettagliata si crea l'aspetto del pulsante personalizzato. A tale scopo, è prima di tutto convertire un rettangolo a un pulsante. È quindi aggiungere altre forme per il modello del pulsante, la creazione di un pulsante dall'aspetto professionale più complesso. Perché non inizia con un pulsante normale e personalizzarlo? Poiché un pulsante ha funzionalità incorporate che non è necessario; per i pulsanti personalizzati, è più semplice iniziare con un rettangolo.  
  
#### <a name="to-create-a-new-project-in-expression-blend"></a>Per creare un nuovo progetto in Expression Blend  
  
1. Avvia Expression Blend. (Fare clic su **avviare**, scegliere **tutti i programmi**, scegliere **Microsoft Expression**, quindi fare clic su **Microsoft Expression Blend**.)  
  
2. Ottimizzare l'applicazione se necessario.  
  
3. Scegliere **Nuovo progetto** dal menu **File**.  
  
4. Selezionare **applicazione Standard (.exe)**.  
  
5. Denominare il progetto `CustomButton` e premere **OK**.  
  
 A questo punto si dispone di uno spazio vuoto [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] progetto. È possibile premere F5 per eseguire l'applicazione. Come è prevedibile, l'applicazione è costituita da solo una finestra vuota. Successivamente, si crea un rettangolo arrotondato e convertirlo in un pulsante.  
  
#### <a name="to-convert-a-rectangle-to-a-button"></a>Per convertire un rettangolo a un pulsante  
  
1. **Impostare la proprietà dello sfondo sul nero:** Selezionare la finestra, fare clic sui **scheda delle proprietà**e impostare le <xref:System.Windows.Controls.Control.Background%2A> proprietà `Black`.  
  
     ![Come impostare lo sfondo di un pulsante sul nero](./media/custom-button-blend-changebackground.png "custom_button_blend_ChangeBackground")  
  
2. **Disegna un rettangolo circa le dimensioni di un pulsante nella finestra:** Selezionare lo strumento rettangolo nel pannello a sinistra dello strumento e trascinare il rettangolo nella finestra.  
  
     ![Come disegnare un rettangolo](./media/custom-button-blend-drawrect.png "custom_button_blend_DrawRect")  
  
3. **Arrotondare gli angoli del rettangolo di:** Trascinare i punti di controllo del rettangolo oppure impostare direttamente la <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> e <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> proprietà. Impostare i valori delle <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> e <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> su 20.  
  
     ![Come rendere gli angoli di un rettangolo arrotondato](./media/custom-button-blend-roundcorners.png "custom_button_blend_RoundCorners")  
  
4. **Modificare il rettangolo in un pulsante:** Selezionare il rettangolo. Nel **Tools** menu, fare clic su **Crea pulsante**.  
  
     ![Come rendere una forma in un pulsante](./media/custom-button-blend-makebutton.png "custom_button_blend_MakeButton")  
  
5. **Specificare l'ambito dello stile o modello:** Viene visualizzata una finestra di dialogo simile alla seguente.  
  
     ![La finestra di dialogo "Crea risorsa stile"](./media/custom-button-blend-makebutton2.gif "custom_button_blend_MakeButton2")  
  
     Per la **nome della risorsa (Key)**, selezionare **applica a tutti**.  In questo modo il modello si applicano a tutti gli oggetti che sono disponibili pulsanti e lo stile risulta. Per la **definire**, selezionare **applicazione**. In questo modo il modello con ambito all'intera applicazione e lo stile risulta. Quando si impostano i valori in queste due scatole, il modello e stile del pulsante si applicano a tutti i pulsanti all'interno dell'intera applicazione e qualsiasi pulsante creato nell'applicazione, per impostazione predefinita, questo modello verrà usato.  
  
## <a name="edit-the-button-template"></a>Modificare il modello di pulsante  
 È ora disponibile un rettangolo che è stato modificato in un pulsante. In questa sezione verrà modificare il modello del pulsante e personalizzare ulteriormente l'aspetto.  
  
#### <a name="to-edit-the-button-template-to-change-the-button-appearance"></a>Per modificare il modello di pulsante per modificare l'aspetto del pulsante  
  
1. **Passare alla visualizzazione modello di modifica:** Per personalizzare ulteriormente l'aspetto del pulsante, è necessario modificare il modello di pulsante. Questo modello è stato creato al momento della conversione il rettangolo in un pulsante. Per modificare il modello di pulsante, fare doppio clic sul pulsante e selezionare **modificare le parti di un controllo (modello)** e quindi **modifica modello**.  
  
     ![Come modificare un modello](./media/custom-button-blend-edittemplate.jpg "custom_button_blend_EditTemplate")  
  
     Nell'editor del modello, si noti che il pulsante è state suddivise in una <xref:System.Windows.Shapes.Rectangle> e il <xref:System.Windows.Controls.ContentPresenter>. Il <xref:System.Windows.Controls.ContentPresenter> viene usato per presentare il contenuto all'interno del pulsante (ad esempio, la stringa "Button"). Sia il rettangolo e <xref:System.Windows.Controls.ContentPresenter> sono disposte all'interno di un <xref:System.Windows.Controls.Grid>.  
  
     ![I componenti nella presentazione di un rettangolo](./media/custom-button-blend-templatepanel.png "custom_button_blend_TemplatePanel")  
  
2. **Modificare i nomi dei componenti di modello:** Fare clic sul rettangolo nell'inventario dei modelli, modifica il <xref:System.Windows.Shapes.Rectangle> assegnare un nome da "[Rectangle]" a "Rettangolo esterno" e modificare "[ContentPresenter]" a "myContentPresenter".  
  
     ![Come rinominare un componente di un modello](./media/custom-button-blend-renamecomponents.png "custom_button_blend_RenameComponents")  
  
3. **Modificare il rettangolo in modo che risulti vuota all'interno (ad esempio, un grafico ad anello):** Selezionare **rettangolo esterno** e impostare <xref:System.Windows.Shapes.Shape.Fill%2A> su "Transparent" e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> a 5.  
  
     ![Come rendere vuoto un rettangolo](./media/custom-button-blend-changerectproperties.png "custom_button_blend_ChangeRectProperties")  
  
     Impostare quindi il <xref:System.Windows.Shapes.Shape.Stroke%2A> al colore di qualunque sia il modello sarà. A tale scopo, fare clic sulla casella bianca accanto a **tratto**, selezionare **espressione personalizzata**, digitare "{TemplateBinding Background}" nella finestra di dialogo.  
  
     ![Come impostare il colore del modello di utilizzo](./media/custom-button-blend-templatestroke.png "custom_button_blend_TemplateStroke")  
  
4. **Creare un rettangolo interno:** A questo punto, creare un altro rettangolo (denominarla "rettangolo interno") e posizionarlo in modo simmetrico all'interno del **rettangolo esterno** . Per questo tipo di lavoro, è probabile che si desideri eseguire lo zoom per ingrandire il pulsante nell'area di modifica.  
  
    > [!NOTE]
    >  Il rettangolo potrebbe apparire diverso da quello nella figura (ad esempio, potrebbe avere gli angoli arrotondati).  
  
     ![Come creare un rettangolo all'interno di un altro rettangolo](./media/custom-button-blend-innerrectangleproperties.png "custom_button_blend_innerRectangleProperties")  
  
5. **Spostare ContentPresenter nella parte superiore:** A questo punto, è possibile che il testo "Button" non sarà più visibile. Se si tratta di questa operazione, infatti **rettangolo interno** si trova sopra il **myContentPresenter**. Per risolvere questo problema, trascinare **myContentPresenter** seguito **rettangolo interno**. Riposizionare i rettangoli e **myContentPresenter** di aspetto simile al seguente.  
  
    > [!NOTE]
    >  In alternativa, è anche possibile posizionare **myContentPresenter** nella parte superiore facendovi e quindi premendo **inviare inoltrare**.  
  
     ![Come spostare un pulsante sopra un altro pulsante](./media/custom-button-blend-innerrectangle2.png "custom_button_blend_innerRectangle2")  
  
6. **Modificare l'aspetto del rettangolo interno:** Impostare il <xref:System.Windows.Shapes.Rectangle.RadiusX%2A>, <xref:System.Windows.Shapes.Rectangle.RadiusY%2A>, e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> valori a 20. Inoltre, impostare il <xref:System.Windows.Shapes.Shape.Fill%2A> sullo sfondo del modello tramite l'espressione personalizzata "{TemplateBinding Background}") e impostare <xref:System.Windows.Shapes.Shape.Stroke%2A> a "transparent". Si noti che le impostazioni per il <xref:System.Windows.Shapes.Shape.Fill%2A> e <xref:System.Windows.Shapes.Shape.Stroke%2A> dei **rettangolo interno** sono l'opposto di quelli per **rettangolo esterno**.  
  
     ![Come modificare l'aspetto di un rettangolo](./media/custom-button-blend-glassrectangleproperties1.png "custom_button_blend_glassRectangleProperties1")  
  
7. **Aggiungere un effetto cristallo in primo piano:** L'ultima parte della personalizzazione dell'aspetto del pulsante consiste nell'aggiungere un livello di ingrandimento in alto. Questo effetto cristallo è costituito da un terzo rettangolo. Poiché l'effetto cristallo ricopre l'intero pulsante, il rettangolo trasparente è simile in dimensioni per il **rettangolo esterno**. Pertanto, creare il rettangolo eseguendo semplicemente una copia del **rettangolo esterno**. Evidenziare **rettangolo esterno** e utilizzare CTRL + V e CTRL + C per creare una copia. Denominare il nuovo rettangolo "glassCube".  
  
8. **Se necessario, riposizionare glassCube:** Se **glassCube** è non è già posizionato in modo da coprire l'intero pulsante, trascinarlo in posizione.  
  
9. **Offrono una forma leggermente diversa rispetto a rettangolo esterno glassCube:** Modificare le proprietà di **glassCube**. Iniziare impostando il <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> e <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> delle proprietà a 10 e il <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> su 2.  
  
     ![Impostazioni dell'aspetto di glassCube](./media/custom-button-blend-glasscubeappearance.gif "custom_button_blend_GlassCubeAppearance")  
  
10. **Rendere glassCube simile glass:** Impostare il <xref:System.Windows.Shapes.Shape.Fill%2A> su un aspetto utilizzando una sfumatura lineare che è opaca al 75% e alterna tra il colore nero e trasparente oltre 6 approssimativamente in modo uniforme, separate da uno spazio intervalli. Si tratta di quale valore impostare i cursori sfumatura:  
  
    - Cursore sfumatura 1: Bianco, con valore alfa pari al 75%  
  
    - Cursore sfumatura 2: Trasparente  
  
    - Cursore sfumatura 3: Bianco, con valore alfa pari al 75%  
  
    - Cursore sfumatura 4: Trasparente  
  
    - Cursore sfumatura 5: Bianco, con valore alfa pari al 75%  
  
    - Cursore sfumatura 6: Trasparente  
  
     Ciò crea un effetto cristallo "ondulata".  
  
     ![Un rettangolo con effetto trasparente](./media/custom-button-blend-glassrectangleproperties2.png "custom_button_blend_glassRectangleProperties2")  
  
11. **Nascondi l'effetto cristallo:** Ora che viene visualizzato come appare strato di cristallo, andare nel **riquadro aspetto** delle **Pannello proprietà** e impostare l'opacità allo 0% per nasconderlo. Nelle sezioni successive, useremo i trigger di proprietà ed eventi per visualizzare e modificare l'effetto cristallo.  
  
     ![Come nascondere il rettangolo trasparente](./media/custom-button-glassrectangleproperties3.gif "custom_button_glassRectangleProperties3")  
  
## <a name="customize-the-button-behavior"></a>Personalizzare il comportamento del pulsante  
 A questo punto, è stata personalizzata la presentazione del pulsante modificando il modello, ma il pulsante non reagisce alle azioni dell'utente come pulsanti tipico (ad esempio, modifica dell'aspetto al passaggio del puntatore del mouse, riceve lo stato attivo e facendo clic su.) Le due procedure che seguono viene illustrato come compilare comportamenti simili ai seguenti nel pulsante personalizzato. Si sarà inizia con i trigger di proprietà semplice e quindi aggiungere le animazioni e trigger di evento.  
  
#### <a name="to-set-property-triggers"></a>Impostare la proprietà attiva  
  
1. **Creare un nuovo trigger di proprietà:** Con **glassCube** selezionato, fare clic su **proprietà +** nel **trigger** pannello (vedere la figura che segue il passaggio successivo). Crea un trigger di proprietà con un trigger di proprietà predefinito.  
  
2. **Rendere IsMouseOver la proprietà utilizzata dal trigger:** Modificare la proprietà in <xref:System.Windows.UIElement.IsMouseOver%2A>. In questo modo, il trigger di proprietà si attiva quando la <xref:System.Windows.UIElement.IsMouseOver%2A> è di proprietà `true` (quando l'utente deve scegliere il pulsante con il puntatore del mouse).  
  
     ![Come impostare un trigger su una proprietà](./media/custom-button-blend-ismousedoverpropertytrigger.png "custom_button_blend_IsMousedOverPropertyTrigger")  
  
3. **Opacità pari al 100% dell'aspetto di glassCube IsMouseOver consente di:** Si noti che il **Trigger la registrazione è attivata** (vedere la figura precedente). Ciò significa che le modifiche apportate ai valori della proprietà della **glassCube** durante la registrazione è attivata diventerà un'azione che ha luogo quando <xref:System.Windows.UIElement.IsMouseOver%2A> è `true`. Durante la registrazione, modificare il <xref:System.Windows.UIElement.Opacity%2A> dei **glassCube** al 100%.  
  
     ![Come impostare l'opacità di un pulsante](./media/custom-button-blend-ismousedoverpropertytrigger2.gif "custom_button_blend_IsMousedOverPropertyTrigger2")  
  
     È stato creato il primo trigger di proprietà. Si noti che il **pannello Triggers** dell'editor è registrato il <xref:System.Windows.UIElement.Opacity%2A> viene modificato al 100%.  
  
     ![The "Triggers" panel](./media/custom-button-blend-propertytriggerinfo.png "custom_button_blend_PropertyTriggerInfo")  
  
     Premere F5 per eseguire l'applicazione e spostare il puntatore del mouse su e disattivazione del pulsante. Si dovrebbe essere visualizzato quando l'effetto cristallo il pulsante del puntatore del mouse e della scompaiono quando il puntatore esce.  
  
4. **IsMouseOver il del tratto di modifica del valore:** Per associare alcune altre operazioni con il <xref:System.Windows.UIElement.IsMouseOver%2A> trigger. Durante la registrazione continua, spostare la selezione da **glassCube** al **rettangolo esterno**. Impostare quindi le <xref:System.Windows.Shapes.Shape.Stroke%2A> dei **rettangolo esterno** per l'espressione personalizzata di "{DynamicResource {X:Static SystemColors. HighlightBrushKey}}". Consente di impostare il <xref:System.Windows.Shapes.Shape.Stroke%2A> per il tipico utilizzato dai pulsanti di colore di evidenziazione. Premere F5 per visualizzare l'effetto quando passa il mouse su esso.  
  
     ![Come impostare il tratto sul colore di evidenziazione](./media/custom-button-blend-ismousedoverpropertytrigger3.png "custom_button_blend_IsMousedOverPropertyTrigger3")  
  
5. **Testo sfocato IsMouseOver consente di:** Per associare un'altra azione per il <xref:System.Windows.UIElement.IsMouseOver%2A> trigger di proprietà. Visualizzare il contenuto del pulsante sfocato leggermente quando viene visualizzata l'effetto cristallo su di esso. A tale scopo, è possibile applicare un' sfocatura <xref:System.Windows.Media.Effects.BitmapEffect> per il <xref:System.Windows.Controls.ContentPresenter> (**myContentPresenter**).  
  
     ![Procedura di sfocatura del contenuto di un pulsante](./media/custom-button-blend-propertytriggerwithbitmapeffect.png "custom_button_blend_PropertyTriggerWithBitMapEffect")  
  
    > [!NOTE]
    >  Per restituire il **Pannello proprietà** su quello che era prima l'operazione di ricerca per <xref:System.Windows.Media.Effects.BitmapEffect>, cancellare il testo dal **casella di ricerca**.  
  
     A questo punto, è stato utilizzato un trigger di proprietà con diverse azioni associate per creare il comportamento di evidenziazione per quando il puntatore del mouse entra ed esce dall'area pulsante. È un altro comportamento anomalo per un pulsante per evidenziare quando lo stato attivo (ad esempio, dopo un clic). È possibile aggiungere tali comportamenti mediante l'aggiunta di un altro trigger di proprietà per il <xref:System.Windows.UIElement.IsFocused%2A> proprietà.  
  
6. **Creare trigger di proprietà per IsFocused:** Con la stessa procedura utilizzata per <xref:System.Windows.UIElement.IsMouseOver%2A> (vedere il primo passaggio di questa sezione), creare un altro trigger di proprietà per il <xref:System.Windows.UIElement.IsFocused%2A> proprietà. Sebbene **Trigger la registrazione è attivata**, aggiungere le seguenti azioni per il trigger:  
  
    - **glassCube** Ottiene un <xref:System.Windows.UIElement.Opacity%2A> pari al 100%.  
  
    - **Rettangolo esterno** Ottiene un <xref:System.Windows.Shapes.Shape.Stroke%2A> valore dell'espressione personalizzati di "{DynamicResource {X:Static SystemColors. HighlightBrushKey}}".  
  
 Come passaggio finale in questa procedura dettagliata, si aggiungerà le animazioni al pulsante. Queste animazioni verranno attivate da eventi, in particolare, il <xref:System.Windows.UIElement.MouseEnter> e <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventi.  
  
#### <a name="to-use-event-triggers-and-animations-to-add-interactivity"></a>Usare i trigger di evento e le animazioni per aggiungere interattività  
  
1. **Creare un Trigger di evento MouseEnter:** Aggiungere un nuovo trigger di evento e selezionare <xref:System.Windows.UIElement.MouseEnter> dell'evento da utilizzare nel trigger.  
  
     ![Come creare un trigger di evento MouseEnter](./media/custom-button-blend-mouseovereventtrigger.png "custom_button_blend_MouseOverEventTrigger")  
  
2. **Creare una sequenza temporale di animazione:** Successivamente, associare una sequenza temporale di animazione per il <xref:System.Windows.UIElement.MouseEnter> evento.  
  
     ![Come aggiungere una sequenza temporale di animazione a un evento](./media/custom-button-blend-mouseovereventtrigger2.png "custom_button_blend_MouseOverEventTrigger2")  
  
     Dopo aver premuto **OK** per creare una nuova sequenza temporale, un **pannello della sequenza temporale** viene visualizzata e "Sequenza temporale la registrazione è attivata" sia visibile nel Pannello di progettazione. In questo modo che è possibile avviare la registrazione delle modifiche di proprietà nella sequenza temporale (modifiche alla proprietà animata).  
  
    > [!NOTE]
    >  Potrebbe essere necessario ridimensionare la finestra e/o i pannelli per visualizzare la visualizzazione.  
  
     ![Il pannello della sequenza temporale](./media/custom-button-blend-mouseovereventtrigger3.png "custom_button_blend_MouseOverEventTrigger3")  
  
3. **Creare un fotogramma chiave:** Per creare un'animazione, selezionare l'oggetto che si desidera aggiungere un'animazione, creare due o più i fotogrammi chiave sulla sequenza temporale e per i fotogrammi chiave, impostare i valori delle proprietà desiderate dell'animazione per interpolare tra. Nella figura seguente illustra la creazione di un fotogramma chiave.  
  
     ![Come creare un fotogramma chiave](./media/custom-button-blend-mouseovereventtrigger4.png "custom_button_blend_MouseOverEventTrigger4")  
  
4. **Compattazione glassCube in questo fotogramma chiave:** Con il secondo fotogramma chiave selezionato, ridurre la dimensione dei **glassCube** al 90% delle relative dimensioni completa usando la **dimensioni trasformare**.  
  
     ![Come compattare le dimensioni di un pulsante](./media/custom-button-blend-sizetransform.png "custom_button_blend_SizeTransform")  
  
     Premere F5 per eseguire l'applicazione. Spostare il puntatore del mouse su esso. Si noti che l'effetto cristallo compatta sopra il pulsante.  
  
5. **Creare un altro Trigger di evento e associare un'animazione di diversi:** È possibile aggiungere un'altra animazione. Usare una procedura simile a quello utilizzato per creare l'animazione di trigger di evento precedente:  
  
    1. Creare un nuovo trigger evento usando il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento.  
  
    2. Associare una nuova sequenza temporale con la <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento.  
  
     ![Come creare una nuova sequenza temporale](./media/custom-button-blend-clickeventtrigger1.png "custom_button_blend_ClickEventTrigger1")  
  
    1. Per questa sequenza temporale, creare due fotogrammi chiave, in secondi compreso tra 0,0 e il secondo 0,3 secondi.  
  
    2. Con il fotogramma chiave 0,3 secondi evidenziato, impostare il **Ruota l'angolo di trasformare** a 360 gradi.  
  
     ![Come creare una trasformazione rotativa](./media/custom-button-blend-rotatetransform.gif "custom_button_blend_RotateTransform")  
  
    1. Premere F5 per eseguire l'applicazione. Fare clic sul pulsante. Si noti che l'effetto cristallo intorno.  
  
## <a name="conclusion"></a>Conclusione  
 È stato completato un pulsante personalizzato. È stato eseguito questa operazione utilizzando un modello di pulsante che è stato applicato a tutti i pulsanti nell'applicazione. Se si esce dalla modalità di modifica di modelli (vedere la figura seguente) e creare più pulsanti, si noterà che l'aspetto e si comportano come il pulsante personalizzato anziché, ad esempio il pulsante predefinito.  
  
 ![Il modello di pulsante personalizzato](./media/custom-button-blend-scopeup.gif "custom_button_blend_ScopeUp")  
  
 ![Più pulsanti che utilizzano lo stesso modello](./media/custom-button-blend-createmultiplebuttons.png "custom_button_blend_CreateMultipleButtons")  
  
 Premere F5 per eseguire l'applicazione. Fare clic sui pulsanti e notare come tutte lo stesso comportamento.  
  
 Tenere presente che mentre si era personalizzando il modello, è impostato il <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà di **rettangolo interno** e il <xref:System.Windows.Shapes.Shape.Stroke%2A> proprietà **rettangolo esterno** sullo sfondo del modello ({ Sfondo TemplateBinding}). Per questo motivo, quando si imposta il colore di sfondo dei pulsanti di singoli, lo sfondo che è impostato verrà utilizzato per le rispettive proprietà. Provare a passare a questo punto gli sfondi. Nella figura seguente, vengono utilizzate le sfumature diverse. Pertanto, un modello è molto utile per la personalizzazione generale dei controlli come pulsante, i controlli con i modelli possono essere ancora modificati per un aspetto diverso da altra.  
  
 ![I pulsanti con lo stesso modello con un aspetto differente](./media/custom-button-blend-blendconclusion.jpg "custom_button_blend_BlendConclusion")  
  
 In conclusione, nel processo di personalizzazione di un modello di pulsante si è appreso come eseguire le operazioni seguenti in Microsoft Expression Blend:  
  
- Personalizzare l'aspetto di un controllo.  
  
- Impostare i trigger di proprietà. I trigger di proprietà sono molto utili perché possono essere usati nella maggior parte degli oggetti, non solo i controlli.  
  
- Impostare i trigger di evento. I trigger di evento sono molto utili perché possono essere usati nella maggior parte degli oggetti, non solo i controlli.  
  
- Creare animazioni.  
  
- Varie: creare sfumature, aggiungere BitmapEffects, usare le trasformazioni e impostare le proprietà di base di oggetti.  
  
## <a name="see-also"></a>Vedere anche

- [Creare un pulsante usando XAML](walkthrough-create-a-button-by-using-xaml.md)
- [Applicazione di stili e modelli](styling-and-templating.md)
- [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md)
- [Cenni sul disegno con colori a tinta unita e sfumature](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Panoramica sugli effetti bitmap](../graphics-multimedia/bitmap-effects-overview.md)
