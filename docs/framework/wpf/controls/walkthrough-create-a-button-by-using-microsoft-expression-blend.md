---
title: 'Procedura dettagliata: Creare un pulsante usando Microsoft Expression Blend'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
- converting [WPF], shape to button
- Expression Blend [WPF Designer]
ms.assetid: ff5037c2-bba7-4cae-8abb-6475b686c48e
ms.openlocfilehash: 1b4c775ea0680dcd8252a98c722dfe8f7e62548f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942497"
---
# <a name="walkthrough-create-a-button-by-using-microsoft-expression-blend"></a>Procedura dettagliata: Creare un pulsante usando Microsoft Expression Blend
Questa procedura dettagliata illustra il processo di creazione di un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] pulsante personalizzato con Microsoft Expression Blend.  
  
> [!IMPORTANT]
> Microsoft Expression Blend funziona generando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] che viene quindi compilato per rendere il programma eseguibile. Se invece si preferisce [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] usare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] direttamente, è disponibile un'altra procedura dettagliata che crea la stessa applicazione con Visual Studio anziché Blend. Per altre informazioni, vedere [creare un pulsante usando XAML](walkthrough-create-a-button-by-using-xaml.md) .  
  
 Nella figura seguente viene illustrato il pulsante personalizzato che verrà creato.  
  
 ![Pulsante personalizzato che viene creato](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")  
  
## <a name="convert-a-shape-to-a-button"></a>Convertire una forma in un pulsante  
 Nella prima parte di questa procedura dettagliata viene illustrato come creare l'aspetto personalizzato del pulsante personalizzato. A tale scopo, è necessario innanzitutto convertire un rettangolo in un pulsante. È quindi possibile aggiungere altre forme al modello del pulsante, creando un pulsante ricerca più complesso. Perché non iniziare con un pulsante normale e personalizzarlo? Poiché un pulsante presenta funzionalità predefinite che non sono necessarie; per i pulsanti personalizzati, è più semplice iniziare con un rettangolo.  
  
#### <a name="to-create-a-new-project-in-expression-blend"></a>Per creare un nuovo progetto in Expression Blend  
  
1. Avviare Expression Blend. (Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Expression**, quindi fare clic su **Microsoft Expression Blend**.)  
  
2. Se necessario, ingrandire l'applicazione.  
  
3. Scegliere **Nuovo progetto** dal menu **File**.  
  
4. Selezionare **applicazione standard (exe)** .  
  
5. Assegnare un nome `CustomButton` al progetto e fare clic su **OK**.  
  
 A questo punto si dispone di un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] progetto vuoto. È possibile premere F5 per eseguire l'applicazione. Come si può immaginare, l'applicazione è costituita solo da una finestra vuota. Successivamente, creare un rettangolo arrotondato e convertirlo in un pulsante.  
  
#### <a name="to-convert-a-rectangle-to-a-button"></a>Per convertire un rettangolo in un pulsante  
  
1. **Impostare la proprietà sfondo finestra su nero:** Selezionare la finestra, fare clic sulla **scheda Proprietà**e impostare la <xref:System.Windows.Controls.Control.Background%2A> proprietà su `Black`.  
  
     ![Come impostare lo sfondo di un pulsante su nero](./media/custom-button-blend-changebackground.png "custom_button_blend_ChangeBackground")  
  
2. **Creare un rettangolo circa la dimensione di un pulsante nella finestra:** Selezionare lo strumento rettangolo sul pannello degli strumenti a sinistra e trascinare il rettangolo sulla finestra.  
  
     ![Come creare un rettangolo](./media/custom-button-blend-drawrect.png "custom_button_blend_DrawRect")  
  
3. **Arrotondare gli angoli del rettangolo:** Trascinare i punti di controllo del rettangolo o impostare direttamente le <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> proprietà e. <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> Impostare i valori di <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> e <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> su 20.  
  
     ![Come rendere gli angoli di un rettangolo arrotondato](./media/custom-button-blend-roundcorners.png "custom_button_blend_RoundCorners")  
  
4. **Modificare il rettangolo in un pulsante:** Selezionare il rettangolo. Scegliere **Crea**dal menu **strumenti** .  
  
     ![Come creare una forma in un pulsante](./media/custom-button-blend-makebutton.png "custom_button_blend_MakeButton")  
  
5. **Specificare l'ambito dello stile o del modello:** Viene visualizzata una finestra di dialogo simile alla seguente.  
  
     Finestra ![di dialogo "Crea risorsa di stile"](./media/custom-button-blend-makebutton2.gif "custom_button_blend_MakeButton2")  
  
     Per **nome risorsa (chiave)** selezionare **applica a tutti**.  In questo modo, lo stile e il modello di pulsante risultanti si applicano a tutti gli oggetti che sono pulsanti. Per **define in**selezionare **applicazione**. In questo modo, lo stile e il modello di pulsante risultante avranno un ambito per l'intera applicazione. Quando si impostano i valori in queste due caselle, lo stile e il modello del pulsante si applicano a tutti i pulsanti all'interno dell'intera applicazione. per impostazione predefinita, il pulsante creato nell'applicazione utilizzerà questo modello.  
  
## <a name="edit-the-button-template"></a>Modificare il modello di pulsante  
 A questo punto si dispone di un rettangolo che è stato modificato in un pulsante. In questa sezione si modificherà il modello del pulsante e ne verrà ulteriormente personalizzato l'aspetto.  
  
#### <a name="to-edit-the-button-template-to-change-the-button-appearance"></a>Per modificare il modello di pulsante per modificare l'aspetto del pulsante  
  
1. **Passare a modifica visualizzazione modello:** Per personalizzare ulteriormente l'aspetto del pulsante, è necessario modificare il modello di pulsante. Questo modello è stato creato quando il rettangolo è stato convertito in un pulsante. Per modificare il modello di pulsante, fare clic con il pulsante destro del mouse sul pulsante e selezionare **Modifica parti di controllo (modello)** e quindi **modifica modello**.  
  
     ![Come modificare un modello](./media/custom-button-blend-edittemplate.jpg "custom_button_blend_EditTemplate")  
  
     Nell'editor dei modelli si noti che il pulsante è ora separato in un <xref:System.Windows.Shapes.Rectangle> oggetto <xref:System.Windows.Controls.ContentPresenter>e. <xref:System.Windows.Controls.ContentPresenter> Viene utilizzato per presentare il contenuto all'interno del pulsante (ad esempio, la stringa "button"). Sia il rettangolo che <xref:System.Windows.Controls.ContentPresenter> l'oggetto sono disposti all'interno <xref:System.Windows.Controls.Grid>di un oggetto.  
  
     ![Componenti nella presentazione di un rettangolo](./media/custom-button-blend-templatepanel.png "custom_button_blend_TemplatePanel")  
  
2. **Modificare i nomi dei componenti del modello:** Fare clic con il pulsante destro del mouse sul rettangolo nell'inventario <xref:System.Windows.Shapes.Rectangle> dei modelli, modificare il nome da "[rettangolo]" a "rettangolo esterno" e modificare "[ContentPresenter]" in "ContentPresenter".  
  
     ![Come rinominare un componente di un modello](./media/custom-button-blend-renamecomponents.png "custom_button_blend_RenameComponents")  
  
3. **Modificare il rettangolo in modo che sia vuoto all'interno di (ad esempio, un anello):** Selezionare **rettangolo esterno** e impostare <xref:System.Windows.Shapes.Shape.Fill%2A> su "trasparente" e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> su 5.  
  
     ![Come rendere vuoto un rettangolo](./media/custom-button-blend-changerectproperties.png "custom_button_blend_ChangeRectProperties")  
  
     Quindi impostare sul <xref:System.Windows.Shapes.Shape.Stroke%2A> colore di qualunque sia il modello. A tale scopo, fare clic sulla piccola casella bianca accanto a **Stroke**, selezionare **CustomExpression**e digitare "{TemplateBinding Background}" nella finestra di dialogo.  
  
     ![Come impostare l'utilizzo del colore del modello](./media/custom-button-blend-templatestroke.png "custom_button_blend_TemplateStroke")  
  
4. **Creare un rettangolo interno:** A questo punto, creare un altro rettangolo (denominarlo "rettangolo interno") e posizionarlo in un punto simmetrico all'interno di **rettangolo esterno** . Per questo tipo di lavoro, è probabile che si desideri applicare lo zoom per rendere il pulsante più grande nell'area di modifica.  
  
    > [!NOTE]
    > Il rettangolo potrebbe avere un aspetto diverso da quello della figura (ad esempio, potrebbe avere angoli arrotondati).  
  
     ![Come creare un rettangolo all'interno di un altro rettangolo](./media/custom-button-blend-innerrectangleproperties.png "custom_button_blend_innerRectangleProperties")  
  
5. **Sposta ContentPresenter nella parte superiore:** A questo punto, è possibile che il testo "button" non sia più visibile. In caso affermativo, questo è dovuto al fatto che **rettangolo interno** è sopra a **ContentPresenter**. Per risolvere questo problema, trascinare **ContentPresenter** sotto **rettangolo interno**. Riposizionare i rettangoli e **ContentPresenter** per avere un aspetto simile al seguente.  
  
    > [!NOTE]
    > In alternativa, è possibile posizionare anche **ContentPresenter** in alto facendo clic con il pulsante destro del mouse su di esso e scegliendo **Invia avanti**.  
  
     ![Come spostare un pulsante all'inizio di un altro pulsante](./media/custom-button-blend-innerrectangle2.png "custom_button_blend_innerRectangle2")  
  
6. **Modificare l'aspetto di rettangolo interno:** Impostare i <xref:System.Windows.Shapes.Rectangle.RadiusX%2A>valori <xref:System.Windows.Shapes.Rectangle.RadiusY%2A>, e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> su 20. Inoltre, impostare sullo <xref:System.Windows.Shapes.Shape.Fill%2A> sfondo del modello usando l'espressione personalizzata "{TemplateBinding Background}" e impostare <xref:System.Windows.Shapes.Shape.Stroke%2A> su "transparent". Si noti che le impostazioni per <xref:System.Windows.Shapes.Shape.Fill%2A> e <xref:System.Windows.Shapes.Shape.Stroke%2A> di **rettangolo interno** sono l'opposto di quelle per **rettangolo esterno**.  
  
     ![Come modificare l'aspetto di un rettangolo](./media/custom-button-blend-glassrectangleproperties1.png "custom_button_blend_glassRectangleProperties1")  
  
7. **Aggiungere un livello cristallo all'inizio:** L'ultima parte della personalizzazione dell'aspetto del pulsante è l'aggiunta di un livello cristallo in alto. Questo livello cristallo è costituito da un terzo rettangolo. Poiché il cristallo coprirà l'intero pulsante, il rettangolo di vetro sarà simile in dimensioni a **rettangolo esterno**. Quindi, creare il rettangolo semplicemente eseguendo una copia di **rettangolo esterno**. Evidenziare **rettangolo esterno** e usare Ctrl + C e CTRL + V per creare una copia. Assegnare al nuovo rettangolo il nome "glassCube".  
  
8. **Riposizionare glassCube se necessario:** Se **glassCube** non è già posizionato in modo da coprire l'intero pulsante, trascinarlo in posizione.  
  
9. **Assegnare a glassCube una forma leggermente diversa da rettangolo esterno:** Modificare le proprietà di **glassCube**. Per iniziare, modificare le <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> proprietà <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> e su 10 e su 2.  
  
     ![Impostazioni dell'aspetto per glassCube](./media/custom-button-blend-glasscubeappearance.gif "custom_button_blend_GlassCubeAppearance")  
  
10. **Rendere glassCube simile a Glass:** <xref:System.Windows.Shapes.Shape.Fill%2A> Impostare su un aspetto vitreo usando una sfumatura lineare che è opaca del 75% e alterna tra il colore bianco e trasparente oltre 6 intervalli approssimativamente equidistanti. Ecco cosa impostare per i cursori sfumatura:  
  
    - Cursore sfumatura 1: Bianco con valore alfa pari al 75%  
  
    - Cursore sfumatura 2: Trasparente  
  
    - Cursore sfumatura 3: Bianco con valore alfa pari al 75%  
  
    - Cursore sfumatura 4: Trasparente  
  
    - Cursore sfumatura 5: Bianco con valore alfa pari al 75%  
  
    - Cursore sfumatura 6: Trasparente  
  
     Viene così creato un aspetto a cristallino ondulato.  
  
     ![Un rettangolo] simile a Glass (./media/custom-button-blend-glassrectangleproperties2.png "custom_button_blend_glassRectangleProperties2")  
  
11. **Nascondi il livello cristallo:** Ora che è possibile visualizzare l'aspetto del livello vitreo, passare al **riquadro aspetto** del **pannello Proprietà** e impostare l'opacità su 0% per nasconderlo. Nelle sezioni precedenti si useranno trigger di proprietà ed eventi per mostrare e modificare il livello cristallo.  
  
     ![Come nascondere il rettangolo Glass](./media/custom-button-glassrectangleproperties3.gif "custom_button_glassRectangleProperties3")  
  
## <a name="customize-the-button-behavior"></a>Personalizzare il comportamento del pulsante  
 A questo punto, la presentazione del pulsante è stata personalizzata modificando il modello, ma il pulsante non risponde alle azioni dell'utente come i pulsanti tipici, ad esempio modificando l'aspetto al passaggio del mouse, ricevendo lo stato attivo e facendo clic. Nelle due procedure successive viene illustrato come creare comportamenti come questi nel pulsante personalizzato. Si inizierà con i trigger di proprietà semplici e quindi si aggiungono trigger di evento e animazioni.  
  
#### <a name="to-set-property-triggers"></a>Per impostare i trigger di proprietà  
  
1. **Creare un nuovo trigger di proprietà:** Con **glassCube** selezionato, fare clic su **+ Proprietà** nel pannello **trigger** (vedere la figura che segue il passaggio successivo). Viene creato un trigger di proprietà con un trigger di proprietà predefinito.  
  
2. **Eseguire l'impostazione di MouseOver sulla proprietà usata dal trigger:** Modificare la proprietà in <xref:System.Windows.UIElement.IsMouseOver%2A>. In questo modo viene attivato il trigger della <xref:System.Windows.UIElement.IsMouseOver%2A> proprietà quando `true` la proprietà è (quando l'utente punta al pulsante con il mouse).  
  
     ![Come impostare un trigger su una proprietà](./media/custom-button-blend-ismousedoverpropertytrigger.png "custom_button_blend_IsMousedOverPropertyTrigger")  
  
3. **Il passaggio a MouseOver attiva l'opacità del 100% per glassCube:** Si noti che la **registrazione del trigger è attivata** (vedere la figura precedente). Ciò significa che tutte le modifiche apportate ai valori delle proprietà di **glassCube** durante la registrazione si troveranno in un'azione che viene <xref:System.Windows.UIElement.IsMouseOver%2A> eseguita `true`quando è. Durante la registrazione, modificare <xref:System.Windows.UIElement.Opacity%2A> il di **glassCube** in 100%.  
  
     ![Come impostare l'opacità di un pulsante](./media/custom-button-blend-ismousedoverpropertytrigger2.gif "custom_button_blend_IsMousedOverPropertyTrigger2")  
  
     A questo punto è stato creato il primo trigger di proprietà. Si noti che il **pannello Trigger** dell'editor ha registrato l' <xref:System.Windows.UIElement.Opacity%2A> oggetto modificato in 100%.  
  
     ![The "Triggers" panel](./media/custom-button-blend-propertytriggerinfo.png "custom_button_blend_PropertyTriggerInfo")  
  
     Premere F5 per eseguire l'applicazione e spostare il puntatore del mouse sul pulsante. Si noterà che il livello cristallo viene visualizzato quando si passa il mouse sul pulsante e si scompare quando il puntatore viene lasciato.  
  
4. **La modifica del valore del tratto per i trigger di MouseOver:** Si associano ad altre azioni al <xref:System.Windows.UIElement.IsMouseOver%2A> trigger. Durante la registrazione continua, cambiare la selezione da **glassCube** a **rettangolo esterno**. Impostare <xref:System.Windows.Shapes.Shape.Stroke%2A> quindi di **rettangolo esterno** sull'espressione personalizzata di "{DynamicResource {x:Static SystemColors. HighlightBrushKey}}". <xref:System.Windows.Shapes.Shape.Stroke%2A> In questo modo viene impostato sul colore di evidenziazione tipico utilizzato dai pulsanti. Premere F5 per visualizzare l'effetto quando si passa il mouse sul pulsante.  
  
     ![Come impostare il tratto sul colore di evidenziazione](./media/custom-button-blend-ismousedoverpropertytrigger3.png "custom_button_blend_IsMousedOverPropertyTrigger3")  
  
5. **Il testo sfocato viene attivato da MouseOver:** Associare un'altra azione al trigger di <xref:System.Windows.UIElement.IsMouseOver%2A> proprietà. Fare in modo che il contenuto del pulsante appaia leggermente sfocato quando viene visualizzato il cristallo. A tale scopo, è possibile applicare una sfocatura <xref:System.Windows.Media.Effects.BitmapEffect> <xref:System.Windows.Controls.ContentPresenter> a (**ContentPresenter**).  
  
     ![Come sfocare il contenuto di un pulsante](./media/custom-button-blend-propertytriggerwithbitmapeffect.png "custom_button_blend_PropertyTriggerWithBitMapEffect")  
  
    > [!NOTE]
    > Per riportare il **pannello Proprietà** a quello in cui si trovava prima di <xref:System.Windows.Media.Effects.BitmapEffect>eseguire la ricerca, cancellare il testo dalla **casella di ricerca**.  
  
     A questo punto, è stato usato un trigger di proprietà con diverse azioni associate per creare il comportamento di evidenziazione quando il puntatore del mouse entra e lascia l'area del pulsante. Un altro comportamento tipico per un pulsante è evidenziare quando ha lo stato attivo, come dopo aver fatto clic su di esso. È possibile aggiungere tale comportamento aggiungendo un altro trigger di proprietà per <xref:System.Windows.UIElement.IsFocused%2A> la proprietà.  
  
6. **Crea trigger di proprietà per con stato attivo:** Utilizzando la stessa procedura utilizzata per <xref:System.Windows.UIElement.IsMouseOver%2A> (vedere il primo passaggio di questa sezione), creare un altro trigger di proprietà <xref:System.Windows.UIElement.IsFocused%2A> per la proprietà. Mentre la **registrazione dei trigger è attivata**, aggiungere al trigger le azioni seguenti:  
  
    - **glassCube** ottiene un <xref:System.Windows.UIElement.Opacity%2A> del 100%.  
  
    - **rettangolo esterno** ottiene un <xref:System.Windows.Shapes.Shape.Stroke%2A> valore di espressione personalizzato "{DynamicResource {x:Static SystemColors. HighlightBrushKey}}".  
  
 Come ultimo passaggio di questa procedura dettagliata, si aggiungeranno animazioni al pulsante. Queste animazioni verranno attivate dagli eventi, in particolare gli <xref:System.Windows.UIElement.MouseEnter> eventi e. <xref:System.Windows.Controls.Primitives.ButtonBase.Click>  
  
#### <a name="to-use-event-triggers-and-animations-to-add-interactivity"></a>Per usare trigger di evento e animazioni per aggiungere interattività  
  
1. **Creare un trigger di evento MouseEnter:** Aggiungere un nuovo trigger di evento e <xref:System.Windows.UIElement.MouseEnter> Selezionare come evento da usare nel trigger.  
  
     ![Come creare un trigger di evento MouseEnter](./media/custom-button-blend-mouseovereventtrigger.png "custom_button_blend_MouseOverEventTrigger")  
  
2. **Creare una sequenza temporale di animazione:** Successivamente, associare una sequenza temporale di animazione <xref:System.Windows.UIElement.MouseEnter> all'evento.  
  
     ![Come aggiungere una sequenza temporale di animazione a un evento](./media/custom-button-blend-mouseovereventtrigger2.png "custom_button_blend_MouseOverEventTrigger2")  
  
     Dopo aver premuto **OK** per creare una nuova sequenza temporale, viene visualizzato il **Pannello sequenza temporale** e l'opzione "registrazione sequenza temporale è attiva" è visibile nel pannello di progettazione. Ciò significa che è possibile avviare la registrazione delle modifiche delle proprietà nella sequenza temporale (animare le modifiche alle proprietà).  
  
    > [!NOTE]
    > Potrebbe essere necessario ridimensionare la finestra e/o i pannelli per visualizzare la visualizzazione.  
  
     ![Pannello sequenza temporale](./media/custom-button-blend-mouseovereventtrigger3.png "custom_button_blend_MouseOverEventTrigger3")  
  
3. **Creare un fotogramma chiave:** Per creare un'animazione, selezionare l'oggetto che si desidera animare, creare due o più fotogrammi chiave sulla sequenza temporale e, per tali fotogrammi chiave, impostare i valori delle proprietà per cui si desidera che l'animazione interpolata. Nella figura seguente viene illustrata la creazione di un fotogramma chiave.  
  
     ![Come creare un fotogramma chiave](./media/custom-button-blend-mouseovereventtrigger4.png "custom_button_blend_MouseOverEventTrigger4")  
  
4. **Compatta glassCube in questo fotogramma chiave:** Con il secondo fotogramma chiave selezionato, ridurre le dimensioni del **glassCube** al 90% delle sue dimensioni complete usando la **trasformazione Dimensione**.  
  
     ![Come ridurre le dimensioni di un pulsante](./media/custom-button-blend-sizetransform.png "custom_button_blend_SizeTransform")  
  
     Premere F5 per eseguire l'applicazione. Spostare il puntatore del mouse sul pulsante. Si noti che il livello cristallo viene compattato sulla parte superiore del pulsante.  
  
5. **Creare un altro trigger di evento e associarvi un'animazione diversa:** Aggiungere un'altra animazione. Usare una procedura simile a quella usata per creare l'animazione del trigger di evento precedente:  
  
    1. Creare un nuovo trigger di evento usando <xref:System.Windows.Controls.Primitives.ButtonBase.Click> l'evento.  
  
    2. Associare una nuova sequenza temporale <xref:System.Windows.Controls.Primitives.ButtonBase.Click> all'evento.  
  
     ![Come creare una nuova sequenza temporale](./media/custom-button-blend-clickeventtrigger1.png "custom_button_blend_ClickEventTrigger1")  
  
    1. Per questa sequenza temporale, creare due fotogrammi chiave, uno a 0,0 secondi e il secondo a 0,3 secondi.  
  
    2. Con il fotogramma chiave a 0,3 secondi evidenziato, impostare l' **angolo di trasformazione ruota** su 360 gradi.  
  
     ![Come creare una trasformazione di rotazione](./media/custom-button-blend-rotatetransform.gif "custom_button_blend_RotateTransform")  
  
    1. Premere F5 per eseguire l'applicazione. Fare clic sul pulsante. Si noti che il livello cristallo ruota intorno.  
  
## <a name="conclusion"></a>Conclusione  
 È stato completato un pulsante personalizzato. Questa operazione è stata fatta usando un modello di pulsante che è stato applicato a tutti i pulsanti nell'applicazione. Se si lascia la modalità di modifica del modello (vedere la figura seguente) e si crea un numero maggiore di pulsanti, si noterà che sembrano e si comportano come il pulsante personalizzato anziché come il pulsante predefinito.  
  
 ![Modello di pulsante personalizzato](./media/custom-button-blend-scopeup.gif "custom_button_blend_ScopeUp")  
  
 ![Più pulsanti che usano lo stesso modello](./media/custom-button-blend-createmultiplebuttons.png "custom_button_blend_CreateMultipleButtons")  
  
 Premere F5 per eseguire l'applicazione. Fare clic sui pulsanti e notare come si comportano tutti allo stesso modo.  
  
 Tenere presente che, durante la personalizzazione del modello, <xref:System.Windows.Shapes.Shape.Fill%2A> impostare la proprietà di **rettangolo interno** e la <xref:System.Windows.Shapes.Shape.Stroke%2A> proprietà **rettangolo esterno** sullo sfondo del modello ({TemplateBinding Background}). Per questo motivo, quando si imposta il colore di sfondo dei singoli pulsanti, lo sfondo impostato verrà usato per le rispettive proprietà. Provare subito a modificare gli sfondi. Nella figura seguente vengono usate diverse sfumature. Pertanto, anche se un modello è utile per la personalizzazione complessiva dei controlli, ad esempio il pulsante, i controlli con i modelli possono comunque essere modificati in modo da risultare diversi tra loro.  
  
 ![Pulsanti con lo stesso modello che sembrano diferente](./media/custom-button-blend-blendconclusion.jpg "custom_button_blend_BlendConclusion")  
  
 In conclusione, nel processo di personalizzazione di un modello di pulsante si è appreso come eseguire le operazioni seguenti in Microsoft Expression Blend:  
  
- Personalizzare l'aspetto di un controllo.  
  
- Imposta i trigger di proprietà. I trigger di proprietà sono molto utili perché possono essere usati per la maggior parte degli oggetti, non solo per i controlli.  
  
- Impostare i trigger di evento. I trigger di evento sono molto utili perché possono essere usati nella maggior parte degli oggetti, non solo nei controlli.  
  
- Creazione di animazioni.  
  
- Varie: creazione di sfumature, aggiunta di BitmapEffect, utilizzo di trasformazioni e impostazione delle proprietà di base degli oggetti.  
  
## <a name="see-also"></a>Vedere anche

- [Creare un pulsante usando XAML](walkthrough-create-a-button-by-using-xaml.md)
- [Applicazione di stili e modelli](styling-and-templating.md)
- [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md)
- [Cenni sul disegno con colori a tinta unita e sfumature](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Panoramica sugli effetti bitmap](../graphics-multimedia/bitmap-effects-overview.md)
