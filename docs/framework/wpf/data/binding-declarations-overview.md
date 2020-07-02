---
title: Cenni preliminari sulle dichiarazioni di associazione
description: Informazioni su come dichiarare un'associazione in XAML per lo sviluppo di applicazioni in Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- markup extensions [WPF]
- data binding [WPF], declarations
- object element syntax [WPF]
- binding data [WPF], declarations
- syntax [WPF], object elements
- binding declarations [WPF]
ms.assetid: b97fd626-4c0d-4761-872a-2bca5820da2c
ms.openlocfilehash: 8d4943de0cacb5fe0b5a0c37a5a68f15243ad528
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619637"
---
# <a name="binding-declarations-overview"></a>Cenni preliminari sulle dichiarazioni di associazione

In questo argomento vengono illustrati i diversi modi in cui è possibile dichiarare un'associazione.

<a name="Prereq"></a>

## <a name="prerequisites"></a>Prerequisiti

Prima di leggere questo argomento, è importante avere familiarità con i concetti e l'utilizzo delle estensioni di markup. Per altre informazioni sulle estensioni di markup, vedere [Estensioni di markup e WPF XAML](../advanced/markup-extensions-and-wpf-xaml.md).

In questo argomento non vengono illustrati i concetti relativi all'associazione dati. Per informazioni sui concetti relativi all'associazione dati, vedere [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md).

<a name="BindinginXAML"></a>

## <a name="declaring-a-binding-in-xaml"></a>Dichiarazione di un'associazione in XAML

Questa sezione illustrato come dichiarare un'associazione in XAML.

<a name="MarkupExtensionSyntax"></a>

### <a name="markup-extension-usage"></a>Uso delle estensioni di markup

<xref:System.Windows.Data.Binding> è un'estensione di markup. Quando si usa l'estensione dell'associazione per dichiarare un'associazione, la dichiarazione è costituita da una serie di clausole che seguono la parola chiave `Binding` separate da virgole (,). Le clausole nella dichiarazione di associazione possono essere in qualsiasi ordine con molte possibili combinazioni. Le clausole sono coppie *nome*- = *valore* in cui *nome* è il nome della <xref:System.Windows.Data.Binding> proprietà *Value* e il valore è il valore impostato per la proprietà.

Durante la creazione di stringhe di dichiarazione di associazione nel markup, queste devono essere associate alla proprietà di dipendenza specifica di un oggetto di destinazione. Nell'esempio seguente viene illustrato come associare la <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> proprietà utilizzando l'estensione di binding, specificando le <xref:System.Windows.Data.Binding.Source%2A> <xref:System.Windows.Data.Binding.Path%2A> proprietà e.

[!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#L37-L37)]

In questo modo è possibile specificare la maggior parte delle proprietà della <xref:System.Windows.Data.Binding> classe. Per ulteriori informazioni sull'estensione di binding e per un elenco di <xref:System.Windows.Data.Binding> proprietà che non possono essere impostate utilizzando l'estensione di binding, vedere Cenni preliminari sull' [estensione di markup di binding](../advanced/binding-markup-extension.md) .

<a name="ObjectElementSyntax"></a>

### <a name="object-element-syntax"></a>Sintassi degli elementi oggetto

La sintassi degli elementi oggetto è un'alternativa alla creazione della dichiarazione di associazione. Nella maggior parte dei casi, non esiste alcun vantaggio specifico per l'uso dell'estensione di markup rispetto alla sintassi dell'elemento oggetto. Tuttavia, nei casi in cui l'estensione di markup non supporta uno scenario, ad esempio quando il valore della proprietà è di un tipo non stringa per il quale non esistono conversioni di tipo, sarà necessario usare la sintassi degli elementi oggetto.

Di seguito viene riportato un esempio dell'uso sia della sintassi per elementi oggetto, sia dell'estensione di markup:

[!code-xaml[BindConversionMarkup#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindConversionMarkup/CSharp/Page1.xaml#1)]

Nell'esempio viene associata la <xref:System.Windows.Controls.TextBlock.Foreground%2A> Proprietà dichiarando un'associazione usando la sintassi dell'estensione. La dichiarazione di associazione per la <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà utilizza la sintassi dell'elemento oggetto.

Per altre informazioni sui diversi termini, vedere [Descrizione dettagliata della sintassi XAML](../advanced/xaml-syntax-in-detail.md).

<a name="MBandPB"></a>

### <a name="multibinding-and-prioritybinding"></a>MultiBinding e PriorityBinding

<xref:System.Windows.Data.MultiBinding>e non <xref:System.Windows.Data.PriorityBinding> supportano la sintassi dell'estensione XAML. Pertanto, è necessario utilizzare la sintassi dell'elemento oggetto se si dichiara <xref:System.Windows.Data.MultiBinding> o <xref:System.Windows.Data.PriorityBinding> in XAML.

<a name="BindinginCode"></a>

## <a name="creating-a-binding-in-code"></a>Creazione di un'associazione nel codice

Un altro modo per specificare un'associazione consiste nell'impostare le proprietà direttamente su un <xref:System.Windows.Data.Binding> oggetto nel codice. Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Data.Binding> oggetto e specificare le proprietà nel codice.  In questo esempio, `TheConverter` è un oggetto che implementa l' <xref:System.Windows.Data.IValueConverter> interfaccia.

[!code-csharp[BindConversion#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindConversion/CSharp/Window1.xaml.cs#1)]
[!code-vb[BindConversion#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindConversion/visualbasic/window1.xaml.vb#1)]

Se l'oggetto da associare è <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> , è possibile chiamare `SetBinding` direttamente il metodo sull'oggetto invece di usare <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> . Per un esempio, vedere [Creare associazioni nel codice](how-to-create-a-binding-in-code.md).

<a name="Path_Syntax"></a>

## <a name="binding-path-syntax"></a>Sintassi del percorso di associazione

Utilizzare la <xref:System.Windows.Data.Binding.Path%2A> proprietà per specificare il valore di origine a cui si desidera eseguire il binding:

- Nel caso più semplice, il <xref:System.Windows.Data.Binding.Path%2A> valore della proprietà è il nome della proprietà dell'oggetto di origine da usare per l'associazione, ad esempio `Path=PropertyName` .

- Le sottoproprietà di una proprietà possono essere specificate con una sintassi simile a quella di C#. Ad esempio, la clausola `Path=ShoppingCart.Order` imposta l'associazione sulla sottoproprietà `Order` dell'oggetto o la proprietà `ShoppingCart`.

- Per eseguire l'associazione a una proprietà associata, racchiuderla tra parentesi. Ad esempio, per eseguire l'associazione alla proprietà associata <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> , la sintassi è `Path=(DockPanel.Dock)` .

- Gli indicizzatori di una proprietà possono essere specificati all'interno di parentesi quadre dopo il nome della proprietà in cui viene applicato l'indicizzatore. La clausola `Path=ShoppingCart[0]` ad esempio imposta l'associazione all'indice corrispondente al modo in cui l'indicizzazione interna della proprietà gestisce la stringa letterale "0". Sono supportati anche indicizzatori annidati.

- Indicizzatori e sottoproprietà possono essere combinati in una clausola `Path`, ad esempio,`Path=ShoppingCart.ShippingInfo[MailingAddress,Street].`

- All'interno degli indicizzatori è possibile specificare più parametri di indicizzatore separati da virgole (,). È possibile specificare tra parentesi il tipo di ogni parametro. È possibile ad esempio avere `Path="[(sys:Int32)42,(sys:Int32)24]"`, dove è stato eseguito il mapping di `sys` allo spazio dei nomi `System`.

- Quando l'origine è una visualizzazione di raccolta, è possibile specificare l'elemento corrente con una barra (/). La clausola `Path=/` ad esempio imposta l'associazione all'elemento corrente nella visualizzazione. Quando l'origine è una raccolta, questa sintassi specifica l'elemento corrente della visualizzazione di raccolta predefinita.

- Barre e nomi di proprietà possono essere combinate per attraversare le proprietà che sono raccolte. `Path=/Offices/ManagerName` ad esempio specifica l'elemento corrente della raccolta di origine, che contiene una proprietà `Offices` che è anche una raccolta. L'elemento corrente è un oggetto che contiene una proprietà `ManagerName`.

- È possibile usare facoltativamente un percorso con il punto (.) per eseguire l'associazione all'origine corrente. Ad esempio, `Text="{Binding}"` equivale a `Text="{Binding Path=.}"`.

### <a name="escaping-mechanism"></a>Meccanismo di escape

- All'interno degli indicizzatori ([]), l’accento circonflesso (^) funge da escape per il carattere successivo.

- Se si imposta <xref:System.Windows.Data.Binding.Path%2A> in XAML, è necessario anche usare caratteri di escape (con entità XML) per determinati caratteri speciali per la definizione del linguaggio XML:

  - Usare `&amp;` come carattere di escape per "&".

  - Usare `&gt;` come carattere di escape per il tag di fine ">".

- Se si descrive inoltre l'intera associazione di un attributo usando la sintassi dell'estensione di markup, è necessario usare un carattere di escape (la barra rovesciata \\) per i caratteri speciali del parser dell'estensione di markup [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:

  - La barra rovesciata (\\) è il carattere di escape.

  - Il segno di uguale (=) separa il nome di proprietà dal valore della proprietà.

  - Le proprietà sono separate da virgole (,).

  - La parentesi graffa chiusa (}) è la fine di un'estensione di markup.

<a name="Default"></a>

## <a name="default-behaviors"></a>Comportamenti predefiniti

Il comportamento predefinito è come indicato di seguito se non viene specificato nella dichiarazione.

- Viene creato un convertitore predefinito che tenta di eseguire una conversione di tipo tra il valore dell'origine dell'associazione e il valore della destinazione dell'associazione. Se non è possibile eseguire una conversione, il convertitore predefinito restituisce `null`.

- Se non si imposta <xref:System.Windows.Data.Binding.ConverterCulture%2A> , il motore di binding utilizzerà la `Language` proprietà dell'oggetto di destinazione del binding. In XAML, questo valore viene impostato in modalità predefinita su "en-US" o eredita il valore dell'elemento radice (o qualsiasi elemento) della pagina, se ne è stato impostato uno in modo esplicito.

- Se l'associazione dispone già di un contesto dati (ad esempio, il contesto dati ereditato da un elemento padre) e indipendentemente da quale elemento, o raccolta, restituito da quel contesto sia adatto all'associazione senza richiedere altre modifiche del percorso, una dichiarazione di associazione può essere totalmente priva di clausole: `{Binding}` Si tratta della modalità con cui spesso si specifica un'associazione per l'applicazione di stili ai dati, se l'associazione agisce su una raccolta. Per altre informazioni, vedere la sezione "Utilizzo di oggetti interi come origine di associazione" in [Cenni preliminari sulle origini di associazione](binding-sources-overview.md).

- Il valore predefinito <xref:System.Windows.Data.Binding.Mode%2A> varia a seconda della proprietà di dipendenza associata, ovvero unidirezionale e bidirezionale. È sempre possibile dichiarare in modo esplicito la modalità di associazione per garantire che il comportamento sia quello desiderato. In generale, le proprietà del controllo modificabile dall'utente, ad esempio <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> e <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A?displayProperty=nameWithType> , per impostazione predefinita sono le associazioni bidirezionali, mentre la maggior parte delle altre proprietà viene impostata per impostazione predefinita sulle associazioni unidirezionali.

- Il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore predefinito varia tra <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> e <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> a seconda della proprietà di dipendenza associata. Il valore predefinito per la maggior parte delle proprietà di dipendenza è <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, mentre la proprietà <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> ha il valore predefinito <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.

## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedure](data-binding-how-to-topics.md)
- [Data binding](../advanced/optimizing-performance-data-binding.md)
- [Sintassi XAML di PropertyPath](../advanced/propertypath-xaml-syntax.md)
