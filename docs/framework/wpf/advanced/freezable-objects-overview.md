---
title: Cenni preliminari sugli oggetti Freezable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], description
- unfreezing Freezable objects [WPF]
- classes [WPF], Freezable
ms.assetid: 89c71692-4f43-4057-b611-67c6a8a863a2
ms.openlocfilehash: b1887afd19407898d8de1d92252e29778899fb89
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095190"
---
# <a name="freezable-objects-overview"></a>Cenni preliminari sugli oggetti Freezable

In questo argomento viene descritto come utilizzare e creare in modo efficace oggetti <xref:System.Windows.Freezable>, che forniscono funzionalità speciali che consentono di migliorare le prestazioni dell'applicazione. Esempi di oggetti Freezable includono pennelli, penne, trasformazioni, geometrie e animazioni.

<a name="whatisafreezable"></a>

## <a name="what-is-a-freezable"></a>Che cos'è un oggetto Freezable?

Un <xref:System.Windows.Freezable> è un tipo speciale di oggetto con due stati: non bloccato e bloccato. Quando viene sbloccato, un <xref:System.Windows.Freezable> sembra comportarsi come qualsiasi altro oggetto. Quando il blocco è bloccato, non è più possibile modificare un <xref:System.Windows.Freezable>.

Un <xref:System.Windows.Freezable> fornisce un evento <xref:System.Windows.Freezable.Changed> per notificare agli osservatori le eventuali modifiche apportate all'oggetto. Il blocco di un <xref:System.Windows.Freezable> può migliorare le prestazioni, perché non è più necessario spendere risorse per le notifiche di modifica. Un <xref:System.Windows.Freezable> bloccato può anche essere condiviso tra thread, mentre un <xref:System.Windows.Freezable> non bloccato non può.

Anche se la classe <xref:System.Windows.Freezable> dispone di molte applicazioni, la maggior parte degli oggetti <xref:System.Windows.Freezable> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sono correlati al sottosistema grafico.

La classe <xref:System.Windows.Freezable> rende più semplice l'utilizzo di determinati oggetti di sistema grafici e consente di migliorare le prestazioni dell'applicazione. Esempi di tipi che ereditano da <xref:System.Windows.Freezable> includono le classi <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>e <xref:System.Windows.Media.Geometry>. Poiché contengono risorse non gestite, il sistema deve monitorare tali oggetti per le modifiche e quindi aggiornare le corrispondenti risorse non gestite quando viene apportata una modifica all'oggetto originale. Anche se non si modifica effettivamente un oggetto di sistema grafico, il sistema deve comunque dedicare alcune risorse al monitoraggio dell'oggetto, nel caso in cui venga modificato.

Si supponga, ad esempio, di creare un pennello <xref:System.Windows.Media.SolidColorBrush> e di usarlo per disegnare lo sfondo di un pulsante.

[!code-csharp[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
[!code-vb[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]

Quando viene eseguito il rendering del pulsante, il sottosistema grafico [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa le informazioni fornite per disegnare un gruppo di pixel per creare l'aspetto di un pulsante. Sebbene sia stato usato un pennello tinta unita per descrivere il modo in cui deve essere disegnato il pulsante, il pennello tinta unita non esegue effettivamente il disegno. Il sistema grafico genera oggetti veloci e di basso livello per il pulsante e il pennello e sono gli oggetti effettivamente visualizzati sullo schermo.

Per modificare il pennello, è necessario rigenerare tali oggetti di basso livello. La classe Freezable fornisce a un pennello la possibilità di trovare gli oggetti di basso livello generati corrispondenti e di aggiornarli quando cambiano. Quando questa funzionalità è abilitata, il pennello viene definito "non bloccato".

Il metodo <xref:System.Windows.Freezable.Freeze%2A> di un oggetto Freezable consente di disabilitare questa funzionalità di aggiornamento automatico. È possibile utilizzare questo metodo per fare in modo che il pennello diventi "bloccato" o non modificabile.

> [!NOTE]
> Non tutti gli oggetti Freezable possono essere bloccati. Per evitare di generare un <xref:System.InvalidOperationException>, controllare il valore della proprietà <xref:System.Windows.Freezable.CanFreeze%2A> dell'oggetto Freezable per determinare se può essere bloccato prima di tentare di bloccarlo.

[!code-csharp[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
[!code-vb[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]

Quando non è più necessario modificare un oggetto Freezable, il blocco offre vantaggi in merito alle prestazioni. Se si blocca il pennello in questo esempio, il sistema grafico non dovrà più monitorarlo per le modifiche. Il sistema grafico può anche eseguire altre ottimizzazioni, perché sa che il pennello non cambierà.

> [!NOTE]
> Per praticità, gli oggetti Freezable rimangono bloccati a meno che non vengano bloccati in modo esplicito.

<a name="frozenfreezables"></a>

## <a name="using-freezables"></a>Uso di Freezable

L'utilizzo di un oggetto Freezable sbloccato è analogo all'utilizzo di qualsiasi altro tipo di oggetto. Nell'esempio seguente, il colore di un <xref:System.Windows.Media.SolidColorBrush> viene modificato da giallo a rosso dopo che è stato usato per disegnare lo sfondo di un pulsante. Il sistema grafico funziona dietro le quinte per modificare automaticamente il pulsante da giallo a rosso alla successiva aggiornamento dello schermo.

[!code-csharp[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
[!code-vb[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]

### <a name="freezing-a-freezable"></a>Blocco di un oggetto Freezable

Per rendere immodificabile un <xref:System.Windows.Freezable>, chiamare il relativo metodo <xref:System.Windows.Freezable.Freeze%2A>. Quando si blocca un oggetto che contiene oggetti Freezable, anche questi oggetti sono bloccati. Se, ad esempio, si blocca un <xref:System.Windows.Media.PathGeometry>, anche le figure e i segmenti in esso contenuti verrebbero bloccati.

Un oggetto Freezable **non può** essere bloccato se si verifica una delle condizioni seguenti:

- Dispone di proprietà animate o con associazione a dati.

- Dispone di proprietà impostate da una risorsa dinamica. Per ulteriori informazioni sulle risorse dinamiche, vedere le [risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md) .

- Contiene <xref:System.Windows.Freezable> oggetti secondari che non possono essere bloccati.

Se queste condizioni sono false e non si intende modificare il <xref:System.Windows.Freezable>, è consigliabile bloccarlo per ottenere i vantaggi in termini di prestazioni descritti in precedenza.

Una volta chiamato il metodo <xref:System.Windows.Freezable.Freeze%2A> di un oggetto Freezable, non è più possibile modificarlo. Il tentativo di modificare un oggetto bloccato causa la generazione di un <xref:System.InvalidOperationException>. Il codice seguente genera un'eccezione, perché si tenta di modificare il pennello dopo che è stato bloccato.

[!code-csharp[freezablesample_procedural#ExceptionExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
[!code-vb[freezablesample_procedural#ExceptionExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]

Per evitare di generare questa eccezione, è possibile usare il metodo <xref:System.Windows.Freezable.IsFrozen%2A> per determinare se un <xref:System.Windows.Freezable> è bloccato.

[!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
[!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]

Nell'esempio di codice precedente, è stata eseguita una copia modificabile di un oggetto bloccato usando il metodo <xref:System.Windows.Freezable.Clone%2A>. La sezione successiva illustra la clonazione in modo più dettagliato.

> [!NOTE]
> Poiché non è possibile animare un Freezable bloccato, il sistema di animazione creerà automaticamente cloni modificabili di oggetti <xref:System.Windows.Freezable> bloccati quando si tenta di animarli con una <xref:System.Windows.Media.Animation.Storyboard>. Per eliminare l'overhead delle prestazioni causato dalla clonazione, lasciare un oggetto non bloccato se si intende animarlo. Per ulteriori informazioni sull'animazione con gli storyboard, vedere [Cenni preliminari sugli storyboard](../graphics-multimedia/storyboards-overview.md).

### <a name="freezing-from-markup"></a>Blocco dal markup

Per bloccare un oggetto <xref:System.Windows.Freezable> dichiarato nel markup, usare l'attributo `PresentationOptions:Freeze`. Nell'esempio seguente una <xref:System.Windows.Media.SolidColorBrush> viene dichiarata come risorsa di pagina e bloccata. Viene quindi usato per impostare lo sfondo di un pulsante.

[!code-xaml[FreezableSample#FreezeFromMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]

Per utilizzare l'attributo `Freeze`, è necessario eseguire il mapping allo spazio dei nomi delle opzioni di presentazione: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`. `PresentationOptions` è il prefisso consigliato per il mapping di questo spazio dei nomi:

```xaml
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"
```

Poiché non tutti i lettori XAML riconoscono questo attributo, è consigliabile usare l' [attributo MC: Ignorable](mc-ignorable-attribute.md) per contrassegnare l'attributo `Presentation:Freeze` come ignorabile:

```xaml
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
mc:Ignorable="PresentationOptions"
```

Per ulteriori informazioni, vedere la pagina relativa all' [attributo MC: Ignorable](mc-ignorable-attribute.md) .

### <a name="unfreezing-a-freezable"></a>"Sblocco" di un oggetto Freezable

Una volta bloccato, un <xref:System.Windows.Freezable> non può mai essere modificato o sbloccato; Tuttavia, è possibile creare un clone non bloccato usando il metodo <xref:System.Windows.Freezable.Clone%2A> o <xref:System.Windows.Freezable.CloneCurrentValue%2A>.

Nell'esempio seguente lo sfondo del pulsante viene impostato con un pennello e il pennello viene quindi bloccato. Viene eseguita una copia non bloccata del pennello utilizzando il metodo <xref:System.Windows.Freezable.Clone%2A>. Il clone viene modificato e usato per modificare lo sfondo del pulsante da giallo a rosso.

[!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
[!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]

> [!NOTE]
> Indipendentemente dal metodo di clonazione usato, le animazioni non vengono mai copiate nella nuova <xref:System.Windows.Freezable>.

I metodi <xref:System.Windows.Freezable.Clone%2A> e <xref:System.Windows.Freezable.CloneCurrentValue%2A> producono copie complete dell'oggetto Freezable. Se l'oggetto Freezable contiene altri oggetti Freezable bloccati, questi vengono anche clonati e resi modificabili. Se, ad esempio, si clona un <xref:System.Windows.Media.PathGeometry> bloccato per renderlo modificabile, anche le figure e i segmenti in esso contenuti vengono copiati e resi modificabili.

<a name="createyourownfreezableclass"></a>

## <a name="creating-your-own-freezable-class"></a>Creazione di una classe Freezable personalizzata

Una classe che deriva da <xref:System.Windows.Freezable> acquisisce le funzionalità seguenti.

- Stati speciali: uno stato di sola lettura (bloccato) e scrivibile.

- Thread safety: un <xref:System.Windows.Freezable> bloccato può essere condiviso tra thread.

- Notifica dettagliata delle modifiche: diversamente da altre <xref:System.Windows.DependencyObject>s, gli oggetti Freezable forniscono notifiche di modifica quando i valori delle sottoproprietà cambiano.

- Clonazione semplice: la classe Freezable ha già implementato diversi metodi che producono cloni profondi.

Un <xref:System.Windows.Freezable> è un tipo di <xref:System.Windows.DependencyObject>e pertanto utilizza il sistema di proprietà di dipendenza. Le proprietà della classe non devono essere proprietà di dipendenza, ma l'uso delle proprietà di dipendenza ridurrà la quantità di codice da scrivere, perché la classe <xref:System.Windows.Freezable> è stata progettata con le proprietà di dipendenza. Per ulteriori informazioni sul sistema di proprietà di dipendenza, vedere [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md).

Ogni sottoclasse <xref:System.Windows.Freezable> deve eseguire l'override del metodo <xref:System.Windows.Freezable.CreateInstanceCore%2A>. Se la classe USA proprietà di dipendenza per tutti i dati, l'operazione è terminata.

Se la classe contiene membri dati di proprietà non di dipendenza, è necessario anche eseguire l'override dei metodi seguenti:

- <xref:System.Windows.Freezable.CloneCore%2A>

- <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>

- <xref:System.Windows.Freezable.GetAsFrozenCore%2A>

- <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>

- <xref:System.Windows.Freezable.FreezeCore%2A>

È inoltre necessario osservare le regole seguenti per l'accesso e la scrittura a membri dati che non sono proprietà di dipendenza:

- All'inizio di qualsiasi API che legge i membri dati della proprietà non di dipendenza, chiamare il metodo <xref:System.Windows.Freezable.ReadPreamble%2A>.

- All'inizio di qualsiasi API che scriva membri dati di proprietà non di dipendenza, chiamare il metodo <xref:System.Windows.Freezable.WritePreamble%2A>. Dopo aver chiamato <xref:System.Windows.Freezable.WritePreamble%2A> in un'API, non è necessario effettuare una chiamata aggiuntiva a <xref:System.Windows.Freezable.ReadPreamble%2A> se si leggono anche i membri dati della proprietà non di dipendenza.

- Chiamare il metodo <xref:System.Windows.Freezable.WritePostscript%2A> prima di uscire da metodi che scrivono in membri dati di proprietà non di dipendenza.

Se la classe contiene membri dati di proprietà non dipendenza <xref:System.Windows.DependencyObject> oggetti, è necessario chiamare anche il metodo <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> ogni volta che si modifica uno dei relativi valori, anche se si imposta il membro su `null`.

> [!NOTE]
> È molto importante iniziare ogni <xref:System.Windows.Freezable> metodo di cui si esegue l'override con una chiamata all'implementazione di base.

Per un esempio di classe di <xref:System.Windows.Freezable> personalizzata, vedere l' [esempio di animazione personalizzata](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Freezable>
- [Esempio di animazione personalizzata](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)
- [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
