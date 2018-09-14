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
ms.openlocfilehash: a1006816168e405d0d79786b8430b802f1ec0928
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45507940"
---
# <a name="freezable-objects-overview"></a>Cenni preliminari sugli oggetti Freezable
In questo argomento viene descritto come creare e utilizzare in modo efficace <xref:System.Windows.Freezable> oggetti, che forniscono funzionalità speciali che consentono di migliorare le prestazioni dell'applicazione. Sono esempi di oggetti freezable pennelli, penne, trasformazioni, geometrie e animazioni.  
  
<a name="whatisafreezable"></a>   
## <a name="what-is-a-freezable"></a>Che cos'è un oggetto Freezable?  
 Oggetto <xref:System.Windows.Freezable> è un tipo speciale di oggetto che dispone di due stati: non bloccato e bloccato. Quando non è bloccato, un <xref:System.Windows.Freezable> si comporta come qualsiasi altro oggetto. Quando è bloccato, un <xref:System.Windows.Freezable> non può più essere modificato.  
  
 Oggetto <xref:System.Windows.Freezable> fornisce un <xref:System.Windows.Freezable.Changed> evento per notificare agli osservatori di eventuali modifiche all'oggetto. Il blocco di un <xref:System.Windows.Freezable> può migliorare le prestazioni, poiché non è più necessario impiegare le risorse nelle notifiche di modifica. Un oggetto bloccato <xref:System.Windows.Freezable> può essere condivisa anche tra i thread, mentre un non bloccate <xref:System.Windows.Freezable> non è possibile.  
  
 Anche se il <xref:System.Windows.Freezable> classe dispone di molte applicazioni, più <xref:System.Windows.Freezable> gli oggetti in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sono correlati al sottosistema di grafica.  
  
 Il <xref:System.Windows.Freezable> classe rende più semplice usare determinati oggetti di sistema di grafica e consentono di migliorare le prestazioni dell'applicazione. Esempi di tipi da cui ereditare <xref:System.Windows.Freezable> includono il <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, e <xref:System.Windows.Media.Geometry> classi. Poiché contengono le risorse non gestite, il sistema deve monitorare questi oggetti per le modifiche e quindi aggiornare le risorse non gestite, quando viene apportata una modifica all'oggetto originale. Anche se non viene effettivamente modificato un oggetto di sistema di grafica, il sistema deve comunque impiegano alcune delle relative risorse, l'oggetto di monitoraggio nel caso in cui si modifica tale valore.  
  
 Si supponga, ad esempio, creare un <xref:System.Windows.Media.SolidColorBrush> pennello da utilizzare per disegnare lo sfondo di un pulsante.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]  
  
 Il rendering del pulsante di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sottosistema grafico utilizza le informazioni fornite per disegnare un gruppo di pixel per definire l'aspetto di un pulsante. Anche se è usato un pennello di colore a tinta unita per descrivere la modalità è necessario disegnare il pulsante, il pennello di colore a tinta unita non esegue il disegno. Il sistema grafico genera oggetti veloci di basso livello per il pulsante e il pennello, ed è gli oggetti che vengono visualizzati sullo schermo.  
  
 Se fosse necessario modificare il pennello, dovrà essere rigenerati gli oggetti di basso livello. La classe freezable è un pennello che cosa offre la possibilità di trovare gli oggetti di basso livello generati corrispondenti e aggiornarli in caso di modifiche. Quando questa funzionalità è abilitata, il pennello è definito come "fisse".  
  
 Un oggetto freezable <xref:System.Windows.Freezable.Freeze%2A> metodo consente di disabilitare questa possibilità di aggiornamento automatico. È possibile utilizzare questo metodo per rendere il pennello diventano "bloccata" o non modificabile.  
  
> [!NOTE]
>  Non tutti gli oggetti Freezable possono essere bloccato. Per evitare la generazione di un' <xref:System.InvalidOperationException>, controllare il valore dell'oggetto Freezable <xref:System.Windows.Freezable.CanFreeze%2A> proprietà per determinare se può essere bloccata prima di provare a bloccare.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]  
  
 Quando si non è più necessario modificare un oggetto freezable, bloccandolo offre i vantaggi delle prestazioni. Se fosse necessario bloccare il pennello in questo esempio, il sistema grafico non è più necessario verificare la presenza di modifiche. Il sistema grafico può anche rendere altre ottimizzazioni, perché è in grado di che pennello non subirà modifiche.  
  
> [!NOTE]
>  Per praticità, sugli oggetti freezable rimangono non bloccati a meno che non si blocca in modo esplicito.  
  
<a name="frozenfreezables"></a>   
## <a name="using-freezables"></a>Utilizzo degli oggetti Freezable  
 Usando un non bloccate freezable è simile all'utilizzo di qualsiasi altro tipo di oggetto. Nell'esempio seguente, il colore di un <xref:System.Windows.Media.SolidColorBrush> viene modificata da giallo a rosso, dopo essere stato utilizzato per disegnare lo sfondo di un pulsante. Il sistema grafico opera dietro le quinte per modificare automaticamente il pulsante da giallo a rosso al successivo che aggiornamento della schermata.  
  
 [!code-csharp[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
 [!code-vb[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]  
  
### <a name="freezing-a-freezable"></a>Il blocco di un oggetto Freezable  
 Per rendere un <xref:System.Windows.Freezable> immodificabile, chiamare il <xref:System.Windows.Freezable.Freeze%2A> (metodo). Quando si blocca un oggetto che contiene oggetti freezable, vengono bloccati anche tali oggetti. Ad esempio, se si blocca un <xref:System.Windows.Media.PathGeometry>, le figure e i segmenti in esso contenuti vengono bloccate anche.  
  
 Un oggetto Freezable **non è possibile** essere bloccato se viene soddisfatta una delle operazioni seguenti:  
  
-   È stata eseguita l'animazione o le proprietà con associazione a dati.  
  
-   Include proprietà impostata da una risorsa dinamica. (Vedere la [risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md) per altre informazioni sulle risorse dinamiche.)  
  
-   Contiene <xref:System.Windows.Freezable> oggetti secondari che non possono essere bloccati.  
  
 Se queste condizioni sono false e non si prevede di modificare il <xref:System.Windows.Freezable>, quindi è necessario bloccare in modo da ottenere i vantaggi di prestazioni descritti in precedenza.  
  
 Dopo aver chiamato un oggetto freezable <xref:System.Windows.Freezable.Freeze%2A> (metodo), non può più essere modificato. Tenta di modificare un oggetto bloccato dell'oggetto cause un <xref:System.InvalidOperationException> generata. Il codice seguente genera un'eccezione, perché si tenta di modificare il pennello dopo che è stato bloccato.  
  
 [!code-csharp[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
 [!code-vb[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]  
  
 Per evitare la generazione di questa eccezione, è possibile usare la <xref:System.Windows.Freezable.IsFrozen%2A> metodo per determinare se un <xref:System.Windows.Freezable> è bloccato.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 Nell'esempio di codice precedente, è stata creata una copia modificabile di un oggetto bloccato tramite le <xref:System.Windows.Freezable.Clone%2A> (metodo). La sezione seguente illustra la clonazione in modo più dettagliato.  
  
 **Nota** perché un oggetto bloccato freezable non possono essere animata, il sistema di animazione creerà automaticamente duplicati modificabili di bloccate <xref:System.Windows.Freezable> gli oggetti quando si tenta di aggiungere un'animazione con una <xref:System.Windows.Media.Animation.Storyboard>. Per eliminare le prestazioni overhead causata dalla clonazione, lasciare non bloccato se si prevede di aggiungere un'animazione, l'oggetto. Per altre informazioni sull'animazione con gli storyboard, vedere la [Cenni preliminari sugli storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
### <a name="freezing-from-markup"></a>Blocco dal Markup  
 Per bloccare un <xref:System.Windows.Freezable> oggetto dichiarato nel markup, si utilizza il `PresentationOptions:Freeze` attributo. Nell'esempio seguente, un <xref:System.Windows.Media.SolidColorBrush> è dichiarato come una risorsa di pagina e bloccato. Quindi utilizzato per impostare lo sfondo di un pulsante.  
  
 [!code-xaml[FreezableSample#FreezeFromMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]  
  
 Usare la `Freeze` attributo, è necessario eseguire il mapping allo spazio dei nomi di opzioni di presentazione: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`. `PresentationOptions` è il prefisso consigliato per il mapping di questo spazio dei nomi:  
  
```  
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"   
```  
  
 Poiché non tutti i reader XAML riconoscono questo attributo, è consigliabile usare la [mc: attributo Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) per contrassegnare il `Presentation:Freeze` dell'attributo come ignorable:  
  
```  
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
mc:Ignorable="PresentationOptions"  
```  
  
 Per altre informazioni, vedere la [mc: Ignorable attributo](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) pagina.  
  
### <a name="unfreezing-a-freezable"></a>"L'operazione di sblocco" un oggetto Freezable  
 Una volta bloccate, una <xref:System.Windows.Freezable> non possono mai essere modificati o non è bloccato; tuttavia, è possibile creare un clone non bloccato usando le <xref:System.Windows.Freezable.Clone%2A> o <xref:System.Windows.Freezable.CloneCurrentValue%2A> (metodo).  
  
 Nell'esempio seguente viene impostato lo sfondo dei pulsanti con un pennello e che poi viene bloccato. È costituita il pennello usando la copia non bloccata la <xref:System.Windows.Freezable.Clone%2A> (metodo). Il clone viene modificato e utilizzato per modificare lo sfondo del pulsante da giallo a rosso.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
> [!NOTE]
>  Indipendentemente dal metodo clone è utilizzare, le animazioni non vengono mai copiate nel nuovo <xref:System.Windows.Freezable>.  
  
 Il <xref:System.Windows.Freezable.Clone%2A> e <xref:System.Windows.Freezable.CloneCurrentValue%2A> metodi producono copie complete dell'oggetto freezable. Se l'oggetto contiene altri oggetti freezable bloccati, sono anche clonati e resi modificabili. Ad esempio, se si clona un oggetto bloccato <xref:System.Windows.Media.PathGeometry> per renderlo modificabile, le figure e i segmenti in esso contenuti vengono inoltre copiati e reso modificabile.  
  
<a name="createyourownfreezableclass"></a>   
## <a name="creating-your-own-freezable-class"></a>Creare la propria classe Freezable  
 Una classe che deriva da <xref:System.Windows.Freezable> Ottiene le funzionalità seguenti.  
  
-   Stati speciali: sola lettura (bloccato) e uno stato accessibile in scrittura.  
  
-   Sicurezza dei thread: un oggetto bloccato <xref:System.Windows.Freezable> possono essere condivisi tra thread.  
  
-   Notifica dettagliata delle modifiche: a differenza di altri <xref:System.Windows.DependencyObject>, sugli oggetti Freezable forniscono le notifiche di modifica quando cambiano i valori delle sottoproprietà.  
  
-   La clonazione semplice: la classe Freezable ha già implementato diversi metodi che producono cloni.  
  
 Oggetto <xref:System.Windows.Freezable> è un tipo di <xref:System.Windows.DependencyObject>e pertanto utilizza il sistema di proprietà di dipendenza. Le proprietà di classe non devono essere proprietà di dipendenza, ma usando le proprietà di dipendenza ridurrà la quantità di codice da scrivere, perché il <xref:System.Windows.Freezable> classe è stata progettata tenendo presenti le proprietà di dipendenza. Per altre informazioni sul sistema di proprietà di dipendenza, vedere la [Cenni preliminari sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
 Ogni <xref:System.Windows.Freezable> sottoclasse deve eseguire l'override di <xref:System.Windows.Freezable.CreateInstanceCore%2A> (metodo). Se la classe Usa le proprietà di dipendenza per tutti i relativi dati, si è finito.  
  
 Se la classe contiene membri dati della proprietà non di dipendenza, è inoltre necessario sostituire i metodi seguenti:  
  
-   <xref:System.Windows.Freezable.CloneCore%2A>  
  
-   <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>  
  
-   <xref:System.Windows.Freezable.GetAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.FreezeCore%2A>  
  
 È inoltre necessario rispettare le regole seguenti per l'accesso e la scrittura in membri dati che non sono proprietà di dipendenza:  
  
-   All'inizio di qualsiasi [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] che legge i membri dati della proprietà di dipendenza non, chiamare il <xref:System.Windows.Freezable.ReadPreamble%2A> (metodo).  
  
-   All'inizio di qualsiasi API che consente di scrivere membri dati della proprietà di dipendenza non, chiamare il <xref:System.Windows.Freezable.WritePreamble%2A> (metodo). (Dopo aver chiamato <xref:System.Windows.Freezable.WritePreamble%2A> in un [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], non è necessario effettuare una chiamata aggiuntiva a <xref:System.Windows.Freezable.ReadPreamble%2A> se è stato inoltre leggere i membri dati della proprietà di dipendenza non.)  
  
-   Chiamare il <xref:System.Windows.Freezable.WritePostscript%2A> metodo prima di uscire dai metodi che scrivono in membri dati della proprietà di dipendenza non.  
  
 Se la classe contiene membri dati non della proprietà di dipendenza <xref:System.Windows.DependencyObject> oggetti, è necessario chiamare anche il <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> metodo ogni volta che viene modificato uno dei relativi valori, anche se si imposta il membro `null`.  
  
> [!NOTE]
>  È molto importante iniziare ogni <xref:System.Windows.Freezable> metodo si esegue l'override con una chiamata all'implementazione di base.  
  
 Per un esempio di una classe personalizzata <xref:System.Windows.Freezable> classe, vedere la [esempio di animazione personalizzata](https://go.microsoft.com/fwlink/?LinkID=159981).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Freezable>  
 [Esempio di animazione personalizzata](https://go.microsoft.com/fwlink/?LinkID=159981)  
 [Panoramica sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Proprietà di dipendenza personalizzate](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
