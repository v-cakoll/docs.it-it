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
ms.openlocfilehash: d3b9f6f7af22b2a846f4ee34e8d4d00bb032fd69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="freezable-objects-overview"></a>Cenni preliminari sugli oggetti Freezable
In questo argomento viene descritto come creare e utilizzare in modo efficace <xref:System.Windows.Freezable> oggetti, che forniscono funzionalità speciali che consentono di migliorare le prestazioni dell'applicazione. Sono esempi di oggetti freezable pennelli, penne, trasformazioni, geometrie e animazioni.  
  
<a name="whatisafreezable"></a>   
## <a name="what-is-a-freezable"></a>Che cos'è un oggetto Freezable?  
 Oggetto <xref:System.Windows.Freezable> è un tipo speciale di oggetto che presenta due stati: non bloccato e bloccato. Quando non è bloccato, un <xref:System.Windows.Freezable> si comporta come qualsiasi altro oggetto. Quando è bloccato, un <xref:System.Windows.Freezable> non può più essere modificato.  
  
 Oggetto <xref:System.Windows.Freezable> fornisce un <xref:System.Windows.Freezable.Changed> evento per notificare agli osservatori di tutte le modifiche all'oggetto. Il blocco di un <xref:System.Windows.Freezable> può migliorare le prestazioni, poiché non è più necessario impiegare le risorse nelle notifiche di modifica. Un oggetto bloccato <xref:System.Windows.Freezable> possono anche essere condivise tra thread mentre ciò <xref:System.Windows.Freezable> non è possibile.  
  
 Sebbene il <xref:System.Windows.Freezable> classe dispone di molte applicazioni, più <xref:System.Windows.Freezable> oggetti [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sono correlati al sottosistema di grafica.  
  
 La <xref:System.Windows.Freezable> classe semplifica l'utilizzo di alcuni oggetti di sistema di grafica e consente di migliorare le prestazioni dell'applicazione. Esempi di tipi che ereditano da <xref:System.Windows.Freezable> includono il <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, e <xref:System.Windows.Media.Geometry> classi. In quanto contengono le risorse non gestite, il sistema deve monitorare questi oggetti per le modifiche e quindi aggiornare le risorse non gestite quando viene apportata una modifica all'oggetto originale. Anche se non viene effettivamente modificato un oggetto di sistema di grafica, il sistema deve comunque impiegare alcune delle relative risorse, l'oggetto di monitoraggio nel caso in cui vengono modificate.  
  
 Si supponga, ad esempio, creare un <xref:System.Windows.Media.SolidColorBrush> pennello da utilizzare per disegnare lo sfondo di un pulsante.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]  
  
 Quando viene eseguito il rendering sul pulsante, il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sottosistema grafico utilizza le informazioni fornite per disegnare un gruppo di pixel per definire l'aspetto di un pulsante. Anche se è stata utilizzata per descrivere come il pulsante deve essere disegnato un pennello tinta unita, il pennello tinta unita non esegue effettivamente il disegno. Il sistema grafico genera oggetti veloci di basso livello per il pulsante e il pennello, ed è tali oggetti che vengono visualizzati sullo schermo.  
  
 Se fosse necessario modificare il pennello, dovranno essere rigenerati gli oggetti di basso livello. La classe oggetto freezable è un pennello cosa offre la possibilità di trovare gli oggetti di basso livello generati corrispondenti e aggiornarli in caso di modifiche. Quando questa funzionalità è abilitata, il pennello è definito "non bloccato".  
  
 Un oggetto freezable <xref:System.Windows.Freezable.Freeze%2A> metodo consente di disabilitare questa possibilità di aggiornamento automatico. È possibile utilizzare questo metodo per rendere il pennello diventano "bloccata" o non modificabile.  
  
> [!NOTE]
>  Non tutti gli oggetti Freezable possono essere bloccato. Per evitare di generare un <xref:System.InvalidOperationException>, controllare il valore dell'oggetto Freezable <xref:System.Windows.Freezable.CanFreeze%2A> proprietà per determinare se può essere bloccata prima di provare a bloccare.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]  
  
 Quando non è necessario modificare un oggetto freezable, bloccandolo offre i vantaggi di prestazioni. Se è necessario bloccare il pennello in questo esempio, il sistema grafico sarebbe non più necessario verificare la presenza di modifiche. Il sistema grafico può inoltre effettuare altre ottimizzazioni, poiché che il pennello non cambia.  
  
> [!NOTE]
>  Per comodità, gli oggetti freezable restano non bloccati a meno che non si blocca in modo esplicito.  
  
<a name="frozenfreezables"></a>   
## <a name="using-freezables"></a>Utilizzo degli oggetti Freezable  
 Utilizzando un sbloccata freezable è simile all'utilizzo di qualsiasi altro tipo di oggetto. Nell'esempio seguente, il colore di un <xref:System.Windows.Media.SolidColorBrush> viene modificata da giallo a rosso dopo essere stato utilizzato per disegnare lo sfondo di un pulsante. Il sistema grafico funziona in background per modificare automaticamente il pulsante da giallo a rosso alla successiva che la schermata viene aggiornata.  
  
 [!code-csharp[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
 [!code-vb[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]  
  
### <a name="freezing-a-freezable"></a>Il blocco di un oggetto Freezable  
 Per rendere un <xref:System.Windows.Freezable> non modificabile, chiamare il relativo <xref:System.Windows.Freezable.Freeze%2A> metodo. Quando si blocca un oggetto che contiene gli oggetti freezable, vengono bloccati anche tali oggetti. Ad esempio, se si blocca un <xref:System.Windows.Media.PathGeometry>, le figure e i segmenti in esso contenuti vengono bloccate anche.  
  
 Un oggetto Freezable **Impossibile** essere bloccato se una delle seguenti sono vere:  
  
-   È stata eseguita l'animazione o la proprietà con associazione a dati.  
  
-   Include le proprietà impostate da una risorsa dinamica. (Vedere il [risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md) per ulteriori informazioni sulle risorse dinamiche.)  
  
-   Contiene <xref:System.Windows.Freezable> oggetti secondari che non possono essere bloccati.  
  
 Se queste condizioni sono false e non si desidera modificare il <xref:System.Windows.Freezable>, quindi è necessario bloccare in modo da migliorare le prestazioni descritte in precedenza.  
  
 Dopo aver chiamato un oggetto freezable <xref:System.Windows.Freezable.Freeze%2A> metodo, non può più essere modificato. Il tentativo di modificare un oggetto bloccato dell'oggetto cause un <xref:System.InvalidOperationException> generata. Il codice seguente genera un'eccezione, perché si tenta di modificare il pennello dopo che è stato bloccato.  
  
 [!code-csharp[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
 [!code-vb[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]  
  
 Per evitare di generare questa eccezione, è possibile utilizzare il <xref:System.Windows.Freezable.IsFrozen%2A> metodo per determinare se un <xref:System.Windows.Freezable> è bloccata.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 Nell'esempio di codice precedente è stata eseguita una copia modificabile di un oggetto bloccato utilizzando il <xref:System.Windows.Freezable.Clone%2A> metodo. La sezione successiva illustra la clonazione in modo più dettagliato.  
  
 **Nota** perché un oggetto bloccato freezable non può essere aggiunta un'animazione, animazione verranno automaticamente creati cloni modificabili di bloccato <xref:System.Windows.Freezable> oggetti quando si tenta di aggiungere un'animazione con un <xref:System.Windows.Media.Animation.Storyboard>. Per eliminare le prestazioni overhead causata dalla clonazione, lasciare non bloccato se si intende animare l'oggetto. Per ulteriori informazioni sull'animazione con storyboard, vedere il [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
### <a name="freezing-from-markup"></a>Blocco dal Markup  
 Per bloccare un <xref:System.Windows.Freezable> oggetto dichiarato nel markup, si utilizza il `PresentationOptions:Freeze` attributo. Nell'esempio seguente, un <xref:System.Windows.Media.SolidColorBrush> è dichiarato come una risorsa di pagina e bloccato. E viene quindi utilizzato per impostare lo sfondo di un pulsante.  
  
 [!code-xaml[FreezableSample#FreezeFromMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]  
  
 Utilizzare il `Freeze` attributo, è necessario eseguire il mapping allo spazio dei nomi di opzioni di presentazione: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`. `PresentationOptions` è il prefisso consigliato per il mapping di questo spazio dei nomi:  
  
```  
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"   
```  
  
 Poiché non tutti i reader XAML riconoscono questo attributo, è consigliabile utilizzare il [mc: attributo Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) per contrassegnare il `Presentation:Freeze` attributo ignorable:  
  
```  
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
mc:Ignorable="PresentationOptions"  
```  
  
 Per ulteriori informazioni, vedere il [mc: attributo Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) pagina.  
  
### <a name="unfreezing-a-freezable"></a>"L'operazione di sblocco" un oggetto Freezable  
 Una volta bloccato, un <xref:System.Windows.Freezable> non può essere modificata o non è bloccato; tuttavia, è possibile creare un clone non bloccato utilizzando il <xref:System.Windows.Freezable.Clone%2A> o <xref:System.Windows.Freezable.CloneCurrentValue%2A> (metodo).  
  
 Nell'esempio seguente, lo sfondo del pulsante viene impostato con un pennello e che quindi è bloccato. È una copia non bloccata del pennello utilizzando il <xref:System.Windows.Freezable.Clone%2A> metodo. Il clone viene modificato e utilizzato per modificare lo sfondo del pulsante da giallo a rosso.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
> [!NOTE]
>  Indipendentemente dal fatto il metodo clone da utilizzare, le animazioni non vengono mai copiate nel nuovo <xref:System.Windows.Freezable>.  
  
 Il <xref:System.Windows.Freezable.Clone%2A> e <xref:System.Windows.Freezable.CloneCurrentValue%2A> producano copie complete dell'oggetto freezable. Se l'oggetto contiene altri oggetti freezable bloccati, sono anche duplicate e resi modificabili. Ad esempio, se si clona un oggetto bloccato <xref:System.Windows.Media.PathGeometry> per renderlo modificabile, le figure e i segmenti in esso contenuti vengono inoltre copiati e resi modificabili.  
  
<a name="createyourownfreezableclass"></a>   
## <a name="creating-your-own-freezable-class"></a>Creazione di una classe oggetto Freezable  
 Una classe che deriva da <xref:System.Windows.Freezable> Ottiene le funzionalità seguenti.  
  
-   Stati speciali: sola lettura (bloccato) e uno stato accessibile in scrittura.  
  
-   Sicurezza dei thread: un oggetto bloccato <xref:System.Windows.Freezable> può essere condivisa tra thread.  
  
-   Notifica dettagliata delle modifiche: a differenza degli altri <xref:System.Windows.DependencyObject>s, gli oggetti Freezable forniscono le notifiche di modifica quando cambiano i valori delle sottoproprietà.  
  
-   Clonazione facile: la classe Freezable ha già implementato diversi metodi che producono cloni.  
  
 Oggetto <xref:System.Windows.Freezable> è un tipo di <xref:System.Windows.DependencyObject>e pertanto viene usato il sistema di proprietà di dipendenza. Le proprietà di classe non debbano di proprietà di dipendenza, ma utilizzando proprietà di dipendenza consente di ridurre la quantità di codice da scrivere, poiché è il <xref:System.Windows.Freezable> classe è stata progettata tenendo presenti le proprietà di dipendenza. Per ulteriori informazioni sul sistema di proprietà di dipendenza, vedere il [Cenni preliminari sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
 Ogni <xref:System.Windows.Freezable> sottoclasse deve eseguire l'override di <xref:System.Windows.Freezable.CreateInstanceCore%2A> metodo. Se la classe utilizza le proprietà di dipendenza per tutti i relativi dati, si è finito.  
  
 Se la classe contiene membri dati della proprietà di non dipendenza, è inoltre necessario sostituire i metodi seguenti:  
  
-   <xref:System.Windows.Freezable.CloneCore%2A>  
  
-   <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>  
  
-   <xref:System.Windows.Freezable.GetAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.FreezeCore%2A>  
  
 Inoltre, è necessario osservare le seguenti regole per l'accesso e la scrittura in membri di dati che non sono proprietà di dipendenza:  
  
-   All'inizio di qualsiasi [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] che legge i membri dati della proprietà di non dipendenza, chiamare il <xref:System.Windows.Freezable.ReadPreamble%2A> metodo.  
  
-   All'inizio di qualsiasi API che scrive i membri dati della proprietà di non dipendenza, chiamare il <xref:System.Windows.Freezable.WritePreamble%2A> metodo. (Dopo aver chiamato <xref:System.Windows.Freezable.WritePreamble%2A> in un [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], non è necessario effettuare una chiamata aggiuntiva al <xref:System.Windows.Freezable.ReadPreamble%2A> se leggere anche i membri dati della proprietà di non dipendenza.)  
  
-   Chiamare il <xref:System.Windows.Freezable.WritePostscript%2A> metodo prima di uscire dai metodi che scrivono in membri dati della proprietà di non dipendenza.  
  
 Se la classe contiene membri dati della proprietà di dipendenza non <xref:System.Windows.DependencyObject> oggetti, è necessario chiamare anche il <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> metodo ogni volta che viene modificato uno dei relativi valori, anche se il membro viene impostato su `null`.  
  
> [!NOTE]
>  È molto importante iniziare ogni <xref:System.Windows.Freezable> metodo si esegue l'override con una chiamata all'implementazione di base.  
  
 Per un esempio di un oggetto personalizzato <xref:System.Windows.Freezable> classe, vedere il [esempio di animazione personalizzata](http://go.microsoft.com/fwlink/?LinkID=159981).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Freezable>  
 [Esempio di animazione personalizzata](http://go.microsoft.com/fwlink/?LinkID=159981)  
 [Panoramica sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Proprietà di dipendenza personalizzate](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
