---
title: Protezione del codice wrapper
description: Esaminare come proteggere il codice wrapper, che può aprire un set univoco di debolezze di sicurezza, soprattutto se il wrapper ha un livello di attendibilità superiore rispetto al codice che lo usa.
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], wrapper code
- wrapper code, securing
- secure coding, wrapper code
- code security, wrapper code
ms.assetid: 1df6c516-5bba-48bd-b450-1070e04b7389
ms.openlocfilehash: 64c5b2455882ca121a6eeb0c0bbcbc4d04ed88cd
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281446"
---
# <a name="securing-wrapper-code"></a>Protezione del codice wrapper
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 Il codice wrapper, soprattutto dove il wrapper ha un'attendibilità più elevata del codice che lo usa, può creare una combinazione univoca di punti di debolezza nella sicurezza. Tutte le operazioni eseguite per conto di un chiamante, in cui le autorizzazioni limitate del chiamante non sono incluse nel controllo di sicurezza appropriato, sono un potenziale punto di debolezza da sfruttare.  
  
 Non abilitare mai tramite il wrapper nulla che il chiamante non possa abilitare manualmente. L'esecuzione di operazioni con un controllo di sicurezza limitato comporta un grave rischio, al contrario di una richiesta di percorso stack completo. Con i controlli dei livelli singoli, se si interpone il codice wrapper tra il vero chiamante e l'elemento API in questione, il controllo di sicurezza potrebbe facilmente avere esito positivo quando non dovrebbe, indebolendo in tal modo la sicurezza.  
  
## <a name="delegates"></a>Delegati  
 La sicurezza dei delegati è diversa a seconda della versione di .NET Framework.  Questa sezione descrive i diversi comportamenti dei delegati e le relative considerazioni sulla sicurezza.  
  
### <a name="in-version-10-and-11-of-the-net-framework"></a>Nelle versioni 1.0 e 1.1 di .NET Framework  
 Le versioni 1.0 e 1.1 di .NET Framework eseguono le seguenti azioni di sicurezza su un creatore del delegato e un chiamante del delegato.  
  
- Quando viene creato un delegato, le richieste di collegamento sicurezza per il metodo destinazione delegato vengono eseguite sul set di concessioni del creatore del delegato.  Se si verifica un errore nell'azione di sicurezza, viene generata un'eccezione <xref:System.Security.SecurityException>.  
  
- Quando il delegato viene richiamato, vengono eseguite le eventuali richieste di sicurezza esistenti per il chiamante del delegato.  
  
 Quando il codice accetta un <xref:System.Delegate> da un codice considerato meno attendibile che potrebbe chiamarlo, assicurarsi di non consentire al codice considerato meno attendibile di eseguire l'escalation delle autorizzazioni. Se si accetta un delegato e lo si usa in un secondo momento, il codice che ha creato il delegato non è nello stack di chiamate e le autorizzazioni non verranno testate se il codice dentro o sotto il delegato tenta di eseguire un'operazione protetta. Se il proprio codice e il codice del chiamante hanno privilegi più elevati di quelli del creatore, il creatore può orchestrare il percorso di chiamate senza far parte dello stack di chiamate.  
  
### <a name="in-version-20-and-later-versions-of-the-net-framework"></a>Nella versione 2,0 e nelle versioni successive del .NET Framework  
 Diversamente dalle versioni precedenti, la versione 2,0 e versioni successive del .NET Framework esegue un'azione di sicurezza sul creatore del delegato quando il delegato viene creato e chiamato.  
  
- Quando viene creato un delegato, le richieste di collegamento sicurezza per il metodo destinazione delegato vengono eseguite sul set di concessioni del creatore del delegato.  Se si verifica un errore nell'azione di sicurezza, viene generata un'eccezione <xref:System.Security.SecurityException>.  
  
- Anche il set di concessioni del creatore del delegato viene acquisito durante la creazione del delegato e archiviato con il delegato.  
  
- Quando il delegato viene richiamato, il set di concessioni acquisito del creatore del delegato viene prima confrontato con eventuali richieste nel contesto corrente se il creatore e il chiamante del delegato appartengono ad assembly diversi.  Vengono poi eseguite eventuali richieste di sicurezza esistenti per il chiamante del delegato.  
  
## <a name="link-demands-and-wrappers"></a>Richieste di collegamento e wrapper  
 Un particolare caso di protezione con richieste di collegamento è stato rafforzato nell'infrastruttura di sicurezza, ma è ancora una possibile fonte di vulnerabilità nel codice.  
  
 Se il codice completamente attendibile chiama una proprietà, un evento o un metodo protetto da un [LinkDemand](link-demands.md), la chiamata ha esito positivo se viene soddisfatta la verifica delle autorizzazioni **LinkDemand** per il chiamante. Inoltre, se il codice completamente attendibile espone una classe che accetta il nome di una proprietà e chiama la relativa funzione di accesso **Get** usando la reflection, la chiamata alla funzione di accesso **Get** riesce anche se il codice utente non ha il diritto di accedere a questa proprietà. Questo è dovuto al fatto che **LinkDemand** controlla solo il chiamante immediato, che è il codice completamente attendibile. In pratica, il codice completamente attendibile effettua una chiamata con privilegi per conto del codice utente senza verificare che il codice utente disponga del diritto per eseguire la chiamata.  
  
 Per evitare tali problemi di sicurezza, il Common Language Runtime estende il controllo in una richiesta di analisi dello stack completa su qualsiasi chiamata indiretta a un metodo, a un costruttore, a una proprietà o a un evento protetto da un **LinkDemand**. Questa protezione comporta costi in termini di prestazioni e richiede modifiche alla semantica del controllo di sicurezza. La richiesta di percorso stack completo potrebbe non riuscire se viene superato il più rapido controllo di un solo livello.  
  
## <a name="assembly-loading-wrappers"></a>Wrapper di caricamento assembly  
 Diversi metodi usati per caricare il codice gestito, tra cui <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>, caricano gli assembly con l'evidenza del chiamante. Se si esegue il wrapping di uno di questi metodi, il sistema di sicurezza potrebbe usare le autorizzazioni del codice, invece delle autorizzazioni del chiamante del wrapper, per caricare gli assembly. Non è consigliabile consentire al codice considerato meno attendibile di caricare codice a cui sono state concesse autorizzazioni più elevate di quelle del chiamante del wrapper.  
  
 In questo modo il codice con attendibilità totale o con un'attendibilità considerevolmente maggiore di quella di un potenziale chiamante (incluso un chiamante con livello di autorizzazioni per Internet) potrebbe indebolire la sicurezza. Se il codice ha un metodo pubblico che accetta una matrice di byte e la passa a **assembly. Load**, creando in tal modo un assembly per conto del chiamante, potrebbe interrompere la protezione.  
  
 Questo problema si verifica con gli elementi API seguenti:  
  
- <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>  
  
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
  
- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>  
  
## <a name="demand-vs-linkdemand"></a>Demand e LinkDemand  
 La sicurezza dichiarativa offre due tipi di controlli di sicurezza che, pur essendo simili, eseguono verifiche molto diverse. È importante conoscerli entrambi perché la scelta sbagliata potrebbe indebolire la sicurezza o provocare una riduzione delle prestazioni.  
  
 La sicurezza dichiarativa offre i controlli di sicurezza seguenti:  
  
- <xref:System.Security.Permissions.SecurityAction.Demand> specifica il percorso di chiamate nello stack di sicurezza dall'accesso al codice. Tutti i chiamanti nello stack devono disporre dell'identità o dell'autorizzazione specificata per poter passare. La **richiesta** si verifica a ogni chiamata perché lo stack potrebbe contenere chiamanti diversi. Se si chiama un metodo più volte, questo controllo di sicurezza viene eseguito ogni volta. La **richiesta** è una protezione efficace contro gli attacchi da attirare; verrà rilevato codice non autorizzato che tenta di ottenerlo.  
  
- [LinkDemand](link-demands.md) si verifica al momento della compilazione JIT (just-in-Time) e controlla solo il chiamante immediato. Questo controllo di sicurezza non verifica il chiamante del chiamante. Una volta passato questo controllo, non ne vengono eseguiti altri, indipendentemente dal numero di chiamate effettuate dal chiamante. Tuttavia, non esiste nemmeno alcuna protezione contro gli attacchi luring. Con **LinkDemand**, qualsiasi codice che supera il test e può fare riferimento al codice può potenzialmente interrompere la sicurezza, consentendo al codice dannoso di chiamare utilizzando il codice autorizzato. Pertanto, non utilizzare **LinkDemand** a meno che non sia possibile evitare tutte le debolezze possibili.  
  
    > [!NOTE]
    > In .NET Framework 4, le richieste di collegamento sono state sostituite dall' <xref:System.Security.SecurityCriticalAttribute> attributo negli <xref:System.Security.SecurityRuleSet.Level2> assembly. <xref:System.Security.SecurityCriticalAttribute>È equivalente a una richiesta di collegamento per l'attendibilità totale; tuttavia, influiscono anche sulle regole di ereditarietà. Per altre informazioni su questa modifica, vedere [codice SecurityTransparent, livello 2](security-transparent-code-level-2.md).  
  
 Le precauzioni aggiuntive necessarie quando si utilizza **LinkDemand** devono essere programmate singolarmente; il sistema di sicurezza può essere utile per l'applicazione. Ogni errore crea un punto di debolezza per la sicurezza. Tutto il codice autorizzato che usa il codice dell'utente deve essere responsabile dell'implementazione di altre misure di sicurezza tramite l'esecuzione delle operazioni seguenti:  
  
- Limitare l'accesso del codice chiamante alla classe o all'assembly.  
  
- Inserire nel codice chiamante gli stessi controlli di sicurezza visualizzati nel codice che viene chiamato e obbligare i chiamanti a fare lo stesso. Se, ad esempio, si scrive codice che chiama un metodo protetto con **LinkDemand** per <xref:System.Security.Permissions.SecurityPermission> con il <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> flag specificato, il metodo deve anche creare un **LinkDemand** (o **Demand**, che è più avanzato) per questa autorizzazione. L'eccezione è rappresentata dal caso in cui il codice utilizzi il metodo protetto da **LinkDemand**in un modo limitato che si decide sia sicuro, dato che altri meccanismi di protezione (ad esempio le richieste) nel codice. In questo caso eccezionale, il chiamante si assume la responsabilità di indebolire la protezione della sicurezza nel codice sottostante.  
  
- Garantire che i chiamanti del codice non possano spingere il codice a chiamare il codice protetto per conto loro. In altre parole, i chiamanti non possono obbligare il codice autorizzato a passare parametri specifici al codice protetto o recuperare i risultati da esso.  
  
### <a name="interfaces-and-link-demands"></a>Interfacce e richieste di collegamento  
 Se un metodo virtuale, una proprietà o un evento con **LinkDemand** esegue l'override di un metodo della classe base, anche il metodo della classe base deve avere lo stesso **LinkDemand** per il metodo sottoposto a override per essere efficace. Per il codice dannoso è possibile eseguire nuovamente il cast al tipo di base e chiamare il metodo della classe base. Si noti inoltre che le richieste di collegamento possono essere aggiunte in modo implicito agli assembly che non dispongono dell'attributo a livello di assembly <xref:System.Security.AllowPartiallyTrustedCallersAttribute>.  
  
 È consigliabile proteggere le implementazioni dei metodi con richieste di collegamento quando anche i metodi di interfaccia dispongono di richieste di collegamento. Tenere presente quanto segue sull'uso di richieste di collegamento con interfacce:  
  
- Se si inserisce un **LinkDemand** su un metodo pubblico di una classe che implementa un metodo di interfaccia, **LinkDemand** non verrà applicato se si esegue il cast all'interfaccia e si chiama il metodo. In questo caso, poiché è stato collegato all'interfaccia, viene rispettato solo l' **LinkDemand** sull'interfaccia.  
  
 Verificare la presenza di problemi di sicurezza negli elementi seguenti:  
  
- Richieste di collegamento esplicite nei metodi di interfaccia. Assicurarsi che le richieste di collegamento offrano la protezione prevista. Determinare se il codice dannoso può usare un cast per evitare le richieste di collegamento, come descritto in precedenza.  
  
- Metodi virtuali con richieste di collegamento applicate.  
  
- Tipi e interfacce implementate. Questi devono usare le richieste di collegamento in modo coerente.  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la generazione di codice sicuro](../../standard/security/secure-coding-guidelines.md)
