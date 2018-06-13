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
ms.openlocfilehash: 27b72d4be9012caf388c90d52a61d9837713c71f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547547"
---
# <a name="resources-and-code"></a>Risorse e codice
Questo argomento illustra le modalità di accesso alle risorse di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] o di creazione delle risorse stesse tramite codice anziché tramite la sintassi [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Per altre informazioni sull'uso delle risorse in generale e sulle risorse dal punto di vista della sintassi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], vedere [Risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
  
  
<a name="accessing"></a>   
## <a name="accessing-resources-from-code"></a>Accesso alle risorse dal codice  
 Le chiavi che identificano le risorse, se definite tramite [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], possono essere usate anche per recuperare risorse specifiche qualora si richieda la risorsa nel codice. Il modo più semplice per recuperare una risorsa dal codice consiste nel chiamare il <xref:System.Windows.FrameworkElement.FindResource%2A> o <xref:System.Windows.FrameworkElement.TryFindResource%2A> metodo dagli oggetti a livello di framework dell'applicazione. La differenza di comportamento tra i due metodi sta nell'azione eseguita quando la chiave richiesta non viene trovata. <xref:System.Windows.FrameworkElement.FindResource%2A> genera un'eccezione. <xref:System.Windows.FrameworkElement.TryFindResource%2A> non genererà un'eccezione ma restituisce `null`. Ogni metodo accetta la chiave di risorsa come parametro di input e restituisce un oggetto debolmente tipizzato. In genere una chiave di risorsa è una stringa, ma esistono utilizzi occasionali di tipo non stringa. Per informazioni dettagliate, vedere la sezione [Uso di oggetti come chiavi](#objectaskey). Di regola, il cast dell'oggetto restituito viene eseguito nel tipo richiesto dalla proprietà impostata al momento della richiesta della risorsa. La logica di ricerca per la risoluzione della risorsa codice è la stessa del codice [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] del riferimento di risorsa dinamica. La ricerca delle risorse ha inizio dall'elemento chiamante e continua con gli elementi padre successivi dell'albero logico. Prosegue quindi nelle risorse, nei temi e, se necessario, nelle risorse di sistema dell'applicazione. Una richiesta di codice per una risorsa terrà in considerazione le modifiche di runtime eventualmente apportate ai dizionari risorse successivamente al caricamento di un determinato dizionario risorse da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], oltre che le modifiche apportate alle risorse di sistema in tempo reale.  
  
 Di seguito è riportato un breve esempio di codice che consente di trovare una risorsa dalla chiave e utilizza il valore restituito per impostare una proprietà, implementata come un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore dell'evento.  
  
 [!code-csharp[PropertiesOvwSupport#ResourceProceduralGet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#resourceproceduralget)]
 [!code-vb[PropertiesOvwSupport#ResourceProceduralGet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#resourceproceduralget)]  
  
 Un metodo alternativo per l'assegnazione di un riferimento a una risorsa è <xref:System.Windows.FrameworkElement.SetResourceReference%2A>. Questo metodo accetta due parametri: la chiave della risorsa e l'identificatore di una particolare proprietà di dipendenza presente nell'istanza dell'elemento a cui deve essere assegnato il valore della risorsa. A livello funzionale, questo metodo è identico al precedente e presenta il vantaggio di non richiedere il cast dei valori restituiti.  
  
 È ancora un altro modo per accedere alle risorse a livello di codice per accedere al contenuto del <xref:System.Windows.FrameworkElement.Resources%2A> proprietà come un dizionario. L'accesso al dizionario incluso in questa proprietà consente anche di aggiungere nuove risorse alle raccolte esistenti, di verificare se un determinato nome di chiave è già usato nella raccolta e di eseguire altre operazioni sul dizionario o sulla raccolta. Se si sta scrivendo un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione interamente nel codice, è possibile anche creare l'intera raccolta nel codice, assegnare le chiavi e quindi assegnare l'insieme di completato per il <xref:System.Windows.FrameworkElement.Resources%2A> proprietà di un elemento prestabilito. Questa procedura sarà descritta nella sezione successiva.  
  
 È possibile indicizzare all'interno di ogni <xref:System.Windows.FrameworkElement.Resources%2A> raccolta utilizzando una chiave specifica dell'indice, ma è necessario essere consapevoli che l'accesso alla risorsa in questo modo non segue le regole di runtime standard di risoluzione di risorse. Viene eseguito l'accesso solo a quella particolare risorsa. La ricerca della risorsa non attraversa l'ambito fino alla radice o all'applicazione se non è stato trovato alcun oggetto valido in corrispondenza della chiave richiesta. Questo approccio, tuttavia, in alcuni casi può presentare vantaggi in termini di prestazioni, proprio perché l'ambito di ricerca della chiave è più limitato. Vedere la <xref:System.Windows.ResourceDictionary> classe per altri dettagli su come lavorare direttamente con il dizionario risorse.  
  
<a name="creating"></a>   
## <a name="creating-resources-with-code"></a>Creazione delle risorse tramite codice  
 Se si vuole creare un'intera applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in codice, può essere necessario creare in codice anche eventuali risorse di tale applicazione. A tale scopo, creare un nuovo <xref:System.Windows.ResourceDictionary> istanza e quindi aggiungere tutte le risorse al dizionario tramite chiamate successive a <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>. Utilizzare quindi la <xref:System.Windows.ResourceDictionary> così creato per impostare il <xref:System.Windows.FrameworkElement.Resources%2A> proprietà su un elemento che è presente nell'ambito di una pagina o <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>. È inoltre possibile utilizzare il <xref:System.Windows.ResourceDictionary> come oggetto autonomo senza aggiungerlo a un elemento. In questo caso, tuttavia, è necessario accedere alle risorse al suo interno tramite la chiave dell'elemento, come se si trattasse di un dizionario generico. Oggetto <xref:System.Windows.ResourceDictionary> che non è collegato a un elemento `Resources` proprietà non esiste come parte dell'albero dell'elemento e non ha alcun ambito di una sequenza di ricerca che può essere utilizzata da <xref:System.Windows.FrameworkElement.FindResource%2A> e metodi correlati.  
  
<a name="objectaskey"></a>   
## <a name="using-objects-as-keys"></a>Uso di oggetti come chiavi  
 La chiave di una risorsa sarà impostata come stringa nella maggior parte degli utilizzi di quella risorsa. Diverse funzionalità di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], tuttavia, non usano un tipo stringa per specificare le chiavi, quel parametro sarà un oggetto. La possibilità di disporre di un oggetto come chiave della risorsa viene usata dal supporto degli stili e dei temi di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Gli stili dei temi che lo stile predefinito per un controllo in caso contrario non stile ognuno con chiave in base il <xref:System.Type> del controllo da applicare ai. L'uso di un tipo come chiave offre un meccanismo di ricerca affidabile che funziona sulle istanze predefinite di ogni tipo di controllo, pertanto il tipo può essere rilevato mediante reflection e usato per applicare uno stile alle classi derivate, anche se il tipo derivato non disporrebbe altrimenti di uno stile predefinito. È possibile specificare un <xref:System.Type> chiave per una risorsa definita in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] utilizzando il [estensione di Markup X:Type](../../../../docs/framework/xaml-services/x-type-markup-extension.md). Esistono estensioni analoghe per altri utilizzi di chiavi di tipo non stringa che supportano funzionalità di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], come l'[estensione di markup ComponentResourceKey](../../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)
