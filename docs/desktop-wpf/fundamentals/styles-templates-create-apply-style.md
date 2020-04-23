---
title: Creare uno stile per un controllo
description: Informazioni su come creare e fare riferimento a uno stile di controllo in Windows Presentation Foundation e .NET Core.Learn how to create and reference a control style in Windows Presentation Foundation and .NET Core.
author: thraka
ms.author: adegeo
ms.date: 09/12/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: 2956dbf93a1d34feca31d3ab10536f5089010189
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "82071269"
---
# <a name="create-a-style-for-a-control-in-wpf"></a>Creare uno stile per un controllo in WPFCreate a style for a control in WPFWPF

Con Windows Presentation Foundation (WPF), è possibile personalizzare l'aspetto di un controllo esistente con il proprio stile riutilizzabile. Gli stili possono essere applicati globalmente all'app, alle finestre e alle pagine o direttamente ai controlli.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="create-a-style"></a>Creare uno stile

È possibile considerare <xref:System.Windows.Style> un modo pratico per applicare un set di valori di proprietà a uno o più elementi. È possibile utilizzare uno stile su <xref:System.Windows.FrameworkElement> qualsiasi <xref:System.Windows.FrameworkContentElement> elemento <xref:System.Windows.Window> che <xref:System.Windows.Controls.Button>deriva da o, ad esempio a o a .

Il modo più comune per dichiarare uno `Resources` stile è come risorsa nella sezione in un file XAML. Poiché gli stili sono risorse, rispettano le stesse regole di ambito che si applicano a tutte le risorse. In parole povere, dove si dichiara uno stile influisce sul punto in cui lo stile può essere applicato. Ad esempio, se dichiari lo stile nell'elemento radice del file XAML di definizione dell'app, lo stile può essere usato in qualsiasi punto dell'app.

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/App.xaml#AppResources)]

Se dichiari lo stile in uno dei file XAML dell'app, lo stile può essere usato solo in tale file XAML. Per altre informazioni sulle regole di ambito delle risorse, vedere [Risorse XAML](xaml-resources-define.md).

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowSingleResource.xaml#WindowResources)]

Uno stile è `<Setter>` costituito da elementi figlio che impostano le proprietà degli elementi a cui viene applicato lo stile. Nell'esempio precedente, si noti che `TextBlock` lo stile `TargetType` è impostato per applicare ai tipi tramite l'attributo. Lo stile <xref:System.Windows.Controls.Control.FontSize%2A> imposterà `15` il <xref:System.Windows.Controls.Control.FontWeight%2A> `ExtraBold`su e il su . Aggiungere `<Setter>` un per ogni proprietà cambia lo stile.

## <a name="apply-a-style-implicitly"></a>Applicare uno stile in modo implicito

A <xref:System.Windows.Style> è un modo pratico per applicare un set di valori di proprietà a più di un elemento. Si considerino, <xref:System.Windows.Controls.TextBlock> ad esempio, gli elementi seguenti e il relativo aspetto predefinito in una finestra.

[!code-xaml[TextBlocks](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetTextBlocks)]

![Schermata di esempio di stile](./media/styles-and-templates-overview/stylingintro-textblocksbefore.png "StylingIntro_TextBlocksBefore")

È possibile modificare l'aspetto predefinito <xref:System.Windows.Controls.Control.FontSize%2A> impostando <xref:System.Windows.Controls.Control.FontFamily%2A>direttamente <xref:System.Windows.Controls.TextBlock> le proprietà, ad esempio e , su ogni elemento. Tuttavia, se <xref:System.Windows.Controls.TextBlock> vuoi che gli elementi condividano alcune proprietà, puoi creare un <xref:System.Windows.Style> nella `Resources` sezione del file XAML, come illustrato di seguito.

[!code-xaml[DefaultTextBlockStyle](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetDefaultTextBlockStyle)]

Quando si <xref:System.Windows.Style.TargetType%2A> imposta lo stile <xref:System.Windows.Controls.TextBlock> sul tipo e `x:Key` si omettono l'attributo, lo stile viene applicato a tutti gli <xref:System.Windows.Controls.TextBlock> elementi con ambito per lo stile, che in genere è il file XAML stesso.

Ora <xref:System.Windows.Controls.TextBlock> gli elementi appaiono come segue.

![Schermata di esempio di stile](./media/styles-and-templates-overview/stylingintro-textblocksbasestyle.png "StylingIntro_TextBlocksBaseStyle")

## <a name="apply-a-style-explicitly"></a>Applicare uno stile in modo esplicito

Se si `x:Key` aggiunge un attributo con valore allo stile, lo stile <xref:System.Windows.Style.TargetType%2A>non viene più applicato in modo implicito a tutti gli elementi di . Solo gli elementi che fanno riferimento in modo esplicito allo stile avranno lo stile applicato.

Ecco lo stile della sezione precedente, `x:Key` ma dichiarato con l'attributo .

[!code-xaml[ExplicitStyleDeclare](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleDeclare)]

Per applicare lo stile, impostate <xref:System.Windows.FrameworkElement.Style%2A> la `x:Key` proprietà sull'elemento sul valore, utilizzando un'estensione di [markup StaticResource](../../framework/wpf/advanced/staticresource-markup-extension.md), come illustrato di seguito.

[!code-xaml[ExplicitStyleReference](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleReference)]

Si noti <xref:System.Windows.Controls.TextBlock> che al primo elemento è applicato lo stile mentre il secondo elemento TextBlock rimane invariato. Lo stile implicito della sezione precedente è `x:Key` stato modificato in uno stile che dichiarava l'attributo, ovvero l'unico elemento interessato dallo stile è quello che faceva riferimento direttamente allo stile.

![Schermata di esempio di stile](./media/styles-and-templates-overview/create-a-style-explicit-textblock.png "create-a-style-explicit-textblock")

Una volta applicato uno stile, in modo esplicito o implicito, questo diventa sealed e non può essere modificato. Se si desidera modificare uno stile che è stato applicato, creare un nuovo stile per sostituire quello esistente. Per altre informazioni, vedere la proprietà <xref:System.Windows.Style.IsSealed%2A>.

È possibile creare un oggetto che sceglie uno stile da applicare in base alla logica personalizzata. Per un esempio, vedere l'esempio fornito per la <xref:System.Windows.Controls.StyleSelector> classe.

## <a name="apply-a-style-programmatically"></a>Applicare uno stile a livello di codiceApply a style programmatically

Per assegnare uno stile denominato a un elemento a livello di codice, <xref:System.Windows.FrameworkElement.Style%2A> ottenere lo stile dalla raccolta di risorse e assegnarlo alla proprietà dell'elemento. Gli elementi in un insieme <xref:System.Object>di risorse sono di tipo . Pertanto, è necessario eseguire <xref:System.Windows.Style?displayProperty=fullName> il cast dello `Style` stile recuperato a un prima di assegnarlo alla proprietà. Ad esempio, il codice seguente `TextBlock` imposta `textblock1` lo stile `TitleText`di un nome sullo stile definito.

[!code-csharp[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml.cs#SnippetSetStyleCode)]
[!code-vb[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/MainWindow.xaml.vb#SnippetSetStyleCode)]

## <a name="extend-a-style"></a>Estendere uno stile

È possibile che <xref:System.Windows.Controls.TextBlock> si desideri che i due <xref:System.Windows.Controls.Control.FontFamily%2A> elementi condividano alcuni valori di proprietà, ad esempio il e il centro . <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Ma si desidera anche il testo **Immagini** per avere alcune proprietà aggiuntive. È possibile farlo creando un nuovo stile basato sul primo stile, come mostrato qui.

[!code-xaml[DefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

[!code-xaml[TextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

Questo `TextBlock` stile è ora centrato, utilizza `Comic Sans MS` `26`un tipo di carattere <xref:System.Windows.Media.LinearGradientBrush> con una dimensione di , e il colore di primo piano impostato sul mostrato nell'esempio. Si noti che <xref:System.Windows.Controls.Control.FontSize%2A> esegue l'override del valore dello stile di base. Se è presente più <xref:System.Windows.Setter> di un che punta <xref:System.Windows.Style>alla `Setter` stessa proprietà in un , l'oggetto dichiarato per ultimo ha la precedenza.

Di seguito viene <xref:System.Windows.Controls.TextBlock> illustrato l'aspetto degli elementi:

![TextBlock con stile](./media/styles-and-templates-overview/stylingintro-textblocks.png "StylingIntro_TextBlocks")

Questo `TitleText` stile estende lo stile creato <xref:System.Windows.Controls.TextBlock> per il `BasedOn="{StaticResource {x:Type TextBlock}}"`tipo, a cui si fa riferimento con . È inoltre possibile estendere uno `x:Key` stile `x:Key` che dispone di un utilizzando lo stile. Ad esempio, se si `Header1` è presente uno stile denominato e `BasedOn="{StaticResource Header1}"`si desidera estendere tale stile, è necessario utilizzare .

## <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>Relazione tra la proprietà TargetType e l'attributo x:Key

Come illustrato in <xref:System.Windows.Style.TargetType%2A> precedenza, impostando la proprietà su `TextBlock` senza assegnare lo stile, `x:Key` lo stile viene applicato a tutti gli <xref:System.Windows.Controls.TextBlock> elementi. In questo caso, l'attributo `x:Key` è impostato in modo implicito su `{x:Type TextBlock}`. Ciò significa che se `x:Key` si imposta `{x:Type TextBlock}`in <xref:System.Windows.Style> modo esplicito il `TextBlock` valore su un valore diverso da , l'oggetto non viene applicato automaticamente a tutti gli elementi. Al contrario, è necessario applicare `x:Key` lo stile `TextBlock` (utilizzando il valore) agli elementi in modo esplicito. Se lo stile si trova nella sezione delle `TargetType` risorse e non si imposta `x:Key` la proprietà sullo stile, è necessario impostare l'attributo.

Oltre a fornire un valore `x:Key`predefinito `TargetType` per l'oggetto , la proprietà specifica il tipo a cui si applicano le proprietà setter. Se non si specifica `TargetType`un , è necessario <xref:System.Windows.Setter> qualificare le proprietà negli `Property="ClassName.Property"`oggetti con un nome di classe utilizzando la sintassi . Ad esempio, anziché `Property="FontSize"`impostare <xref:System.Windows.Setter.Property%2A> `"TextBlock.FontSize"` , `"Control.FontSize"`è necessario impostare su o .

Si noti inoltre che molti controlli WPFWPF sono costituiti da una combinazione di altri controlli WPFWPF. Se si crea uno stile che si applica a tutti i controlli di un tipo, è possibile che si ottengano risultati imprevisti. Ad esempio, se si crea <xref:System.Windows.Controls.TextBlock> uno stile <xref:System.Windows.Window>destinato al tipo `TextBlock` in un oggetto , `TextBlock` lo stile viene applicato a <xref:System.Windows.Controls.ListBox>tutti i controlli della finestra, anche se l'oggetto fa parte di un altro controllo, ad esempio un oggetto .

## <a name="see-also"></a>Vedere anche

<!-- - [Create a style for a control](styles-templates-create-apply-template.md) -->
- [Panoramica delle risorse XAMLOverview of XAML Resources](xaml-resources-define.md)
- [XAML overview (WPF & .NET Core)](xaml.md)
