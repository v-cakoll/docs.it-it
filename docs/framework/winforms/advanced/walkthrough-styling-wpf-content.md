---
title: 'Procedura dettagliata: Stile del contenuto WPFWalkthrough: Style WPF Content'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 07241d41e3fbf270a76bd241765bfa369ee265d5
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646323"
---
# <a name="walkthrough-style-wpf-content"></a>Procedura dettagliata: Stile del contenuto WPFWalkthrough: Style WPF Content

In questo articolo viene illustrato come applicare lo stile a un controllo Windows Presentation Foundation (WPF) ospitato in un Windows Form.This article show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario Visual Studio.

## <a name="create-the-project"></a>Creare il progetto

Aprire Visual Studio e creare un nuovo progetto di applicazione `StylingWpfContent`Windows Form denominato Visual Basic o Visual C.

> [!NOTE]
> Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.

## <a name="create-the-wpf-control-types"></a>Creare i tipi di controllo WPFCreate the WPFwpf types

Dopo avere aggiunto un tipo di controllo WPF al progetto, è possibile inserirlo in un controllo <xref:System.Windows.Forms.Integration.ElementHost>.

1. Aggiungere un nuovo progetto WPF <xref:System.Windows.Controls.UserControl> alla soluzione. Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`. Per altre informazioni, vedere [Procedura dettagliata: creazione di nuovo contenuto WPF in Windows Form in fase di progettazione.](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)

2. In visualizzazione Progettazione verificare che `UserControl1` sia selezionato.

3. Nella finestra **Proprietà** impostare il <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> valore delle proprietà e su **200**.

4. Aggiungere <xref:System.Windows.Controls.Button?displayProperty=nameWithType> un controllo <xref:System.Windows.Controls.UserControl> a e impostare il valore della <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà su **Annulla**.

5. Aggiungere un <xref:System.Windows.Controls.Button?displayProperty=nameWithType> secondo <xref:System.Windows.Controls.UserControl> controllo a e <xref:System.Windows.Controls.ContentControl.Content%2A> impostare il valore della proprietà **su OK**.

6. Compilare il progetto.

## <a name="apply-a-style-to-a-wpf-control"></a>Applicare uno stile a un controllo WPFApply a Style to a WPF Control

È possibile applicare uno stile diverso a un controllo WPF per modificarne l'aspetto e il comportamento.

1. Aprire `Form1` in Progettazione Windows Form.

1. Nella **Casella degli**strumenti `UserControl1` fare doppio `UserControl1` clic per creare un'istanza di nel form.

   L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.

1. Nel pannello smart `elementHost1`tag per , fare clic su **Modifica contenuto ospitato** dall'elenco a discesa.

   `UserControl1`viene aperto in Progettazione WPF.

1. Nella visualizzazione XAML inserire il seguente codice XAML dopo il tag di apertura `<UserControl>`. Questo codice XAML crea una sfumatura con un bordo sfumato a contrasto. Quando si fa clic sul controllo, le sfumature vengono modificate per generare l'aspetto di un pulsante premuto. Per altre informazioni, vedere [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

   ```xaml
   <UserControl.Resources>
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#FFF" Offset="0.0"/>
        <GradientStop Color="#CCC" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#BBB" Offset="0.0"/>
        <GradientStop Color="#EEE" Offset="0.1"/>
        <GradientStop Color="#EEE" Offset="0.9"/>
        <GradientStop Color="#FFF" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#444" Offset="0.0"/>
        <GradientStop Color="#888" Offset="1.0"/>
    </LinearGradientBrush>

    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="{x:Type Button}">
                    <Grid x:Name="Grid">
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>
                    </Grid>
                    <ControlTemplate.Triggers>
                        <Trigger Property="IsPressed" Value="true">
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>
                        </Trigger>
                    </ControlTemplate.Triggers>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>
   </UserControl.Resources>
   ```

1. Applicare `SimpleButton` lo stile definito nel passaggio precedente al pulsante `<Button>` Annulla inserendo il codice XAML seguente nel tag del pulsante **Annulla.**

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   La dichiarazione del pulsante sarà simile al codice XAML seguente:Your button declaration will resemble the following XAML:

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. Compilare il progetto.

1. Aprire `Form1` in Progettazione Windows Form.

1. Il nuovo stile viene applicato al pulsante.

1. Scegliere **Avvia** debug **dal** menu Debug per eseguire l'applicazione.

1. Fare clic sui pulsanti **OK** e **Annulla** e visualizzare le differenze.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migrazione e interoperabilità](../../wpf/advanced/migration-and-interoperability.md)
- [Utilizzo di controlli WPF](using-wpf-controls.md)
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
