---
title: 'Procedura dettagliata: creazione di un pulsante tramite XAML'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5c5efa9f8787e65d59e1b544632e806bf3fbbc81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a>Procedura dettagliata: creazione di un pulsante tramite XAML
L'obiettivo di questa procedura dettagliata consiste nel comprendere come creare un pulsante animato per l'utilizzo in un [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] dell'applicazione. Questa procedura dettagliata utilizza stili e un modello per creare una risorsa pulsante personalizzato che consente il riutilizzo del codice e la separazione logica dalla dichiarazione del pulsante. Questa procedura dettagliata viene scritta interamente in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
> [!IMPORTANT]
>  In questa procedura dettagliata per i passaggi per creare l'applicazione digitando oppure copiando e incollando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] in Microsoft [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Se si preferisce imparare a utilizzare uno strumento di progettazione (Microsoft Expression Blend) per creare la stessa applicazione, vedere [creare un pulsante by Using Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md).  
  
 Nella figura seguente mostra i pulsanti finiti.  
  
 ![Pulsanti personalizzati che sono stati creati tramite XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")  
  
## <a name="create-basic-buttons"></a>Creare pulsanti di base  
 Per iniziare, creare un nuovo progetto e aggiungere alcuni pulsanti alla finestra.  
  
#### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a>Per creare un nuovo progetto WPF e aggiungere pulsanti alla finestra  
  
1.  Avviare[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].  
  
2.  **Creare un nuovo progetto WPF:** sul **File** dal menu **New**, quindi fare clic su **progetto**. Trovare il **applicazione WPF (Windows)** modello e il nome del progetto "AnimatedButton". Verrà creata la struttura per l'applicazione.  
  
3.  **Aggiungere i pulsanti predefiniti di base:** tutti i file necessari per questa procedura dettagliata vengono forniti dal modello. Facendo doppio clic sopra in Esplora soluzioni, aprire il file Window1. Xaml. Per impostazione predefinita, è presente un <xref:System.Windows.Controls.Grid> elemento Window1. Xaml. Rimuovere il <xref:System.Windows.Controls.Grid> elemento e aggiungere alcuni pulsanti per il [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] pagina digitando oppure copiando e incollando il codice evidenziato di seguito in Window1. XAML:  
  
    ```xaml  
    <Window x:Class="AnimatedButton.Window1"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      Title="AnimatedButton" Height="300" Width="300"   
      Background="Black">   <!-- Buttons arranged vertically inside a StackPanel. -->   <StackPanel HorizontalAlignment="Left">     <Button>Button 1</Button>     <Button>Button 2</Button>     <Button>Button 3</Button>   </StackPanel>  
  
    </Window>  
    ```  
  
     Premere F5 per eseguire l'applicazione. dovrebbe essere una serie di pulsanti simile alla figura riportata di seguito.  
  
     ![Tre pulsanti di base](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")  
  
     Dopo avere creato i pulsanti di base, sono completate le operazioni nel file Window1. Xaml. Il resto della procedura dettagliata è incentrata sul file app. XAML, la definizione di stili e un modello per i pulsanti.  
  
## <a name="set-basic-properties"></a>Impostare le proprietà di base  
 Successivamente, consente di impostare alcune proprietà per controllare l'aspetto del pulsante e il layout dei pulsanti. Anziché impostare le proprietà i pulsanti singolarmente, si utilizzerà le risorse per definire le proprietà di pulsante per l'intera applicazione. Le risorse dell'applicazione sono concettualmente simili esterni [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] per le pagine Web; tuttavia, le risorse sono molto più potenti [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)], come verrà visualizzato al termine di questa procedura dettagliata. Per ulteriori informazioni sulle risorse, vedere [risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
#### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a>Per utilizzare gli stili per impostare le proprietà di base per i pulsanti  
  
1.  **Definire un blocco Resources:** aprire app. XAML e aggiungere il markup evidenziato seguente se non è già presente:  
  
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
  
     Ambito di risorse è determinato in cui si definisce la risorsa. Definizione delle risorse in `Application.Resources` nell'app. XAML file abilita la risorsa essere utilizzato da un punto qualsiasi nell'applicazione. Per ulteriori informazioni sulla definizione dell'ambito delle risorse, vedere [risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
2.  **Creare uno stile e definire i valori delle proprietà di base:** il markup seguente per aggiungere il `Application.Resources` blocco. Questo codice crea un <xref:System.Windows.Style> che si applica a tutti i pulsanti nell'applicazione, l'impostazione di <xref:System.Windows.FrameworkElement.Width%2A> dei pulsanti su 90 e <xref:System.Windows.FrameworkElement.Margin%2A> a 10:  
  
    ```xaml  
    <Application.Resources>  
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>  
    </Application.Resources>  
    ```  
  
     Il <xref:System.Windows.Style.TargetType%2A> proprietà specifica che lo stile applicato a tutti gli oggetti di tipo <xref:System.Windows.Controls.Button>. Ogni <xref:System.Windows.Setter> imposta un valore della proprietà diverso per il <xref:System.Windows.Style>. Pertanto, a questo punto ogni pulsante dell'applicazione ha una larghezza di 90 e un margine di 10.  Se si preme F5 per eseguire l'applicazione, visualizzare la finestra seguente.  
  
     ![Pulsanti con una larghezza di 90 e un margine di 10](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")  
  
     È molto più, che è possibile eseguire con gli stili, inclusi i diversi modi per ottimizzare gli oggetti che sono assegnati, specificando i valori di proprietà complessa e anche utilizzati come input per altri stili. Per altre informazioni, vedere [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
3.  **Impostare un valore di proprietà di stile a una risorsa:** un modo semplice per riutilizzare i valori e oggetti comunemente definiti grazie alle risorse. È particolarmente utile definire valori complessi utilizzando le risorse per rendere il codice più modulare. Aggiungere il markup evidenziato seguente in App. Xaml.  
  
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
  
     Direttamente sotto il `Application.Resources` blocco, è stata creata una risorsa denominata "GrayBlueGradientBrush". Risorsa che definisce una sfumatura orizzontale. Questa risorsa può essere utilizzata come valore della proprietà da qualsiasi posizione nell'applicazione, anche all'interno di setter di stile del pulsante per la <xref:System.Windows.Controls.Control.Background%2A> proprietà. A questo punto, tutti i pulsanti hanno un <xref:System.Windows.Controls.Control.Background%2A> valore della proprietà di questo tipo di sfumatura.  
  
     Premere F5 per eseguire l'applicazione. Dovrebbe essere simile al seguente.  
  
     ![Pulsanti con uno sfondo sfumato](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")  
  
## <a name="create-a-template-that-defines-the-look-of-the-button"></a>Creare un modello che definisce l'aspetto del pulsante  
 In questa sezione creare un modello che consente di personalizzare l'aspetto (presentazione) del pulsante. La presentazione del pulsante è composta da più oggetti, tra cui rettangoli e altri componenti per assegnare al pulsante un aspetto univoco.  
  
 Fino a questo punto, il controllo dell'aspetto di pulsanti nell'applicazione è stato limitato alla modifica delle proprietà del pulsante. Cosa accade se si desidera apportare modifiche più radicale all'aspetto del pulsante? I modelli consentono un controllo maggiore la presentazione di un oggetto. Poiché i modelli possono essere utilizzati all'interno di stili, è possibile applicare un modello a tutti gli oggetti a cui si applica lo stile (in questa procedura dettagliata, il pulsante).  
  
#### <a name="to-use-the-template-to-define-the-look-of-the-button"></a>Usare il modello per definire l'aspetto del pulsante  
  
1.  **Impostare il modello:** poiché i controlli come <xref:System.Windows.Controls.Button> hanno un <xref:System.Windows.Controls.Control.Template%2A> proprietà, è possibile definire il valore della proprietà di modello esattamente come gli altri valori di proprietà impostati in un <xref:System.Windows.Style> utilizzando un <xref:System.Windows.Setter>. Aggiungere il markup evidenziato seguente allo stile del pulsante.  
  
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
  
2.  **Presentazione del pulsante di ALTER:** a questo punto, è necessario definire il modello. Aggiungere il seguente markup evidenziato. In questo markup specifica due <xref:System.Windows.Shapes.Rectangle> gli elementi con angoli arrotondati, seguito da un <xref:System.Windows.Controls.DockPanel>. Il <xref:System.Windows.Controls.DockPanel> viene utilizzato per ospitare il <xref:System.Windows.Controls.ContentPresenter> del pulsante. Oggetto <xref:System.Windows.Controls.ContentPresenter> viene visualizzato il contenuto del pulsante. In questa procedura dettagliata, il contenuto è testo ("Pulsante 1", "Button 2", "Button 3"). Tutti i componenti del modello (i rettangoli e <xref:System.Windows.Controls.DockPanel>) sono posizionati all'interno di un <xref:System.Windows.Controls.Grid>.  
  
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
  
     ![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")  
  
3.  **Aggiungere un effetto cristallo al modello:** si aggiungerà l'effetto cristallo. È innanzitutto necessario creare alcune risorse che creano un effetto cristallo. Aggiungere queste risorse sfumatura in qualsiasi punto all'interno di `Application.Resources` blocco:  
  
    ```xaml  
    <Application.Resources>  
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">     <GradientStop Color="WhiteSmoke" Offset="0.2" />     <GradientStop Color="Transparent" Offset="0.4" />     <GradientStop Color="WhiteSmoke" Offset="0.5" />     <GradientStop Color="Transparent" Offset="0.75" />     <GradientStop Color="WhiteSmoke" Offset="0.9" />     <GradientStop Color="Transparent" Offset="1" />   </GradientStopCollection>   <LinearGradientBrush x:Key="MyGlassBrushResource"     StartPoint="0,0" EndPoint="1,1" Opacity="0.75"     GradientStops="{StaticResource MyGlassGradientStopsResource}" />  
    <!-- Styles and other resources below here. -->  
    ```  
  
     Queste risorse sono utilizzate come il <xref:System.Windows.Shapes.Shape.Fill%2A> per un rettangolo da inserire nel <xref:System.Windows.Controls.Grid> del modello del pulsante. Aggiungere il markup evidenziato seguente al modello.  
  
    ```  
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
  
        <!-- Glass Rectangle -->     <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"       VerticalAlignment="Stretch"       StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"       Fill="{StaticResource MyGlassBrushResource}"       RenderTransformOrigin="0.5,0.5">       <Rectangle.Stroke>         <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">           <LinearGradientBrush.GradientStops>             <GradientStop Offset="0.0" Color="LightBlue" />             <GradientStop Offset="1.0" Color="Gray" />           </LinearGradientBrush.GradientStops>         </LinearGradientBrush>       </Rectangle.Stroke>       <!-- These transforms have no effect as they are declared here.             The reason the transforms are included is to be targets             for animation (see later). -->       <Rectangle.RenderTransform>         <TransformGroup>           <ScaleTransform />           <RotateTransform />         </TransformGroup>       </Rectangle.RenderTransform>       <!-- A BevelBitmapEffect is applied to give the button a             "Beveled" look. -->       <Rectangle.BitmapEffect>         <BevelBitmapEffect />       </Rectangle.BitmapEffect>     </Rectangle>  
  
        <!-- Present Text of the button. -->  
        <DockPanel Name="myContentPresenterDockPanel">  
          <ContentPresenter x:Name="myContentPresenter" Margin="20"   
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />  
        </DockPanel>  
      </Grid>  
    </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     Si noti che il <xref:System.Windows.UIElement.Opacity%2A> del rettangolo con il `x:Name` proprietà di "glassCube" è 0, pertanto quando si esegue l'esempio, non viene visualizzato il rettangolo con effetto cristallo visibile. Questo avviene perché seguito verranno aggiunti i trigger per il modello per quando l'utente interagisce con il pulsante. Tuttavia, è possibile visualizzare l'aspetto pulsante ora modificando il <xref:System.Windows.UIElement.Opacity%2A> valore su 1 e l'esecuzione dell'applicazione. Vedere la figura riportata di seguito. Prima di procedere al passaggio successivo, modificare il <xref:System.Windows.UIElement.Opacity%2A> reimpostarlo su 0.  
  
     ![Pulsanti personalizzati che sono stati creati tramite XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")  
  
## <a name="create-button-interactivity"></a>Creare l'interattività del pulsante  
 In questa sezione si creerà i trigger di proprietà e i trigger di evento per modificare i valori delle proprietà ed eseguire le animazioni in risposta alle azioni dell'utente, ad esempio spostando il puntatore del mouse su di esso e fare clic su.  
  
 Un modo semplice per aggiungere interattività (puntatore del mouse, in uscita del mouse, fare clic e così via) consiste nel definire i trigger all'interno del modello o uno stile. Per creare un <xref:System.Windows.Trigger>, si definisce una proprietà "condizione", ad esempio: pulsante <xref:System.Windows.UIElement.IsMouseOver%2A> è uguale al valore della proprietà `true`. Definire quindi Setter (azioni) che si verificano quando viene soddisfatta la condizione del trigger.  
  
#### <a name="to-create-button-interactivity"></a>Per creare l'interattività del pulsante  
  
1.  **Aggiungere trigger di modelli:** aggiungere il markup evidenziato al modello.  
  
    ```  
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
  
2.  **Aggiungere trigger di proprietà:** aggiungere il markup evidenziato per il `ControlTemplate.Triggers` blocco:  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>  
  
    <ControlTemplate.Triggers/>  
    ```  
  
     Premere F5 per eseguire l'applicazione e vedere l'effetto quando si esegue il puntatore del mouse sui pulsanti.  
  
3.  **Aggiungere un trigger di messa a fuoco:** successivamente, aggiungeremo alcuni metodi di impostazione per gestire il caso, quando il pulsante è attivo (ad esempio, dopo che l'utente fa clic).  
  
    ```  
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
  
     Premere F5 per eseguire l'applicazione e fare clic su uno dei pulsanti. Si noti che il pulsante rimane evidenziato dopo aver selezionato perché è ancora attiva. Se si fa clic su un altro pulsante, il nuovo pulsante Ottiene lo stato attivo mentre l'ultimo perde.  
  
4.  **Aggiungere le animazioni per** <xref:System.Windows.UIElement.MouseEnter> **e** <xref:System.Windows.UIElement.MouseLeave> **:** successivo verranno aggiunte alcune animazioni ai trigger. Aggiungere il markup seguente in un punto qualsiasi all'interno del `ControlTemplate.Triggers` blocco.  
  
    ```  
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
  
     Il rettangolo con effetto cristallo compatta quando il puntatore del mouse viene spostato su di esso e torna allo dimensioni normali quando il puntatore esce.  
  
     Esistono due animazioni che vengono attivate quando il puntatore viene spostato sul pulsante (<xref:System.Windows.UIElement.MouseEnter> evento). Queste animazioni riducono il rettangolo con effetto cristallo lungo l'asse X e Y. Si notino le proprietà nel <xref:System.Windows.Media.Animation.DoubleAnimation> elementi, ovvero <xref:System.Windows.Media.Animation.Timeline.Duration%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>. Il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifica che l'animazione si verifica per mezzo secondo, e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifica che l'effetto cristallo viene ridotto del 10%.  
  
     Il secondo trigger di evento (<xref:System.Windows.UIElement.MouseLeave>) interrompe semplicemente il primo. Quando si arresta un <xref:System.Windows.Media.Animation.Storyboard>, tutte le proprietà animate restituiscono i valori predefiniti. Pertanto, quando l'utente sposta il puntatore sul pulsante, il pulsante Torna al modo in cui che si trovava prima di spostata il puntatore del mouse su di esso. Per ulteriori informazioni sulle animazioni, vedere [panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
5.  **Aggiungere un'animazione quando si fa clic sul pulsante:** il passaggio finale consiste nell'aggiungere un trigger per quando l'utente fa clic sul pulsante. Aggiungere il markup seguente in un punto qualsiasi all'interno del `ControlTemplate.Triggers` blocco:  
  
    ```  
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
  
     Premere F5 per eseguire l'applicazione e fare clic su uno dei pulsanti. Quando si fa clic su un pulsante, il rettangolo con effetto cristallo ruota.  
  
## <a name="summary"></a>Riepilogo  
 In questa procedura dettagliata, sono stati eseguiti gli esercizi seguenti:  
  
-   Destinazione un <xref:System.Windows.Style> a un tipo di oggetto (<xref:System.Windows.Controls.Button>).  
  
-   Controllare le proprietà di base dei pulsanti nell'intera applicazione usando il <xref:System.Windows.Style>.  
  
-   Create risorse quali sfumature da utilizzare per i valori delle proprietà di <xref:System.Windows.Style> Setter.  
  
-   Personalizzare l'aspetto dei pulsanti dell'intera applicazione applicando un modello per i pulsanti.  
  
-   Personalizzare il comportamento dei pulsanti in risposta alle azioni dell'utente (ad esempio <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, e <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) che includevano effetti di animazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Creare un pulsante usando Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Cenni sul disegno con colori a tinta unita e sfumature](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Panoramica sugli effetti bitmap](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)
