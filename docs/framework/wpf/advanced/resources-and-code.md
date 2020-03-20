---
title: Risorse e codice
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys [WPF], using objects as
- resources [WPF], accessing from procedural code
- procedural code [WPF], creating resources with
- procedural code [WPF], accessing resources from
- resources [WPF], creating with procedural code
ms.assetid: c1cfcddb-e39c-41c8-a7f3-60984914dfae
ms.openlocfilehash: 2917c9d15a6195c2d67781d6b2cfb0a5f1c136d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187161"
---
# <a name="resources-and-code"></a>Risorse e codice
Questo argomento illustra le modalità di accesso alle risorse di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] o di creazione delle risorse stesse tramite codice anziché tramite la sintassi [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Per altre informazioni sull'uso delle risorse in generale e sulle risorse dal punto di vista della sintassi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], vedere [Risorse XAML](xaml-resources.md).  

<a name="accessing"></a>
## <a name="accessing-resources-from-code"></a>Accesso alle risorse dal codice  
 Le chiavi che identificano le risorse, se definite tramite [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], possono essere usate anche per recuperare risorse specifiche qualora si richieda la risorsa nel codice. Il modo più semplice per recuperare una <xref:System.Windows.FrameworkElement.FindResource%2A> risorsa <xref:System.Windows.FrameworkElement.TryFindResource%2A> dal codice consiste nel chiamare il o il metodo da oggetti a livello di framework nell'applicazione. La differenza di comportamento tra i due metodi sta nell'azione eseguita quando la chiave richiesta non viene trovata. <xref:System.Windows.FrameworkElement.FindResource%2A>genera un'eccezione; <xref:System.Windows.FrameworkElement.TryFindResource%2A> non genererà un'eccezione, ma restituisce `null`. Ogni metodo accetta la chiave di risorsa come parametro di input e restituisce un oggetto debolmente tipizzato. In genere una chiave di risorsa è una stringa, ma esistono utilizzi occasionali di tipo non stringa. Per informazioni dettagliate, vedere la sezione [Uso di oggetti come chiavi](#objectaskey). Di regola, il cast dell'oggetto restituito viene eseguito nel tipo richiesto dalla proprietà impostata al momento della richiesta della risorsa. La logica di ricerca per la risoluzione della risorsa codice è la stessa del codice [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] del riferimento di risorsa dinamica. La ricerca delle risorse ha inizio dall'elemento chiamante e continua con gli elementi padre successivi dell'albero logico. Prosegue quindi nelle risorse, nei temi e, se necessario, nelle risorse di sistema dell'applicazione. Una richiesta di codice per una risorsa terrà in considerazione le modifiche di runtime eventualmente apportate ai dizionari risorse successivamente al caricamento di un determinato dizionario risorse da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], oltre che le modifiche apportate alle risorse di sistema in tempo reale.  
  
 Di seguito è riportato un breve esempio di codice che trova una risorsa <xref:System.Windows.Controls.Primitives.ButtonBase.Click> in base alla chiave e usa il valore restituito per impostare una proprietà, implementata come gestore eventi.  
  
 [!code-csharp[PropertiesOvwSupport#ResourceProceduralGet](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#resourceproceduralget)]
 [!code-vb[PropertiesOvwSupport#ResourceProceduralGet](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#resourceproceduralget)]  
  
 Un metodo alternativo per l'assegnazione di un riferimento di risorsa è <xref:System.Windows.FrameworkElement.SetResourceReference%2A>. Questo metodo accetta due parametri: la chiave della risorsa e l'identificatore di una particolare proprietà di dipendenza presente nell'istanza dell'elemento a cui deve essere assegnato il valore della risorsa. A livello funzionale, questo metodo è identico al precedente e presenta il vantaggio di non richiedere il cast dei valori restituiti.  
  
 Un altro modo per accedere alle risorse a <xref:System.Windows.FrameworkElement.Resources%2A> livello di codice consiste nell'accedere al contenuto della proprietà come dizionario. L'accesso al dizionario incluso in questa proprietà consente anche di aggiungere nuove risorse alle raccolte esistenti, di verificare se un determinato nome di chiave è già usato nella raccolta e di eseguire altre operazioni sul dizionario o sulla raccolta. Se si scrive [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un'applicazione interamente nel codice, è anche possibile creare l'intera raccolta nel <xref:System.Windows.FrameworkElement.Resources%2A> codice, assegnarvi le chiavi e quindi assegnare la raccolta finita alla proprietà di un elemento stabilito. Questa procedura sarà descritta nella sezione successiva.  
  
 È possibile indicizzare all'interno di una determinata <xref:System.Windows.FrameworkElement.Resources%2A> raccolta, usando una chiave specifica come indice, ma è necessario tenere presente che l'accesso alla risorsa in questo modo non segue le normali regole di runtime della risoluzione delle risorse. Viene eseguito l'accesso solo a quella particolare risorsa. La ricerca della risorsa non attraversa l'ambito fino alla radice o all'applicazione se non è stato trovato alcun oggetto valido in corrispondenza della chiave richiesta. Questo approccio, tuttavia, in alcuni casi può presentare vantaggi in termini di prestazioni, proprio perché l'ambito di ricerca della chiave è più limitato. Vedere <xref:System.Windows.ResourceDictionary> la classe per ulteriori dettagli su come utilizzare direttamente il dizionario risorse.  
  
<a name="creating"></a>
## <a name="creating-resources-with-code"></a>Creazione delle risorse tramite codice  
 Se si vuole creare un'intera applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in codice, può essere necessario creare in codice anche eventuali risorse di tale applicazione. A tale scopo, <xref:System.Windows.ResourceDictionary> creare una nuova istanza e quindi aggiungere tutte <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>le risorse al dizionario utilizzando chiamate successive a . Utilizzare quindi <xref:System.Windows.ResourceDictionary> l'oggetto creato <xref:System.Windows.FrameworkElement.Resources%2A> per impostare la proprietà su un <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>elemento presente in un ambito di pagina o su . È anche possibile <xref:System.Windows.ResourceDictionary> mantenere l'oggetto come oggetto autonomo senza aggiungerlo a un elemento. In questo caso, tuttavia, è necessario accedere alle risorse al suo interno tramite la chiave dell'elemento, come se si trattasse di un dizionario generico. Oggetto <xref:System.Windows.ResourceDictionary> che non è associato `Resources` a una proprietà dell'elemento non esisterebbe come parte della struttura <xref:System.Windows.FrameworkElement.FindResource%2A> ad albero dell'elemento e non ha alcun ambito in una sequenza di ricerca che può essere utilizzata da metodi correlati e da quelli correlati.  
  
<a name="objectaskey"></a>
## <a name="using-objects-as-keys"></a>Uso di oggetti come chiavi  
 La chiave di una risorsa sarà impostata come stringa nella maggior parte degli utilizzi di quella risorsa. Diverse funzionalità di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], tuttavia, non usano un tipo stringa per specificare le chiavi, quel parametro sarà un oggetto. La possibilità di disporre di un oggetto come chiave della risorsa viene usata dal supporto degli stili e dei temi di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Gli stili nei temi che diventano lo stile predefinito per un <xref:System.Type> controllo altrimenti senza stile sono ognuno con chiave dal controllo che devono essere applicati. L'uso di un tipo come chiave offre un meccanismo di ricerca affidabile che funziona sulle istanze predefinite di ogni tipo di controllo, pertanto il tipo può essere rilevato mediante reflection e usato per applicare uno stile alle classi derivate, anche se il tipo derivato non disporrebbe altrimenti di uno stile predefinito. È possibile <xref:System.Type> specificare una chiave [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per una risorsa definita in utilizzando l'estensione [x:Type Markup](../../../desktop-wpf/xaml-services/xtype-markup-extension.md). Esistono estensioni analoghe per altri utilizzi di chiavi di tipo non stringa che supportano funzionalità di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], come l'[estensione di markup ComponentResourceKey](componentresourcekey-markup-extension.md).  
  
## <a name="see-also"></a>Vedere anche

- [Risorse XAML](xaml-resources.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
