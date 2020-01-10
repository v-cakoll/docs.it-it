---
title: Memorizzazione nella cache dei client di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation caching in clients
- caching, UI Automation clients
ms.assetid: 94c15031-4975-43cc-bcd5-c9439ed21c9c
ms.openlocfilehash: 5c0c92f40ae60785f780cb573bb7faa77a31f273
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741787"
---
# <a name="caching-in-ui-automation-clients"></a>Memorizzazione nella cache dei client di automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 Questo argomento presenta la memorizzazione nella cache delle proprietà [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] e dei pattern di controllo.  
  
 In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]la memorizzazione nella cache corrisponde al recupero preliminare dei dati. I dati diventano quindi accessibili senza un'ulteriore comunicazione tra processi. La memorizzazione nella cache in genere viene usata dalle applicazioni client di automazione interfaccia utente per recuperare in massa proprietà e pattern di controllo. Le informazioni vengono quindi recuperate dalla cache in base alle necessità. L'applicazione aggiorna periodicamente la cache, in genere come risposta a eventi indicanti che è cambiato qualcosa nell' [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] .  
  
 I vantaggi della memorizzazione nella cache sono molto evidenti con i controlli Windows Presentation Foundation (WPF) e i controlli personalizzati con provider di automazione interfaccia utente lato server. Il vantaggio è minore quando si accede ai provider lato client, ad esempio i provider predefiniti per i controlli Win32.  
  
 La memorizzazione nella cache si verifica quando l'applicazione attiva un elemento <xref:System.Windows.Automation.CacheRequest> e quindi usa un metodo o una proprietà che restituisce un elemento <xref:System.Windows.Automation.AutomationElement>, ad esempio <xref:System.Windows.Automation.AutomationElement.FindFirst%2A>, <xref:System.Windows.Automation.AutomationElement.FindAll%2A>. I metodi della classe <xref:System.Windows.Automation.TreeWalker> sono un'eccezione. La memorizzazione nella cache viene eseguita solo se un elemento <xref:System.Windows.Automation.CacheRequest> viene specificato come parametro (ad esempio, <xref:System.Windows.Automation.TreeWalker.GetFirstChild%28System.Windows.Automation.AutomationElement%2CSystem.Windows.Automation.CacheRequest%29?displayProperty=nameWithType>.  
  
 La memorizzazione nella cache viene eseguita anche quando si sottoscrive un evento mentre è attivo un elemento <xref:System.Windows.Automation.CacheRequest> . L'elemento <xref:System.Windows.Automation.AutomationElement> passato al gestore eventi come origine di un evento contiene le proprietà e i pattern memorizzati nella cache specificati dall'elemento <xref:System.Windows.Automation.CacheRequest>originale. Eventuali modifiche apportate all'elemento <xref:System.Windows.Automation.CacheRequest> dopo la sottoscrizione dell'evento non vengono applicate.  
  
 Le proprietà e i pattern di controllo di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] di un elemento possono essere memorizzati nella cache.  
  
<a name="Options_for_Caching"></a>   
## <a name="options-for-caching"></a>Opzioni per la memorizzazione nella cache  
 <xref:System.Windows.Automation.CacheRequest> specifica le opzioni seguenti per la memorizzazione nella cache.  
  
<a name="Properties_to_Cache"></a>   
### <a name="properties-to-cache"></a>Proprietà da memorizzare nella cache  
 È possibile specificare le proprietà da memorizzare nella cache chiamando <xref:System.Windows.Automation.CacheRequest.Add%28System.Windows.Automation.AutomationProperty%29> per ogni proprietà prima di attivare la richiesta.  
  
<a name="Control_Patterns_to_Cache"></a>   
### <a name="control-patterns-to-cache"></a>Pattern di controllo da memorizzare nella cache  
 È possibile specificare i pattern di controllo da memorizzare nella cache chiamando <xref:System.Windows.Automation.CacheRequest.Add%28System.Windows.Automation.AutomationPattern%29> per ogni pattern prima di attivare la richiesta. Quando un pattern viene memorizzato nella cache, non vengono automaticamente memorizzate anche le proprietà. È necessario specificare le proprietà che si vuole memorizzare nella cache usando <xref:System.Windows.Automation.CacheRequest.Add%2A?displayProperty=nameWithType>.  
  
<a name="Scope_of_the_Caching"></a>   
### <a name="scope-and-filtering-of-caching"></a>Ambito e applicazione di filtri per la memorizzazione nella cache  
 È possibile specificare gli elementi di cui si vuole memorizzare nella cache le proprietà e i pattern impostando la proprietà <xref:System.Windows.Automation.CacheRequest.TreeScope%2A?displayProperty=nameWithType> prima di attivare la richiesta. L'ambito è relativo agli elementi recuperati mentre la richiesta è attiva. Se, ad esempio, si imposta solo <xref:System.Windows.Automation.TreeScope.Children>e quindi si recupera <xref:System.Windows.Automation.AutomationElement>, le proprietà e i pattern dei figli di tale elemento vengono memorizzati nella cache, ma non quelli dell'elemento stesso. Per assicurarsi che la memorizzazione nella cache venga eseguita proprio per l'elemento recuperato, è necessario includere <xref:System.Windows.Automation.TreeScope.Element> nella proprietà <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> . Non è possibile impostare l'ambito su <xref:System.Windows.Automation.TreeScope.Parent> o <xref:System.Windows.Automation.TreeScope.Ancestors>. Un elemento padre, tuttavia, può essere memorizzato nella cache quando un elemento figlio viene memorizzato nella cache. Vedere Recupero di elementi figlio e padre memorizzati nella cache.  
  
 L'ambito della memorizzazione nella cache è interessato anche dalla proprietà <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A?displayProperty=nameWithType> . Per impostazione predefinita, la memorizzazione nella cache viene eseguita solo per gli elementi presenti nella visualizzazione controllo dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . È possibile, tuttavia, modificare questa proprietà per poter applicare la memorizzazione nella cache a tutti gli elementi o solo agli elementi presenti nella visualizzazione contenuto.  
  
<a name="Strength_of_the_Element_References"></a>   
### <a name="strength-of-the-element-references"></a>Efficacia dei riferimenti a un elemento  
 Quando si recupera un oggetto <xref:System.Windows.Automation.AutomationElement>, per impostazione predefinita si ha accesso a tutte le proprietà e i pattern di tale elemento, inclusi quelli non memorizzati nella cache. Per una maggiore efficienza, tuttavia, è possibile specificare che il riferimento all'elemento si riferisce solo ai dati memorizzati nella cache, impostando la proprietà <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> di <xref:System.Windows.Automation.CacheRequest> su <xref:System.Windows.Automation.AutomationElementMode.None>. In questo caso, non si ha accesso a tutte le proprietà e i pattern non memorizzati nella cache degli elementi recuperati. Non è quindi possibile accedere alle proprietà con <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> o con la proprietà `Current` di <xref:System.Windows.Automation.AutomationElement> o di un pattern di controllo né è possibile recuperare un pattern usando <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> o <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>. Per i pattern memorizzati nella cache è possibile chiamare metodi che recuperano proprietà di matrici, ad esempio <xref:System.Windows.Automation.SelectionPattern.SelectionPatternInformation.GetSelection%2A?displayProperty=nameWithType>, ma nessuno che esegue azioni sul controllo, ad esempio <xref:System.Windows.Automation.InvokePattern.Invoke%2A?displayProperty=nameWithType>.  
  
 Un esempio di applicazione che non necessariamente ha bisogno di riferimenti completi agli oggetti è un'utilità per la lettura dello schermo, che esegue una prelettura delle proprietà <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A> e <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> degli elementi di una finestra, ma non richiede gli oggetti <xref:System.Windows.Automation.AutomationElement> stessi.  
  
<a name="Activating_the_CacheRequest"></a>   
## <a name="activating-the-cacherequest"></a>Attivazione di CacheRequest  
 La memorizzazione nella cache viene eseguita solo quando gli oggetti <xref:System.Windows.Automation.AutomationElement> vengono recuperati mentre un oggetto <xref:System.Windows.Automation.CacheRequest> è attivo per il thread corrente. Esistono due diverse modi per attivare un oggetto <xref:System.Windows.Automation.CacheRequest>.  
  
 Il modo consueto consiste nel chiamare <xref:System.Windows.Automation.CacheRequest.Activate%2A>. Questo metodo restituisce un oggetto che implementa <xref:System.IDisposable>. La richiesta rimane attiva finché esiste l'oggetto <xref:System.IDisposable> . Il modo più semplice per controllare la durata dell'oggetto consiste nel racchiudere la chiamata all'interno di unC#blocco `using` () o `Using` (Visual Basic). In questo modo la richiesta verrà sicuramente estratta dallo stack anche se verrà generata un'eccezione.  
  
 Un altro modo, utile quando si vuole annidare le richieste della cache, consiste nel chiamare <xref:System.Windows.Automation.CacheRequest.Push%2A>, che inserisce la richiesta in uno stack e la attiva. La richiesta rimane attiva finché viene rimossa dallo stack da <xref:System.Windows.Automation.CacheRequest.Pop%2A>. La richiesta diventa temporaneamente inattiva se viene effettuato il push di un'altra richiesta nello stack. Solo la richiesta principale dello stack è attiva.  
  
<a name="Retrieving_Cached_Properties"></a>   
## <a name="retrieving-cached-properties"></a>Recupero di proprietà memorizzate nella cache  
 È possibile recuperare le proprietà memorizzate nella cache di un elemento con i metodi e le proprietà seguenti.  
  
- <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.Cached%2A>  
  
 Se la proprietà richiesta non è nella cache, viene generata un'eccezione.  
  
 <xref:System.Windows.Automation.AutomationElement.Cached%2A>, come <xref:System.Windows.Automation.AutomationElement.Current%2A>, espone le singole proprietà come membri di una struttura che tuttavia non è necessario recuperare perché è possibile accedere direttamente alle singole proprietà. La proprietà <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A> , ad esempio, può essere ottenuta da `element.Cached.Name`, dove `element` è un oggetto <xref:System.Windows.Automation.AutomationElement>.  
  
<a name="Retrieving_Cached_Control_Patterns"></a>   
## <a name="retrieving-cached-control-patterns"></a>Recupero di pattern di controllo memorizzati nella cache  
 È possibile recuperare i pattern di controllo memorizzati nella cache di un elemento con i metodi seguenti.  
  
- <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A>  
  
 Se il pattern non è nella cache, <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> genera un'eccezione e <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> restituisce `false`.  
  
 È possibile recuperare le proprietà memorizzate nella cache di un pattern di controllo usando la proprietà `Cached` dell'oggetto pattern. È anche possibile recuperare i valori correnti con la proprietà `Current` , ma solo se non è stato specificato <xref:System.Windows.Automation.AutomationElementMode.None> quando è stato recuperato l'oggetto <xref:System.Windows.Automation.AutomationElement> . <xref:System.Windows.Automation.AutomationElementMode.Full> è il valore predefinito, che consente l'accesso ai valori correnti.  
  
<a name="Retrieving_Cached_Children_and_Parents"></a>   
## <a name="retrieving-cached-children-and-parents"></a>Recupero di elementi figlio e padre memorizzati nella cache  
 Quando si recupera un oggetto <xref:System.Windows.Automation.AutomationElement> e si richiede la memorizzazione nella cache per i figli di tale elemento con la proprietà <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> della richiesta, successivamente è possibile ottenere gli elementi figlio dalla proprietà <xref:System.Windows.Automation.AutomationElement.CachedChildren%2A> dell'elemento recuperato.  
  
 Se <xref:System.Windows.Automation.TreeScope.Element> è stato incluso nell'ambito della richiesta della cache, l'elemento radice della richiesta è successivamente disponibile nella proprietà <xref:System.Windows.Automation.AutomationElement.CachedParent%2A> di qualsiasi elemento figlio.  
  
> [!NOTE]
> Non è possibile memorizzare nella cache elementi padre o predecessori dell'elemento radice della richiesta.  
  
<a name="Updating_the_Cache"></a>   
## <a name="updating-the-cache"></a>Aggiornamento della cache  
 La cache è valida solo finché non vengono apportate modifiche all' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. L'applicazione è responsabile dell'aggiornamento della cache, di solito come risposta a un evento.  
  
 Se si sottoscrive un evento mentre è attivo un oggetto <xref:System.Windows.Automation.CacheRequest> , si ottiene un <xref:System.Windows.Automation.AutomationElement> con una cache aggiornata come origine dell'evento quando viene chiamato il delegato del gestore eventi. È anche possibile aggiornare le informazioni memorizzate nella cache per un elemento chiamando <xref:System.Windows.Automation.AutomationElement.GetUpdatedCache%2A>. È possibile passare l'oggetto <xref:System.Windows.Automation.CacheRequest> originale per aggiornare tutte le informazioni memorizzate in precedenza nella cache.  
  
 L'aggiornamento della cache non modifica le proprietà dei riferimenti a <xref:System.Windows.Automation.AutomationElement> esistenti.  
  
## <a name="see-also"></a>Vedere anche

- [Eventi di automazione interfaccia utente per i client](ui-automation-events-for-clients.md)
- [Usare la memorizzazione nella cache in automazione interfaccia utente](use-caching-in-ui-automation.md)
- [Esempio FetchTimer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771456(v=vs.90))
