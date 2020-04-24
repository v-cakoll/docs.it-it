---
title: 'Procedura dettagliata: creazione di un pulsante tramite XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: a8cc227703e81e5de9dea7e44e10dfecca2cd05c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646473"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a>Procedura dettagliata: creazione di un pulsante tramite XAML

L'obiettivo di questa procedura dettagliata consiste nell'imparare a creare un pulsante animato da utilizzare in un'applicazione Windows Presentation Foundation (WPF). In questa procedura dettagliata vengono utilizzati gli stili e un modello per creare una risorsa pulsante personalizzata che consente il riutilizzo del codice e la separazione della logica del pulsante dalla dichiarazione del pulsante. Questa procedura dettagliata [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]è scritta interamente in .

> [!IMPORTANT]
> Questa procedura dettagliata illustra i passaggi per la creazione [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] dell'applicazione digitandoo o copiando e incollando in Visual Studio.This walkthrough guides you through the steps for creating the application by typing or copying and pasting into Visual Studio. Se si preferisce imparare a utilizzare una finestra di progettazione per creare la stessa applicazione, vedere [Creare un pulsante utilizzando Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).

La figura seguente mostra i pulsanti finiti.

![Pulsanti personalizzati creati utilizzando XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-basic-buttons"></a>Creazione di pulsanti di base

Iniziamo creando un nuovo progetto e aggiungendo alcuni pulsanti alla finestra.

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a>Per creare un nuovo progetto WPF e aggiungere pulsanti alla finestraTo create a new WPF project and add buttons to the window

1. Avviare Visual Studio.

2. **Creare un nuovo progetto WPF:Create** a new WPF project: Scegliere **Nuovo**dal menu **File** , quindi fare clic su **Progetto**. Individuare il modello **di applicazione Windows (WPF)** e denominare il progetto "AnimatedButton". Questo creerà lo scheletro per l'applicazione.

3. **Aggiungere pulsanti predefiniti di base:** Tutti i file necessari per questa procedura dettagliata vengono forniti dal modello. Aprire il file Window1.xaml facendo doppio clic su di esso in Esplora soluzioni. Per impostazione predefinita, è presente un elemento in Window1.xaml.By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml. Rimuovi <xref:System.Windows.Controls.Grid> l'elemento e aggiungi [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] alcuni pulsanti alla pagina digitando o copiando e incollando il seguente codice evidenziato in Window1.xaml:

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

     Premere F5 per eseguire l'applicazione; si dovrebbe vedere un set di pulsanti che assomiglia alla figura seguente.

     ![Tre pulsanti di base](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")

     Dopo aver creato i pulsanti di base, si sta terminando di lavorare nel file Window1.xaml. Il resto della procedura dettagliata è incentrato sul file app.xaml, sulla definizione degli stili e su un modello per i pulsanti.

## <a name="set-basic-properties"></a>Impostazione delle proprietà di base

Successivamente, è possibile impostare alcune proprietà su questi pulsanti per controllare l'aspetto e il layout del pulsante. Anziché impostare le proprietà sui pulsanti singolarmente, si utilizzeranno le risorse per definire le proprietà dei pulsanti per l'intera applicazione. Le risorse dell'applicazione sono concettualmente simili ai css (Cascading Style Sheets) esterni per le pagine Web. tuttavia, le risorse sono molto più potenti dei fogli di stile CSS (Cascading Style Sheets), come si vedrà alla fine di questa procedura dettagliata. Per altre informazioni sulle risorse, vedere [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a>Per utilizzare gli stili per impostare le proprietà di base sui pulsanti

1. **Definire un blocco Application.Resources:Define an Application.Resources block:** Apri app.xaml e aggiungi il markup evidenziato seguente, se non è già presente:

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

     L'ambito della risorsa è determinato dalla posizione in cui si definisce la risorsa. La definizione delle risorse nel `Application.Resources` file app.xaml consente di usare la risorsa da qualsiasi punto dell'applicazione. Per altre informazioni sulla definizione dell'ambito delle risorse, vedere [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

2. Creare uno stile e definire i valori di **proprietà di base con esso:Create** a style and define basic property values with it: Aggiungere il markup `Application.Resources` seguente al blocco. Questo markup <xref:System.Windows.Style> crea un che si applica a <xref:System.Windows.FrameworkElement.Width%2A> tutti i pulsanti <xref:System.Windows.FrameworkElement.Margin%2A> nell'applicazione, impostando il dei pulsanti su 90 e il a 10:

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     La <xref:System.Windows.Style.TargetType%2A> proprietà specifica che lo stile si <xref:System.Windows.Controls.Button>applica a tutti gli oggetti di tipo . Ognuno <xref:System.Windows.Setter> imposta un valore <xref:System.Windows.Style>di proprietà diverso per il file . Pertanto, a questo punto ogni pulsante nell'applicazione ha una larghezza di 90 e un margine di 10.  Se si preme F5 per eseguire l'applicazione, viene visualizzata la finestra seguente.

     ![Pulsanti con una larghezza di 90 e un margine di 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")

     C'è molto di più che si può fare con gli stili, tra cui una varietà di modi per ottimizzare quali oggetti sono mirati, specificando valori di proprietà complessi, e anche utilizzando gli stili come input per altri stili. Per altre informazioni, vedere [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

3. **Impostare il valore di una proprietà di stile su una risorsa:Set a style property value to a resource:** Le risorse consentono un modo semplice per riutilizzare oggetti e valori comunemente definiti. È particolarmente utile definire valori complessi usando le risorse per rendere il codice più modulare. Aggiungi il markup evidenziato seguente a app.xaml.

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

     Direttamente sotto `Application.Resources` il blocco, è stata creata una risorsa denominata "GrayBlueGradientBrush". Questa risorsa definisce una sfumatura orizzontale. Questa risorsa può essere utilizzata come valore della proprietà da qualsiasi punto <xref:System.Windows.Controls.Control.Background%2A> dell'applicazione, incluso il setter di stile del pulsante per la proprietà. A questo punto, <xref:System.Windows.Controls.Control.Background%2A> tutti i pulsanti hanno un valore di proprietà di questa sfumatura.

     Premere F5 per eseguire l'applicazione. Dovrebbe essere simile al seguente.

     ![Pulsanti con uno sfondo sfumato](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")

## <a name="create-a-template-that-defines-the-look-of-the-button"></a>Creazione di un modello che definisce l'aspetto del pulsante

In questa sezione viene creato un modello che personalizza l'aspetto (presentazione) del pulsante. La presentazione del pulsante è composta da diversi oggetti, tra cui rettangoli e altri componenti per conferire al pulsante un aspetto univoco.

Finora, il controllo dell'aspetto dei pulsanti nell'applicazione è stato limitato alla modifica delle proprietà del pulsante. Cosa succede se si desidera apportare modifiche più radicali all'aspetto del pulsante? I modelli consentono un potente controllo sulla presentazione di un oggetto. Poiché i modelli possono essere utilizzati all'interno di stili, è possibile applicare un modello a tutti gli oggetti a cui si applica lo stile (in questa procedura dettagliata, il pulsante).

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a>Per utilizzare il modello per definire l'aspetto del pulsante

1. **Impostare il modello:** Poiché <xref:System.Windows.Controls.Button> i <xref:System.Windows.Controls.Control.Template%2A> controlli come dispongono di una proprietà, è possibile definire <xref:System.Windows.Style> il <xref:System.Windows.Setter>valore della proprietà del modello come gli altri valori di proprietà impostati in un oggetto using a . Aggiungere il markup evidenziato seguente allo stile del pulsante.

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

2. **Cambia presentazione pulsante:** A questo punto, è necessario definire il modello. Aggiungere il markup evidenziato seguente. Questo markup specifica <xref:System.Windows.Shapes.Rectangle> due elementi con bordi <xref:System.Windows.Controls.DockPanel>arrotondati, seguiti da un oggetto . L'oggetto <xref:System.Windows.Controls.DockPanel> viene <xref:System.Windows.Controls.ContentPresenter> utilizzato per ospitare il pulsante. A <xref:System.Windows.Controls.ContentPresenter> visualizza il contenuto del pulsante. In questa procedura dettagliata, il contenuto è testo ("Pulsante 1", "Pulsante 2", "Pulsante 3"). Tutti i componenti del modello (i rettangoli e <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Grid>il ) sono disposti all'interno di un oggetto .

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

3. **Aggiungere un effetto vetro al modello:** Successivamente si aggiungerà il vetro. Per prima cosa si creano alcune risorse che creano un effetto sfumatura di vetro. Aggiungere queste risorse sfumatura in qualsiasi punto del blocco:Add these gradient resources anywhere within the `Application.Resources` block:

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

     Queste risorse vengono <xref:System.Windows.Shapes.Shape.Fill%2A> utilizzate come per un <xref:System.Windows.Controls.Grid> rettangolo che inseriamo nel modello di pulsante. Aggiungere il markup evidenziato seguente al modello.

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

     Si noti che <xref:System.Windows.UIElement.Opacity%2A> il `x:Name` rettangolo con la proprietà di "glassCube" è 0, pertanto quando si esegue l'esempio, non viene visualizzato il rettangolo di vetro sovrapposto. Questo perché in seguito aggiungeremo trigger al modello per quando l'utente interagisce con il pulsante. Tuttavia, è possibile visualizzare l'aspetto <xref:System.Windows.UIElement.Opacity%2A> del pulsante modificando il valore in 1 ed eseguendo l'applicazione. Vedere la figura seguente. Prima di procedere al passaggio successivo, impostare la riadesu0 <xref:System.Windows.UIElement.Opacity%2A> su 0.

     ![Pulsanti personalizzati creati utilizzando XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-button-interactivity"></a>Crea interattività pulsante

In questa sezione verranno creati trigger di proprietà e trigger di evento per modificare i valori delle proprietà ed eseguire animazioni in risposta alle azioni dell'utente, ad esempio spostando il puntatore del mouse sul pulsante e facendo clic.

Un modo semplice per aggiungere interattività (mouse-over, mouse-leave, click e così via) consiste nel definire i trigger all'interno del modello o dello stile. Per creare <xref:System.Windows.Trigger>una , si definisce una proprietà <xref:System.Windows.UIElement.IsMouseOver%2A> "condizione", `true`ad esempio: il valore della proprietà button è uguale a . È quindi possibile definire i setter (azioni) che si verificano quando la condizione del trigger è true.

### <a name="to-create-button-interactivity"></a>Per creare l'interattività dei pulsanti

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

2. **Aggiungere trigger di proprietà:** Aggiungere il markup `ControlTemplate.Triggers` evidenziato al blocco:

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     Premere F5 per eseguire l'applicazione e vedere l'effetto mentre si esegue il puntatore del mouse sui pulsanti.

3. **Aggiungere un trigger di messa a fuoco:Add** a focus trigger: Successivamente, aggiungeremo alcuni setter simili per gestire il caso in cui il pulsante ha lo stato attivo (ad esempio, dopo che l'utente fa clic su di esso).

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

     Premere F5 per eseguire l'applicazione e fare clic su uno dei pulsanti. Si noti che il pulsante rimane evidenziato dopo aver fatto clic su di esso perché ha ancora lo stato attivo. Se si fa clic su un altro pulsante, il nuovo pulsante ottiene lo stato attivo mentre l'ultimo lo perde.

4. **Aggiungi animazioni per** <xref:System.Windows.UIElement.MouseEnter> **e** <xref:System.Windows.UIElement.MouseLeave> **:** Successivamente aggiungiamo alcune animazioni ai trigger.   Aggiungere il markup seguente `ControlTemplate.Triggers` in un punto qualsiasi all'interno del blocco.

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

     Il rettangolo di vetro si riduce quando il puntatore del mouse si sposta sul pulsante e torna alle dimensioni normali quando il puntatore esce.

     Esistono due animazioni che vengono attivate quando<xref:System.Windows.UIElement.MouseEnter> il puntatore passa sopra il pulsante (viene generato l'evento). Queste animazioni riducono il rettangolo di vetro lungo gli assi X e Y. Si notino <xref:System.Windows.Media.Animation.DoubleAnimation> le <xref:System.Windows.Media.Animation.Timeline.Duration%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>proprietà degli elementi, e . Specifica <xref:System.Windows.Media.Animation.Timeline.Duration%2A> che l'animazione si verifica <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> per più di mezzo secondo e specifica che il vetro si riduce del 10%.

     Il secondo trigger<xref:System.Windows.UIElement.MouseLeave>di evento ( ) arresta semplicemente il primo. Quando si <xref:System.Windows.Media.Animation.Storyboard>interrompe un oggetto , tutte le proprietà animate tornano ai valori predefiniti. Pertanto, quando l'utente sposta il puntatore fuori dal pulsante, il pulsante torna al modo in cui era prima che il puntatore del mouse spostato sul pulsante. Per ulteriori informazioni sulle animazioni, consultate [Cenni preliminari](../graphics-multimedia/animation-overview.md)sulle animazioni.

5. **Aggiungere un'animazione per quando si fa clic sul pulsante:** Il passaggio finale consiste nell'aggiungere un trigger per quando l'utente fa clic sul pulsante. Aggiungere il markup seguente `ControlTemplate.Triggers` in qualsiasi punto all'interno del blocco:

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
 In questa procedura dettagliata sono stati eseguiti gli esercizi seguenti:In this walkthrough, you performed the following exercises:

- Destinato <xref:System.Windows.Style> a un tipo<xref:System.Windows.Controls.Button>di oggetto ( ).

- Controllate le proprietà di base dei <xref:System.Windows.Style>pulsanti nell'intera applicazione utilizzando il metodo .

- Risorse create come sfumature da utilizzare <xref:System.Windows.Style> per i valori delle proprietà dei setter.

- Personalizzato l'aspetto dei pulsanti nell'intera applicazione applicando un modello ai pulsanti.

- Comportamento personalizzato per i pulsanti in risposta <xref:System.Windows.UIElement.MouseEnter> <xref:System.Windows.UIElement.MouseLeave>alle <xref:System.Windows.Controls.Primitives.ButtonBase.Click>azioni dell'utente (ad esempio , e ) che includevano effetti di animazione.

## <a name="see-also"></a>Vedere anche

- [Creare un pulsante usando Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md)
- [Cenni sul disegno con colori a tinta unita e sfumature](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Cenni preliminari sugli effetti bitmap](../graphics-multimedia/bitmap-effects-overview.md)
