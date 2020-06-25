---
title: Creare uno stile per un controllo
description: Informazioni su come creare e fare riferimento a uno stile di controllo in Windows Presentation Foundation e .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 09/12/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: de186cd6da83ffef8a5cd59df581e88b24bc474d
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325797"
---
# <a name="create-a-style-for-a-control-in-wpf"></a>Creare uno stile per un controllo in WPF

Con Windows Presentation Foundation (WPF), è possibile personalizzare l'aspetto di un controllo esistente con lo stile riutilizzabile. Gli stili possono essere applicati a livello globale per l'app, le finestre e le pagine o direttamente ai controlli.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="create-a-style"></a>Creare uno stile

È possibile considerare un <xref:System.Windows.Style> come un modo pratico per applicare un set di valori di proprietà a uno o più elementi. È possibile usare uno stile su qualsiasi elemento che deriva da <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> , ad esempio <xref:System.Windows.Window> o <xref:System.Windows.Controls.Button> .

Il modo più comune per dichiarare uno stile è come una risorsa nella `Resources` sezione di un file XAML. Poiché gli stili sono risorse, rispettano le stesse regole di ambito che si applicano a tutte le risorse. Inserire semplicemente, dove si dichiara uno stile influiscono sul punto in cui è possibile applicare lo stile. Se ad esempio si dichiara lo stile nell'elemento radice del file XAML della definizione dell'app, lo stile può essere usato in qualsiasi punto dell'app.

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/App.xaml#AppResources)]

Se si dichiara lo stile in uno dei file XAML dell'app, lo stile può essere usato solo nel file XAML. Per altre informazioni sulle regole di ambito delle risorse, vedere [Risorse XAML](xaml-resources-define.md).

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowSingleResource.xaml#WindowResources)]

Uno stile è costituito da `<Setter>` elementi figlio che impostano proprietà sugli elementi a cui viene applicato lo stile. Nell'esempio precedente si noti che lo stile è impostato su applica ai `TextBlock` tipi tramite l' `TargetType` attributo. Lo stile imposterà <xref:System.Windows.Controls.Control.FontSize%2A> su `15` e <xref:System.Windows.Controls.Control.FontWeight%2A> su `ExtraBold` . Aggiungere un oggetto `<Setter>` per ogni proprietà modificata dallo stile.

## <a name="apply-a-style-implicitly"></a>Applicare uno stile in modo implicito

Un <xref:System.Windows.Style> è un modo pratico per applicare un set di valori di proprietà a più di un elemento. Si considerino, ad esempio, gli <xref:System.Windows.Controls.TextBlock> elementi seguenti e il relativo aspetto predefinito in una finestra.

[!code-xaml[TextBlocks](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetTextBlocks)]

![Schermata di esempio dello stile](./media/styles-and-templates-overview/stylingintro-textblocksbefore.png "StylingIntro_TextBlocksBefore")

È possibile modificare l'aspetto predefinito impostando le proprietà, ad esempio <xref:System.Windows.Controls.Control.FontSize%2A> e <xref:System.Windows.Controls.Control.FontFamily%2A> , su ogni <xref:System.Windows.Controls.TextBlock> elemento direttamente. Tuttavia, se si vuole che gli <xref:System.Windows.Controls.TextBlock> elementi condividano alcune proprietà, è possibile creare un oggetto <xref:System.Windows.Style> nella `Resources` sezione del file XAML, come illustrato di seguito.

[!code-xaml[DefaultTextBlockStyle](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetDefaultTextBlockStyle)]

Quando si imposta il <xref:System.Windows.Style.TargetType%2A> dello stile sul <xref:System.Windows.Controls.TextBlock> tipo e si omette l' `x:Key` attributo, lo stile viene applicato a tutti gli <xref:System.Windows.Controls.TextBlock> elementi che hanno come ambito lo stile, che è in genere il file XAML.

Ora gli <xref:System.Windows.Controls.TextBlock> elementi vengono visualizzati come segue.

![Schermata di esempio dello stile](./media/styles-and-templates-overview/stylingintro-textblocksbasestyle.png "StylingIntro_TextBlocksBaseStyle")

## <a name="apply-a-style-explicitly"></a>Applicare uno stile in modo esplicito

Se si aggiunge un `x:Key` attributo con valore allo stile, lo stile non viene più applicato in modo implicito a tutti gli elementi di <xref:System.Windows.Style.TargetType%2A> . Solo gli elementi che fanno riferimento in modo esplicito allo stile avranno lo stile applicato.

Ecco lo stile della sezione precedente, ma dichiarato con l' `x:Key` attributo.

[!code-xaml[ExplicitStyleDeclare](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleDeclare)]

Per applicare lo stile, impostare la <xref:System.Windows.FrameworkElement.Style%2A> proprietà dell'elemento sul `x:Key` valore utilizzando un' [estensione di markup StaticResource](../../framework/wpf/advanced/staticresource-markup-extension.md), come illustrato di seguito.

[!code-xaml[ExplicitStyleReference](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleReference)]

Si noti che al primo <xref:System.Windows.Controls.TextBlock> elemento è applicato lo stile mentre il secondo elemento TextBlock rimane invariato. Lo stile implicito della sezione precedente è stato modificato in uno stile che dichiara l' `x:Key` attributo, ovvero l'unico elemento interessato dallo stile è quello che ha fatto riferimento direttamente allo stile.

![Schermata di esempio dello stile](./media/styles-and-templates-overview/create-a-style-explicit-textblock.png "Create-a-Style-Explicit-TextBlock")

Una volta applicato uno stile, in modo esplicito o implicito, esso diventa sealed e non può essere modificato. Se si desidera modificare uno stile applicato, creare un nuovo stile per sostituire quello esistente. Per altre informazioni, vedere la proprietà <xref:System.Windows.Style.IsSealed%2A>.

È possibile creare un oggetto che sceglie uno stile da applicare in base alla logica personalizzata. Per un esempio, vedere l'esempio fornito per la <xref:System.Windows.Controls.StyleSelector> classe.

## <a name="apply-a-style-programmatically"></a>Applicare uno stile a livello di codice

Per assegnare uno stile denominato a un elemento a livello di codice, ottenere lo stile dalla raccolta Resources e assegnarlo alla <xref:System.Windows.FrameworkElement.Style%2A> proprietà dell'elemento. Gli elementi di una raccolta Resources sono di tipo <xref:System.Object> . Pertanto, è necessario eseguire il cast dello stile recuperato a un oggetto <xref:System.Windows.Style?displayProperty=fullName> prima di assegnarlo alla `Style` Proprietà. Il codice seguente, ad esempio, imposta lo stile di un oggetto `TextBlock` denominato `textblock1` sullo stile definito `TitleText` .

[!code-csharp[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml.cs#SnippetSetStyleCode)]
[!code-vb[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/MainWindow.xaml.vb#SnippetSetStyleCode)]

## <a name="extend-a-style"></a>Estendi uno stile

Forse si vuole che i due <xref:System.Windows.Controls.TextBlock> elementi condividano alcuni valori di proprietà, ad esempio <xref:System.Windows.Controls.Control.FontFamily%2A> e centrato <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> . Si vuole anche che il testo **Immagini personali** includa alcune proprietà aggiuntive. A tale scopo, è possibile creare un nuovo stile basato sul primo stile, come illustrato di seguito.

[!code-xaml[DefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

[!code-xaml[TextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

Questo `TextBlock` stile è ora centrato, usa un `Comic Sans MS` tipo di carattere con le dimensioni `26` e il colore di primo piano impostato sull'oggetto <xref:System.Windows.Media.LinearGradientBrush> illustrato nell'esempio. Si noti che esegue l'override del <xref:System.Windows.Controls.Control.FontSize%2A> valore dello stile di base. Se è presente più di un <xref:System.Windows.Setter> che punta alla stessa proprietà in un oggetto <xref:System.Windows.Style> , l'oggetto `Setter` dichiarato per ultimo ha la precedenza.

Di seguito sono indicati gli <xref:System.Windows.Controls.TextBlock> elementi che ora hanno un aspetto simile al seguente:

![TextBlock con stile](./media/styles-and-templates-overview/stylingintro-textblocks.png "StylingIntro_TextBlocks")

Questo `TitleText` stile estende lo stile creato per il <xref:System.Windows.Controls.TextBlock> tipo, a cui viene fatto riferimento con `BasedOn="{StaticResource {x:Type TextBlock}}"` . È anche possibile estendere uno stile che dispone di un oggetto `x:Key` usando l'oggetto `x:Key` dello stile. Se, ad esempio, era presente uno stile denominato `Header1` e si desidera estendere tale stile, utilizzare `BasedOn="{StaticResource Header1}"` .

## <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>Relazione tra la proprietà TargetType e l'attributo x:Key

Come illustrato in precedenza, l'impostazione della <xref:System.Windows.Style.TargetType%2A> proprietà su `TextBlock` senza assegnare lo stile a `x:Key` comporta l'applicazione dello stile a tutti <xref:System.Windows.Controls.TextBlock> gli elementi. In questo caso, l'attributo `x:Key` è impostato in modo implicito su `{x:Type TextBlock}`. Ciò significa che se si imposta in modo esplicito il `x:Key` valore su un valore diverso da `{x:Type TextBlock}` , <xref:System.Windows.Style> non viene applicato automaticamente a tutti `TextBlock` gli elementi. Al contrario, è necessario applicare lo stile (usando il `x:Key` valore) agli `TextBlock` elementi in modo esplicito. Se lo stile si trova nella sezione Resources e non si imposta la `TargetType` proprietà nello stile, è necessario impostare l' `x:Key` attributo.

Oltre a fornire un valore predefinito per `x:Key` , la `TargetType` proprietà specifica il tipo a cui si applicano le proprietà del setter. Se non si specifica un oggetto `TargetType` , è necessario qualificare le proprietà negli <xref:System.Windows.Setter> oggetti con un nome di classe usando la sintassi `Property="ClassName.Property"` . Ad esempio, anziché impostare `Property="FontSize"` , è necessario impostare <xref:System.Windows.Setter.Property%2A> su `"TextBlock.FontSize"` o su `"Control.FontSize"` .

Si noti inoltre che molti controlli WPF sono costituiti da una combinazione di altri controlli WPF. Se si crea uno stile che si applica a tutti i controlli di un tipo, è possibile che si ottengano risultati imprevisti. Se, ad esempio, si crea uno stile destinato al <xref:System.Windows.Controls.TextBlock> tipo in un oggetto <xref:System.Windows.Window> , lo stile viene applicato a tutti i `TextBlock` controlli della finestra, anche se `TextBlock` fa parte di un altro controllo, ad esempio <xref:System.Windows.Controls.ListBox> .

## <a name="see-also"></a>Vedi anche

<!-- - [Create a style for a control](styles-templates-create-apply-template.md) -->
- [Panoramica delle risorse XAML](xaml-resources-define.md)
- [Cenni preliminari su XAML (WPF & .NET Core)](xaml.md)
