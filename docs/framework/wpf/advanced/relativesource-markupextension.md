---
title: Estensione del markup RelativeSource
description: Specifica le proprietà di un'origine di associazione RelativeSource, all'interno di un'estensione di markup dell'associazione o quando si imposta la proprietà RelativeSource di un'associazione in XAML.
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: 2da702d23413651a85b45404e088f6708546cc25
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165934"
---
# <a name="relativesource-markupextension"></a>Estensione del markup RelativeSource

Specifica le proprietà di un' <xref:System.Windows.Data.RelativeSource> origine di associazione, da usare all'interno di un' [estensione di markup di associazione](binding-markup-extension.md)o quando si imposta la <xref:System.Windows.Data.Binding.RelativeSource%2A> proprietà di un <xref:System.Windows.Data.Binding> elemento definito in XAML.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xml
<Binding RelativeSource="{RelativeSource modeEnumValue}" ... />
```

## <a name="xaml-attribute-usage-nested-within-binding-extension"></a>Utilizzo della sintassi XAML per gli attributi (annidati nell'estensione Binding)

```xml
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" ... />
```

## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource Mode="modeEnumValue"/>
  </Binding.RelativeSource>
</Binding>
```

-oppure-

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource
      Mode="FindAncestor"
      AncestorType="{x:Type typeName}"
      AncestorLevel="intLevel"
    />
  </Binding.RelativeSource>
</Binding>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`modeEnumValue`|I tipi validi sono:<br /><br /> : Token di stringa `Self` ; corrisponde a un oggetto <xref:System.Windows.Data.RelativeSource> creato con la <xref:System.Windows.Data.RelativeSource.Mode%2A> proprietà impostata su <xref:System.Windows.Data.RelativeSourceMode.Self> .<br />: Token di stringa `TemplatedParent` ; corrisponde a un oggetto <xref:System.Windows.Data.RelativeSource> creato con la <xref:System.Windows.Data.RelativeSource.Mode%2A> proprietà impostata su <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent> .<br />: Token di stringa `PreviousData` ; corrisponde a un oggetto <xref:System.Windows.Data.RelativeSource> creato con la <xref:System.Windows.Data.RelativeSource.Mode%2A> proprietà impostata su <xref:System.Windows.Data.RelativeSourceMode.PreviousData> .<br />Per informazioni sulla modalità, vedere di seguito `FindAncestor` .|
|`FindAncestor`|Token stringa `FindAncestor`. L'utilizzo di questo token consente di accedere a una modalità in cui `RelativeSource` specifica un tipo predecessore e facoltativamente un livello predecessore. Corrisponde a un oggetto <xref:System.Windows.Data.RelativeSource> creato con la proprietà <xref:System.Windows.Data.RelativeSource.Mode%2A> impostata su <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.|
|`typeName`|Obbligatorio per la modalità `FindAncestor`. Nome di un tipo che riempie la proprietà <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.|
|`intLevel`|Facoltativo per la modalità `FindAncestor`. Livello predecessore (valutato nella direzione padre dell'albero logico).|

## <a name="remarks"></a>Osservazioni

`{RelativeSource TemplatedParent}`gli utilizzi di binding sono una tecnica essenziale che risolve un concetto più ampio della separazione tra l'interfaccia utente di un controllo e la logica di un controllo. Ciò consente l'associazione dall'interno della definizione del modello al padre basato su modelli (istanza dell'oggetto in fase di esecuzione alla quale è applicato il modello). Per questo caso, l' [estensione di markup TemplateBinding](templatebinding-markup-extension.md) è in realtà una sintassi abbreviata per la seguente espressione di associazione: `{Binding RelativeSource={RelativeSource TemplatedParent}}` . `TemplateBinding``{RelativeSource TemplatedParent}`gli utilizzi o sono entrambi rilevanti solo all'interno del codice XAML che definisce un modello. Per ulteriori informazioni, vedere [TemplateBinding Markup Extension](templatebinding-markup-extension.md).

`{RelativeSource FindAncestor}`viene usato principalmente nei modelli di controllo o nelle composizioni dell'interfaccia utente autonomia prevedibile, per i casi in cui un controllo deve essere sempre incluso in una struttura ad albero visuale di un determinato tipo di predecessore. Ad esempio, gli elementi di un controllo di elementi potrebbero utilizzare `FindAncestor` per associarsi alle proprietà del relativo predecessore padre del controllo di elementi. In alternativa, gli elementi che fanno parte della composizione del controllo in un modello possono utilizzare le associazioni `FindAncestor` agli elementi padre nella stessa struttura della composizione.

Nella sintassi dell'elemento oggetto per la modalità `FindAncestor` illustrata nelle sezioni sulla sintassi XAML, la sintassi del secondo elemento oggetto viene utilizzata specificamente per la modalità `FindAncestor`. La modalità `FindAncestor` richiede un valore <xref:System.Windows.Data.RelativeSource.AncestorType%2A>. È necessario impostare <xref:System.Windows.Data.RelativeSource.AncestorType%2A> come attributo utilizzando un riferimento all' [estensione di markup x:Type](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) al tipo di predecessore da cercare. Il valore <xref:System.Windows.Data.RelativeSource.AncestorType%2A> viene utilizzato quando la richiesta di associazione viene elaborata in fase di esecuzione.

Per la modalità `FindAncestor`, la proprietà facoltativa <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> consente di rendere meno ambigua la ricerca del predecessore laddove vi sono più predecessori di questo tipo nella struttura ad albero dell'elemento.

Per ulteriori informazioni su come utilizzare la modalità `FindAncestor`, vedere <xref:System.Windows.Data.RelativeSource>.

`{RelativeSource Self}`è utile per gli scenari in cui una proprietà di un'istanza deve dipendere dal valore di un'altra proprietà della stessa istanza e non esiste già una relazione di proprietà di dipendenza generale, ad esempio la coercizione, tra queste due proprietà. Sebbene sia raro che esistano due proprietà su un oggetto in modo che i valori siano letteralmente identici (e siano tipizzati in modo identico), è anche possibile applicare un `Converter` parametro a un'associazione che dispone di `{RelativeSource Self}` e usare il convertitore per eseguire la conversione tra i tipi di origine e di destinazione. Un altro scenario per `{RelativeSource Self}` è come parte di un oggetto <xref:System.Windows.MultiDataTrigger> .

Ad esempio, nel codice XAML seguente viene definito un elemento <xref:System.Windows.Shapes.Rectangle> in modo che, indipendentemente dal valore inserito per <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.Shapes.Rectangle> sia sempre un quadrato: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`

`{RelativeSource PreviousData}`è utile nei modelli di dati oppure nei casi in cui le associazioni utilizzano una raccolta come origine dati. È possibile utilizzare `{RelativeSource PreviousData}` per evidenziare le relazioni tra gli elementi di dati adiacenti nella raccolta. Una tecnica correlata consiste nel porre un oggetto <xref:System.Windows.Data.MultiBinding> tra l'elemento corrente e quello precedente nell'origine dati e utilizzare un convertitore su quell'associazione per determinare la differenza tra i due elementi e le relative proprietà.

Nell'esempio riportato di seguito, il primo <xref:System.Windows.Controls.TextBlock> in un modello di elementi visualizza il numero corrente. Il secondo <xref:System.Windows.Controls.TextBlock> binding è un oggetto <xref:System.Windows.Data.MultiBinding> che ha nominalmente due <xref:System.Windows.Data.Binding> costituenti: il record corrente e un'associazione che utilizza intenzionalmente il record di dati precedente tramite `{RelativeSource PreviousData}` . Quindi, un convertitore applicato a <xref:System.Windows.Data.MultiBinding> calcola la differenza e la restituisce all'associazione.

```xml
<ListBox Name="fibolist">
    <ListBox.ItemTemplate>
        <DataTemplate>
            <StackPanel Orientation="Horizontal">
            <TextBlock Text="{Binding}"/>
            <TextBlock>, difference = </TextBlock>
                <TextBlock>
                    <TextBlock.Text>
                        <MultiBinding Converter="{StaticResource DiffConverter}">
                            <Binding/>
                            <Binding RelativeSource="{RelativeSource PreviousData}"/>
                        </MultiBinding>
                    </TextBlock.Text>
                </TextBlock>
            </StackPanel>
        </DataTemplate>
    </ListBox.ItemTemplate>
</ListBox>
```

La descrizione di data binding come concetto non è illustrata in questo articolo, vedere [Cenni preliminari sul data binding](../../../desktop-wpf/data/data-binding-overview.md).

Nell' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementazione del processore XAML, la gestione di questa estensione di markup viene definita dalla <xref:System.Windows.Data.RelativeSource> classe.

`RelativeSource` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in XAML usano i `{` `}` caratteri e nella relativa sintassi di attributo, ovvero la convenzione con cui un processore XAML riconosce che un'estensione di markup deve elaborare l'attributo. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.Binding>
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Cenni preliminari sulle dichiarazioni di associazione](../data/binding-declarations-overview.md)
- [Estensione del markup x:Type](../../../desktop-wpf/xaml-services/xtype-markup-extension.md)
