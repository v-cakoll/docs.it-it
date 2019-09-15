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
ms.openlocfilehash: 05cd3c27430146f575c23011f53995aa07aaf99e
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991487"
---
# <a name="freezable-objects-overview"></a>Cenni preliminari sugli oggetti Freezable

In questo argomento viene descritto come utilizzare e creare <xref:System.Windows.Freezable> in modo efficace oggetti, che forniscono funzionalità speciali che consentono di migliorare le prestazioni dell'applicazione. Esempi di oggetti Freezable includono pennelli, penne, trasformazioni, geometrie e animazioni.

<a name="whatisafreezable"></a>

## <a name="what-is-a-freezable"></a>Che cos'è un oggetto Freezable?

Un <xref:System.Windows.Freezable> è un tipo speciale di oggetto con due stati: non bloccato e bloccato. Quando viene sbloccato, <xref:System.Windows.Freezable> un sembra comportarsi come qualsiasi altro oggetto. Quando è bloccato, <xref:System.Windows.Freezable> un oggetto non può più essere modificato.

Un <xref:System.Windows.Freezable> oggetto fornisce <xref:System.Windows.Freezable.Changed> un evento per notificare agli osservatori le eventuali modifiche apportate all'oggetto. Il blocco <xref:System.Windows.Freezable> di un può migliorare le prestazioni, perché non è più necessario spendere risorse per le notifiche di modifica. Un oggetto <xref:System.Windows.Freezable> bloccato può anche essere condiviso tra thread, mentre un oggetto <xref:System.Windows.Freezable> non bloccato non può.

Sebbene la <xref:System.Windows.Freezable> classe includa molte applicazioni, <xref:System.Windows.Freezable> la maggior [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] parte degli oggetti in sono correlati al sottosistema grafico.

La <xref:System.Windows.Freezable> classe semplifica l'utilizzo di determinati oggetti di sistema grafici e può contribuire a migliorare le prestazioni dell'applicazione. Esempi di tipi che ereditano <xref:System.Windows.Freezable> da includono <xref:System.Windows.Media.Brush>le <xref:System.Windows.Media.Transform>classi, <xref:System.Windows.Media.Geometry> e. Poiché contengono risorse non gestite, il sistema deve monitorare tali oggetti per le modifiche e quindi aggiornare le corrispondenti risorse non gestite quando viene apportata una modifica all'oggetto originale. Anche se non si modifica effettivamente un oggetto di sistema grafico, il sistema deve comunque dedicare alcune risorse al monitoraggio dell'oggetto, nel caso in cui venga modificato.

Si supponga, ad esempio, di <xref:System.Windows.Media.SolidColorBrush> creare un pennello e usarlo per disegnare lo sfondo di un pulsante.

[!code-csharp[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
[!code-vb[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]

Quando viene eseguito il rendering del pulsante [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , il sottosistema grafico usa le informazioni fornite per disegnare un gruppo di pixel per creare l'aspetto di un pulsante. Sebbene sia stato usato un pennello tinta unita per descrivere il modo in cui deve essere disegnato il pulsante, il pennello tinta unita non esegue effettivamente il disegno. Il sistema grafico genera oggetti veloci e di basso livello per il pulsante e il pennello e sono gli oggetti effettivamente visualizzati sullo schermo.

Per modificare il pennello, è necessario rigenerare tali oggetti di basso livello. La classe Freezable fornisce a un pennello la possibilità di trovare gli oggetti di basso livello generati corrispondenti e di aggiornarli quando cambiano. Quando questa funzionalità è abilitata, il pennello viene definito "non bloccato".

Il <xref:System.Windows.Freezable.Freeze%2A> metodo di un oggetto Freezable consente di disabilitare questa funzionalità di aggiornamento automatico. È possibile utilizzare questo metodo per fare in modo che il pennello diventi "bloccato" o non modificabile.

> [!NOTE]
> Non tutti gli oggetti Freezable possono essere bloccati. Per evitare di generare <xref:System.InvalidOperationException>un' <xref:System.Windows.Freezable.CanFreeze%2A> eccezione, controllare il valore della proprietà dell'oggetto Freezable per determinare se può essere bloccato prima di tentare di bloccarlo.

[!code-csharp[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
[!code-vb[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]

Quando non è più necessario modificare un oggetto Freezable, il blocco offre vantaggi in merito alle prestazioni. Se si blocca il pennello in questo esempio, il sistema grafico non dovrà più monitorarlo per le modifiche. Il sistema grafico può anche eseguire altre ottimizzazioni, perché sa che il pennello non cambierà.

> [!NOTE]
> Per praticità, gli oggetti Freezable rimangono bloccati a meno che non vengano bloccati in modo esplicito.

<a name="frozenfreezables"></a>

## <a name="using-freezables"></a>Uso di Freezable

L'utilizzo di un oggetto Freezable sbloccato è analogo all'utilizzo di qualsiasi altro tipo di oggetto. Nell'esempio seguente, il colore di un oggetto <xref:System.Windows.Media.SolidColorBrush> viene modificato da giallo a rosso dopo che è stato usato per disegnare lo sfondo di un pulsante. Il sistema grafico funziona dietro le quinte per modificare automaticamente il pulsante da giallo a rosso alla successiva aggiornamento dello schermo.

[!code-csharp[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
[!code-vb[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]

### <a name="freezing-a-freezable"></a>Blocco di un oggetto Freezable

Per rendere <xref:System.Windows.Freezable> immodificabile, chiamare il relativo <xref:System.Windows.Freezable.Freeze%2A> metodo. Quando si blocca un oggetto che contiene oggetti Freezable, anche questi oggetti sono bloccati. Se, ad esempio, si blocca <xref:System.Windows.Media.PathGeometry>un oggetto, le figure e i segmenti in esso contenuti verrebbero bloccati.

Un oggetto Freezable **non può** essere bloccato se si verifica una delle condizioni seguenti:

- Dispone di proprietà animate o con associazione a dati.

- Dispone di proprietà impostate da una risorsa dinamica. Per ulteriori informazioni sulle risorse dinamiche, vedere le [risorse XAML](xaml-resources.md) .

- Contiene <xref:System.Windows.Freezable> oggetti secondari che non possono essere bloccati.

Se queste condizioni sono false e non si intende modificare il <xref:System.Windows.Freezable>, è consigliabile bloccarlo per ottenere i vantaggi in termini di prestazioni descritti in precedenza.

Una volta chiamato il metodo di <xref:System.Windows.Freezable.Freeze%2A> un oggetto Freezable, non è più possibile modificarlo. Il tentativo di modificare un oggetto bloccato causa la <xref:System.InvalidOperationException> generazione di un'eccezione. Il codice seguente genera un'eccezione, perché si tenta di modificare il pennello dopo che è stato bloccato.

[!code-csharp[freezablesample_procedural#ExceptionExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
[!code-vb[freezablesample_procedural#ExceptionExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]

Per evitare di generare questa eccezione, è possibile usare <xref:System.Windows.Freezable.IsFrozen%2A> il metodo per determinare se <xref:System.Windows.Freezable> un oggetto è bloccato.

[!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
[!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]

Nell'esempio di codice precedente, è stata eseguita una copia modificabile di un oggetto bloccato <xref:System.Windows.Freezable.Clone%2A> usando il metodo. La sezione successiva illustra la clonazione in modo più dettagliato.

> [!NOTE]
> Poiché non è possibile animare un oggetto Freezable bloccato, il sistema di animazione creerà automaticamente cloni <xref:System.Windows.Freezable> modificabili di oggetti bloccati quando si tenta di animarli con un oggetto. <xref:System.Windows.Media.Animation.Storyboard> Per eliminare l'overhead delle prestazioni causato dalla clonazione, lasciare un oggetto non bloccato se si intende animarlo. Per ulteriori informazioni sull'animazione con gli storyboard, vedere [Cenni preliminari sugli storyboard](../graphics-multimedia/storyboards-overview.md).

### <a name="freezing-from-markup"></a>Blocco dal markup

Per bloccare un <xref:System.Windows.Freezable> oggetto dichiarato nel markup, usare l' `PresentationOptions:Freeze` attributo. Nell'esempio seguente un oggetto <xref:System.Windows.Media.SolidColorBrush> viene dichiarato come risorsa di pagina e bloccato. Viene quindi usato per impostare lo sfondo di un pulsante.

[!code-xaml[FreezableSample#FreezeFromMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]

Per utilizzare l' `Freeze` attributo, è necessario eseguire il mapping allo spazio dei nomi `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`delle opzioni di presentazione:. `PresentationOptions`è il prefisso consigliato per il mapping di questo spazio dei nomi:

```xaml
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"
```

Poiché non tutti i lettori XAML riconoscono questo attributo, è consigliabile usare l' [attributo MC: Ignorable](mc-ignorable-attribute.md) per contrassegnare `Presentation:Freeze` l'attributo come ignorabile:

```xaml
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
mc:Ignorable="PresentationOptions"
```

Per ulteriori informazioni, vedere la pagina relativa all' [attributo MC: Ignorable](mc-ignorable-attribute.md) .

### <a name="unfreezing-a-freezable"></a>"Sblocco" di un oggetto Freezable

Una volta bloccato, <xref:System.Windows.Freezable> un oggetto non può mai essere modificato o sbloccato; tuttavia, è possibile creare un clone non <xref:System.Windows.Freezable.Clone%2A> bloccato <xref:System.Windows.Freezable.CloneCurrentValue%2A> usando il metodo o.

Nell'esempio seguente lo sfondo del pulsante viene impostato con un pennello e il pennello viene quindi bloccato. Viene eseguita una copia non bloccata del pennello utilizzando il <xref:System.Windows.Freezable.Clone%2A> metodo. Il clone viene modificato e usato per modificare lo sfondo del pulsante da giallo a rosso.

[!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
[!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]

> [!NOTE]
> Indipendentemente dal metodo di clonazione usato, le animazioni non vengono mai copiate nel <xref:System.Windows.Freezable>nuovo oggetto.

I <xref:System.Windows.Freezable.Clone%2A> metodi <xref:System.Windows.Freezable.CloneCurrentValue%2A> e producono copie complete dell'oggetto Freezable. Se l'oggetto Freezable contiene altri oggetti Freezable bloccati, questi vengono anche clonati e resi modificabili. Se, ad esempio, si clona un <xref:System.Windows.Media.PathGeometry> oggetto bloccato per renderlo modificabile, anche le figure e i segmenti in esso contenuti vengono copiati e resi modificabili.

<a name="createyourownfreezableclass"></a>

## <a name="creating-your-own-freezable-class"></a>Creazione di una classe Freezable personalizzata

Una classe che deriva da <xref:System.Windows.Freezable> ottiene le funzionalità seguenti.

- Stati speciali: uno stato di sola lettura (bloccato) e scrivibile.

- Thread safety: un <xref:System.Windows.Freezable> oggetto bloccato può essere condiviso tra thread.

- Notifica dettagliata delle modifiche: Diversamente da altri <xref:System.Windows.DependencyObject>, gli oggetti Freezable forniscono notifiche di modifica quando cambiano i valori delle sottoproprietà.

- Clonazione semplice: la classe Freezable ha già implementato diversi metodi che producono cloni profondi.

Un <xref:System.Windows.Freezable> è un tipo di <xref:System.Windows.DependencyObject>e pertanto utilizza il sistema di proprietà di dipendenza. Non è necessario che le proprietà della classe siano proprietà di dipendenza, ma l'uso delle proprietà di dipendenza ridurrà la quantità di codice da <xref:System.Windows.Freezable> scrivere, perché la classe è stata progettata tenendo conto delle proprietà di dipendenza. Per ulteriori informazioni sul sistema di proprietà di dipendenza, vedere [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md).

Ogni <xref:System.Windows.Freezable> sottoclasse deve eseguire <xref:System.Windows.Freezable.CreateInstanceCore%2A> l'override del metodo. Se la classe USA proprietà di dipendenza per tutti i dati, l'operazione è terminata.

Se la classe contiene membri dati di proprietà non di dipendenza, è necessario anche eseguire l'override dei metodi seguenti:

- <xref:System.Windows.Freezable.CloneCore%2A>

- <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>

- <xref:System.Windows.Freezable.GetAsFrozenCore%2A>

- <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>

- <xref:System.Windows.Freezable.FreezeCore%2A>

È inoltre necessario osservare le regole seguenti per l'accesso e la scrittura a membri dati che non sono proprietà di dipendenza:

- All'inizio di qualsiasi API che legge i membri dati della proprietà non di dipendenza, chiamare <xref:System.Windows.Freezable.ReadPreamble%2A> il metodo.

- All'inizio di qualsiasi API che scrive i membri dati della proprietà non di dipendenza, chiamare <xref:System.Windows.Freezable.WritePreamble%2A> il metodo. (Dopo aver chiamato <xref:System.Windows.Freezable.WritePreamble%2A> in un'API, non è necessario effettuare una chiamata aggiuntiva a <xref:System.Windows.Freezable.ReadPreamble%2A> se si leggono anche i membri dati della proprietà non di dipendenza).

- Chiamare il <xref:System.Windows.Freezable.WritePostscript%2A> metodo prima di uscire da metodi che scrivono in membri dati di proprietà non di dipendenza.

Se la classe contiene membri dati di proprietà non dipendenza che sono <xref:System.Windows.DependencyObject> oggetti, è necessario chiamare anche il <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> metodo ogni volta che si modifica uno dei relativi valori, anche se si imposta il membro su `null`.

> [!NOTE]
> È molto importante iniziare ogni <xref:System.Windows.Freezable> metodo di cui si esegue l'override con una chiamata all'implementazione di base.

Per un esempio di classe personalizzata <xref:System.Windows.Freezable> , vedere l' [esempio di animazione personalizzata](https://go.microsoft.com/fwlink/?LinkID=159981).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Freezable>
- [Esempio di animazione personalizzata](https://go.microsoft.com/fwlink/?LinkID=159981)
- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
