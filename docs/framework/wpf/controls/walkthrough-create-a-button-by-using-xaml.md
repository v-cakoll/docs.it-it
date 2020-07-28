---
title: 'Procedura dettagliata: creazione di un pulsante tramite XAML'
description: Usare questa procedura dettagliata per apprendere come creare un pulsante animato da usare in un'applicazione Windows Presentation Foundation usando XAML.
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: 136d1ad5d6fefd70f0d977e5287ae75f06c52d36
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164852"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a>Procedura dettagliata: creazione di un pulsante tramite XAML

In questa procedura dettagliata viene illustrato come creare un pulsante animato da utilizzare in un'applicazione Windows Presentation Foundation (WPF). Questa procedura dettagliata USA stili e un modello per creare una risorsa pulsante personalizzata che consente il riutilizzo del codice e la separazione della logica dei pulsanti dalla dichiarazione del pulsante. Questa procedura dettagliata viene scritta interamente in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .

> [!IMPORTANT]
> Questa procedura dettagliata illustra i passaggi per la creazione dell'applicazione digitando o copiando e incollando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] in Visual Studio. Se si preferisce imparare a usare una finestra di progettazione per creare la stessa applicazione, vedere [creare un pulsante tramite Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).

Nella figura seguente sono illustrati i pulsanti finiti.

![Pulsanti personalizzati creati tramite XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-basic-buttons"></a>Crea pulsanti di base

Iniziamo creando un nuovo progetto e aggiungendo alcuni pulsanti alla finestra.

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a>Per creare un nuovo progetto WPF e aggiungere pulsanti alla finestra

1. Avviare Visual Studio.

2. **Creare un nuovo progetto WPF:** Scegliere **nuovo**dal menu **file** , quindi fare clic su **progetto**. Trovare il modello di **applicazione Windows (WPF)** e denominare il progetto "AnimatedButton". Verrà creata la struttura per l'applicazione.

3. **Aggiungere i pulsanti predefiniti di base:** Tutti i file necessari per questa procedura dettagliata sono forniti dal modello. Aprire il file Window1. xaml facendo doppio clic su di esso in Esplora soluzioni. Per impostazione predefinita, è presente un <xref:System.Windows.Controls.Grid> elemento in Window1. XAML. Rimuovere l' <xref:System.Windows.Controls.Grid> elemento e aggiungere alcuni pulsanti alla [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] pagina digitando o copiando e incollando il codice evidenziato seguente in Window1. XAML:

    ```xaml
    <Window x:Class="AnimatedButton.Window1"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      Title="AnimatedButton" Height="300" Width="300"
      Background="Black">
      <!-- Buttons arranged vertically inside a StackPanel. -->
      <StackPanel HorizontalAlignment="Left">
          <Button>Button 1</Button>
          <Button>Button 2</Button>
          <Button>Button 3</Button>
      </StackPanel>
    </Window>
    ```

     Premere F5 per eseguire l'applicazione; verrà visualizzato un set di pulsanti simile a quello illustrato nella figura seguente.

     ![Tre pulsanti di base](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")

     Ora che sono stati creati i pulsanti di base, si è terminato di usare il file Window1. XAML. Il resto della procedura dettagliata è incentrato sul file app. XAML, definendo gli stili e un modello per i pulsanti.

## <a name="set-basic-properties"></a>Imposta proprietà di base

Successivamente, è possibile impostare alcune proprietà su questi pulsanti per controllare l'aspetto e il layout dei pulsanti. Invece di impostare le proprietà sui pulsanti singolarmente, si utilizzeranno le risorse per definire le proprietà dei pulsanti per l'intera applicazione. Le risorse dell'applicazione sono concettualmente simili a Cascading Style Sheets esterno (CSS) per le pagine Web; Tuttavia, le risorse sono molto più potenti di Cascading Style Sheets (CSS), come si vedrà alla fine di questa procedura dettagliata. Per altre informazioni sulle risorse, vedere [risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a>Per utilizzare gli stili per impostare le proprietà di base sui pulsanti

1. **Definire un blocco Application. resources:** Aprire app. XAML e aggiungere il markup evidenziato seguente se non è già presente:

    ```xaml
    <Application x:Class="AnimatedButton.App"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      StartupUri="Window1.xaml"
      >
      <Application.Resources>
        <!-- Resources for the entire application can be defined here. -->
      </Application.Resources>
    </Application>
    ```

     L'ambito della risorsa è determinato dalla posizione in cui viene definita la risorsa. La definizione delle risorse in `Application.Resources` nel file app. XAML consente di usare la risorsa da qualsiasi punto dell'applicazione. Per altre informazioni sulla definizione dell'ambito delle risorse, vedere [risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

2. **Creare uno stile e definire i valori di proprietà di base:** Aggiungere al blocco il markup seguente `Application.Resources` . Questo markup crea un oggetto <xref:System.Windows.Style> che si applica a tutti i pulsanti nell'applicazione, impostando il <xref:System.Windows.FrameworkElement.Width%2A> dei pulsanti su 90 e <xref:System.Windows.FrameworkElement.Margin%2A> su 10:

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     La <xref:System.Windows.Style.TargetType%2A> proprietà specifica che lo stile si applica a tutti gli oggetti di tipo <xref:System.Windows.Controls.Button> . Ogni <xref:System.Windows.Setter> imposta un valore di proprietà diverso per l'oggetto <xref:System.Windows.Style> . Quindi, a questo punto ogni pulsante nell'applicazione ha una larghezza di 90 e un margine di 10.  Se si preme F5 per eseguire l'applicazione, viene visualizzata la finestra seguente.

     ![Pulsanti con una larghezza di 90 e un margine di 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")

     È possibile eseguire molte altre operazioni con gli stili, inclusi diversi modi per ottimizzare gli oggetti di destinazione, specificare valori di proprietà complessi e persino usare gli stili come input per altri stili. Per altre informazioni, vedere [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

3. **Impostare un valore di proprietà di stile su una risorsa:** Le risorse consentono un metodo semplice per riutilizzare oggetti e valori comunemente definiti. È particolarmente utile per definire valori complessi usando le risorse per rendere il codice più modulare. Aggiungere il markup evidenziato seguente ad app. XAML.

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush" StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     Direttamente sotto il `Application.Resources` blocco è stata creata una risorsa denominata "GrayBlueGradientBrush". Questa risorsa definisce una sfumatura orizzontale. Questa risorsa può essere usata come valore della proprietà da qualsiasi punto dell'applicazione, incluso all'interno del setter di stile del pulsante per la <xref:System.Windows.Controls.Control.Background%2A> Proprietà. A questo punto, tutti i pulsanti hanno un <xref:System.Windows.Controls.Control.Background%2A> valore della proprietà di questa sfumatura.

     Premere F5 per eseguire l'applicazione. Dovrebbe essere simile al seguente.

     ![Pulsanti con uno sfondo sfumato](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")

## <a name="create-a-template-that-defines-the-look-of-the-button"></a>Creare un modello che definisce l'aspetto del pulsante

In questa sezione viene creato un modello per personalizzare l'aspetto (presentazione) del pulsante. La presentazione del pulsante è costituita da diversi oggetti, inclusi i rettangoli e altri componenti, per dare al pulsante un aspetto univoco.

Fino a questo punto, il controllo dell'aspetto dei pulsanti nell'applicazione è stato limitato alla modifica delle proprietà del pulsante. Che cosa accade se si desidera apportare modifiche più radicali all'aspetto del pulsante? I modelli consentono un controllo potente sulla presentazione di un oggetto. Poiché i modelli possono essere utilizzati all'interno di stili, è possibile applicare un modello a tutti gli oggetti a cui lo stile si applica (in questa procedura dettagliata, il pulsante).

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a>Per usare il modello per definire l'aspetto del pulsante

1. **Configurare il modello:** Poiché i controlli come <xref:System.Windows.Controls.Button> hanno una <xref:System.Windows.Controls.Control.Template%2A> proprietà, è possibile definire il valore della proprietà del modello proprio come gli altri valori di proprietà impostati in un oggetto <xref:System.Windows.Style> usando un oggetto <xref:System.Windows.Setter> . Aggiungere il markup evidenziato seguente allo stile del pulsante.

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"
        StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
        <Setter Property="Template">
          <Setter.Value>
            <!-- The button template is defined here. -->
          </Setter.Value>
        </Setter>
      </Style>
    </Application.Resources>
    ```

2. **Presentazione pulsante modifica:** A questo punto, è necessario definire il modello. Aggiungere il markup evidenziato seguente. Questo markup specifica due <xref:System.Windows.Shapes.Rectangle> elementi con bordi arrotondati, seguiti da <xref:System.Windows.Controls.DockPanel> . <xref:System.Windows.Controls.DockPanel>Viene utilizzato per ospitare l'oggetto <xref:System.Windows.Controls.ContentPresenter> del pulsante. Un oggetto <xref:System.Windows.Controls.ContentPresenter> Visualizza il contenuto del pulsante. In questa procedura dettagliata il contenuto è testo ("Button 1", "Button 2", "Button 3"). Tutti i componenti del modello, ovvero i rettangoli e, <xref:System.Windows.Controls.DockPanel> sono disposti all'interno di un oggetto <xref:System.Windows.Controls.Grid> .

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="Button">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}" ClipToBounds="True">
          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}" RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />
          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20" Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />
          <!-- Present Content (text) of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20" Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>
      </ControlTemplate>
    </Setter.Value>
    ```

     Premere F5 per eseguire l'applicazione. Dovrebbe essere simile al seguente.

     ![Finestra con 3 pulsanti](./media/custom-button-animatedbutton-4.gif)

3. **Aggiungere un GlassEffect al modello:** Successivamente, verrà aggiunto il vetro. Prima di tutto, è necessario creare alcune risorse che creino un effetto gradiente di cristallo. Aggiungere queste risorse gradienti in qualsiasi punto all'interno del `Application.Resources` blocco:

    ```xaml
    <Application.Resources>
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">
        <GradientStop Color="WhiteSmoke" Offset="0.2" />
        <GradientStop Color="Transparent" Offset="0.4" />
        <GradientStop Color="WhiteSmoke" Offset="0.5" />
        <GradientStop Color="Transparent" Offset="0.75" />
        <GradientStop Color="WhiteSmoke" Offset="0.9" />
        <GradientStop Color="Transparent" Offset="1" />
      </GradientStopCollection>
      <LinearGradientBrush x:Key="MyGlassBrushResource"
        StartPoint="0,0" EndPoint="1,1" Opacity="0.75"
        GradientStops="{StaticResource MyGlassGradientStopsResource}" />
    <!-- Styles and other resources below here. -->
    ```

     Queste risorse vengono usate come <xref:System.Windows.Shapes.Shape.Fill%2A> per un rettangolo inserito nell'oggetto <xref:System.Windows.Controls.Grid> del modello di pulsante. Aggiungere il markup evidenziato seguente al modello.

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}"
          ClipToBounds="True">

        <!-- Outer Rectangle with rounded corners. -->
        <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

        <!-- Inner Rectangle with rounded corners. -->
        <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20"
          Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />

        <!-- Glass Rectangle -->
        <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch"
          StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
          Fill="{StaticResource MyGlassBrushResource}"
          RenderTransformOrigin="0.5,0.5">
          <Rectangle.Stroke>
            <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
              <LinearGradientBrush.GradientStops>
                <GradientStop Offset="0.0" Color="LightBlue" />
                <GradientStop Offset="1.0" Color="Gray" />
              </LinearGradientBrush.GradientStops>
            </LinearGradientBrush>
          </Rectangle.Stroke>
          <!-- These transforms have no effect as they are declared here.
          The reason the transforms are included is to be targets
          for animation (see later). -->
          <Rectangle.RenderTransform>
            <TransformGroup>
              <ScaleTransform />
              <RotateTransform />
            </TransformGroup>
          </Rectangle.RenderTransform>
          <!-- A BevelBitmapEffect is applied to give the button a "Beveled" look. -->
          <Rectangle.BitmapEffect>
            <BevelBitmapEffect />
          </Rectangle.BitmapEffect>
        </Rectangle>

        <!-- Present Text of the button. -->
        <DockPanel Name="myContentPresenterDockPanel">
          <ContentPresenter x:Name="myContentPresenter" Margin="20"
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
        </DockPanel>
      </Grid>
    </ControlTemplate>
    </Setter.Value>
    ```

     Si noti che il <xref:System.Windows.UIElement.Opacity%2A> del rettangolo con la `x:Name` proprietà di "glassCube" è 0, pertanto quando si esegue l'esempio, il rettangolo di cristallo viene sovrapposto alla parte superiore. Ciò è dovuto al fatto che in seguito si aggiungeranno trigger al modello per quando l'utente interagisce con il pulsante. Tuttavia, è possibile visualizzare l'aspetto del pulsante modificando il <xref:System.Windows.UIElement.Opacity%2A> valore in 1 ed eseguendo l'applicazione. Vedere la figura seguente. Prima di procedere con il passaggio successivo, modificare il <xref:System.Windows.UIElement.Opacity%2A> ritorno a 0.

     ![Pulsanti personalizzati creati tramite XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-button-interactivity"></a>Interattività pulsante Crea

In questa sezione si creeranno trigger di proprietà e trigger di evento per modificare i valori delle proprietà ed eseguire animazioni in risposta alle azioni dell'utente, ad esempio lo spostamento del puntatore del mouse sul pulsante e sulla selezione.

Un modo semplice per aggiungere interattività (passaggio del mouse, uscita dal mouse, clic e così via) consiste nel definire i trigger all'interno del modello o dello stile. Per creare un oggetto <xref:System.Windows.Trigger> , definire una proprietà "Condition", ad esempio: il <xref:System.Windows.UIElement.IsMouseOver%2A> valore della proprietà Button è uguale a `true` . Si definiscono quindi i setter (azioni) che avvengono quando la condizione del trigger è true.

### <a name="to-create-button-interactivity"></a>Per creare l'interattività di un pulsante

1. **Aggiungere trigger di modello:** Aggiungere il markup evidenziato al modello.

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}"
          Height="{TemplateBinding Height}" ClipToBounds="True">

          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch" Stroke="Transparent"
            StrokeThickness="20"
            Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20"
          />

          <!-- Glass Rectangle -->
          <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch"
            StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
            Fill="{StaticResource MyGlassBrushResource}"
            RenderTransformOrigin="0.5,0.5">
            <Rectangle.Stroke>
              <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
                <LinearGradientBrush.GradientStops>
                  <GradientStop Offset="0.0" Color="LightBlue" />
                  <GradientStop Offset="1.0" Color="Gray" />
                </LinearGradientBrush.GradientStops>
              </LinearGradientBrush>
            </Rectangle.Stroke>

            <!-- These transforms have no effect as they
                 are declared here.
                 The reason the transforms are included is to be targets
                 for animation (see later). -->
            <Rectangle.RenderTransform>
              <TransformGroup>
                <ScaleTransform />
                <RotateTransform />
              </TransformGroup>
            </Rectangle.RenderTransform>

              <!-- A BevelBitmapEffect is applied to give the button a
                   "Beveled" look. -->
            <Rectangle.BitmapEffect>
              <BevelBitmapEffect />
            </Rectangle.BitmapEffect>
          </Rectangle>

          <!-- Present Text of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20"
              Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>

        <ControlTemplate.Triggers>       <!-- Set action triggers for the buttons and define            what the button does in response to those triggers. -->     </ControlTemplate.Triggers>
      </ControlTemplate>
    </Setter.Value>
    ```

2. **Aggiungere trigger di proprietà:** Aggiungere il markup evidenziato al `ControlTemplate.Triggers` blocco:

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     Premere F5 per eseguire l'applicazione e visualizzare l'effetto quando si esegue il puntatore del mouse sui pulsanti.

3. **Aggiungere un trigger di attivazione:** Successivamente, verranno aggiunti alcuni setter simili per gestire il caso in cui il pulsante ha lo stato attivo, ad esempio dopo che l'utente ha fatto clic su di esso.

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->
      <Trigger Property="IsMouseOver" Value="True">

        <!-- Below are three property settings that occur when the
             condition is met (user mouses over button).  -->
        <!-- Change the color of the outer rectangle when user          mouses over it. -->
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />

        <!-- Sets the glass opacity to 1, therefore, the          glass "appears" when user mouses over it. -->
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />

        <!-- Makes the text slightly blurry as though you were          looking at it through blurry glass. -->
        <Setter Property="ContentPresenter.BitmapEffect"       TargetName="myContentPresenter">
          <Setter.Value>
            <BlurBitmapEffect Radius="1" />
          </Setter.Value>
        </Setter>
      </Trigger>
      <!-- Set properties when button has focus. -->   <Trigger Property="IsFocused" Value="true">     <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />     <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />   </Trigger>

    </ControlTemplate.Triggers>
    ```

     Premere F5 per eseguire l'applicazione e fare clic su uno dei pulsanti. Si noti che il pulsante rimane evidenziato dopo aver fatto clic su di esso perché ha ancora lo stato attivo. Se si fa clic su un altro pulsante, il pulsante nuovo acquisisce lo stato attivo mentre l'ultimo lo perde.

4. **Aggiungere animazioni per** <xref:System.Windows.UIElement.MouseEnter> **e** <xref:System.Windows.UIElement.MouseLeave> **:** Successivamente, si aggiungono alcune animazioni ai trigger.   Aggiungere il markup seguente in qualsiasi punto all'interno del `ControlTemplate.Triggers` blocco.

    ```xaml
    <!-- Animations that start when mouse enters and leaves button. -->
    <EventTrigger RoutedEvent="Mouse.MouseEnter">
      <EventTrigger.Actions>
        <BeginStoryboard Name="mouseEnterBeginStoryboard">
          <Storyboard>
          <!-- This animation makes the glass rectangle shrink in the X direction. -->
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)"
              By="-0.1" Duration="0:0:0.5" />
            <!-- This animation makes the glass rectangle shrink in the Y direction. -->
            <DoubleAnimation
            Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)"
              By="-0.1" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    <EventTrigger RoutedEvent="Mouse.MouseLeave">
      <EventTrigger.Actions>
        <!-- Stopping the storyboard sets all animated properties back to default. -->
        <StopStoryboard BeginStoryboardName="mouseEnterBeginStoryboard" />
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     Il rettangolo di cristallo viene compattato quando il puntatore del mouse viene spostato sul pulsante e torna alla dimensione normale quando il puntatore viene lasciato.

     Ci sono due animazioni che vengono attivate quando il puntatore viene posizionato sul pulsante ( <xref:System.Windows.UIElement.MouseEnter> viene generato l'evento). Queste animazioni compattano il rettangolo vetro lungo l'asse X e Y. Si notino le proprietà degli <xref:System.Windows.Media.Animation.DoubleAnimation> elementi, <xref:System.Windows.Media.Animation.Timeline.Duration%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> . <xref:System.Windows.Media.Animation.Timeline.Duration%2A>Specifica che l'animazione viene eseguita oltre mezzo secondo e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifica che il vetro viene compattato del 10%.

     Il secondo trigger di evento ( <xref:System.Windows.UIElement.MouseLeave> ) arresta semplicemente la prima. Quando si arresta un oggetto <xref:System.Windows.Media.Animation.Storyboard> , tutte le proprietà animate restituiscono i valori predefiniti. Pertanto, quando l'utente sposta il puntatore del mouse sul pulsante, il pulsante Torna al modo in cui si trovava prima che il puntatore del mouse venisse spostato sul pulsante. Per ulteriori informazioni sulle animazioni, vedere [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md).

5. **Aggiungere un'animazione per quando si fa clic sul pulsante:** Il passaggio finale consiste nell'aggiungere un trigger per quando l'utente fa clic sul pulsante. Aggiungere il markup seguente in qualsiasi punto all'interno del `ControlTemplate.Triggers` blocco:

    ```xaml
    <!-- Animation fires when button is clicked, causing glass to spin.  -->
    <EventTrigger RoutedEvent="Button.Click">
      <EventTrigger.Actions>
        <BeginStoryboard>
          <Storyboard>
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[1].(RotateTransform.Angle)"
              By="360" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     Premere F5 per eseguire l'applicazione e fare clic su uno dei pulsanti. Quando si fa clic su un pulsante, il rettangolo di vetro ruota intorno.

## <a name="summary"></a>Summary
 In questa procedura dettagliata sono stati eseguiti gli esercizi seguenti:

- Destinata <xref:System.Windows.Style> a un tipo di oggetto ( <xref:System.Windows.Controls.Button> ).

- Proprietà di base controllate dei pulsanti nell'intera applicazione usando <xref:System.Windows.Style> .

- Risorse create come le sfumature da usare per i valori delle proprietà dei <xref:System.Windows.Style> Setter.

- Personalizzare l'aspetto dei pulsanti nell'intera applicazione applicando un modello ai pulsanti.

- Comportamento personalizzato per i pulsanti in risposta alle azioni dell'utente, ad esempio <xref:System.Windows.UIElement.MouseEnter> , <xref:System.Windows.UIElement.MouseLeave> e, <xref:System.Windows.Controls.Primitives.ButtonBase.Click> che includevano gli effetti di animazione.

## <a name="see-also"></a>Vedere anche

- [Creare un pulsante usando Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md)
- [Cenni sul disegno con colori a tinta unita e sfumature](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Cenni preliminari sugli effetti bitmap](../graphics-multimedia/bitmap-effects-overview.md)
