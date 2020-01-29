---
title: Tipi di modifiche di rilievo-.NET Core
description: Informazioni sul modo in cui .NET Core tenta di mantenere la compatibilità per gli sviluppatori tra le versioni di .NET e il tipo di modifica che viene considerata una modifica di rilievo.
ms.date: 06/10/2019
ms.openlocfilehash: 76d04504c4476f0f7517a633cfbf1c0aa9d5797e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738580"
---
# <a name="changes-that-affect-compatibility"></a>Modifiche che influiscono sulla compatibilità

Nel corso del tempo, .NET ha tentato di mantenere un elevato livello di compatibilità tra le diverse versioni. Questo è vero anche per .NET Core. Anche se la tecnologia .NET Core può essere considerata indipendente da .NET Framework, due fattori principali limitano la possibilità di .NET Core di discostarsi da .NET Framework:

- Numerosi sviluppatori hanno originariamente sviluppato o continuano a sviluppare applicazioni .NET Framework e si aspettano un comportamento coerente in tutte le implementazioni di .NET.

- I progetti di libreria .NET Standard consentono agli sviluppatori di creare librerie per API comuni condivise da .NET Core e .NET Framework. Gli sviluppatori si aspettano che una libreria usata in un'applicazione .NET Core debba comportarsi in modo identico alla stessa libreria usata in un'applicazione .NET Framework.

Oltre alla compatibilità tra le implementazioni di .NET, gli sviluppatori si aspettano un elevato livello di compatibilità tra le versioni di .NET Core. In particolare, il codice scritto per una versione precedente di .NET Core dovrebbe essere eseguito senza problemi in una versione successiva di .NET Core. In realtà, molti gli sviluppatori si aspettano che le nuove API incluse nelle nuove versioni rilasciate di .NET Core siano compatibili anche con le versioni non definitive in cui sono state introdotte le API.

Questo articolo descrive le categorie di modifiche di compatibilità (o che causano un'interruzione) e il modo in cui le modifiche di ogni categoria vengono valutate dal team di .NET. Conoscere il modo in cui il team .NET si avvicina alle possibili modifiche di rilievo è particolarmente utile per gli sviluppatori che aprono le richieste pull nel repository GitHub [DotNet/Runtime](https://github.com/dotnet/runtime) che modificano il comportamento delle API esistenti.

> [!NOTE]
> Per una definizione delle categorie di compatibilità, come la compatibilità a livello di codice binario e la compatibilità con le versioni precedenti, vedere [Categorie di modifiche che causano un'interruzione](categories.md).

Le sezioni seguenti descrivono le categorie di modifiche apportate alle API .NET Core e il loro effetto sulla compatibilità delle applicazioni. Le modifiche sono consentite ✔️, non sono consentite ❌o richiedono una valutazione e una valutazione del comportamento prevedibile, ovvio e coerente del precedente ❓.

> [!NOTE]
> Oltre a servire da guida per la valutazione delle modifiche alle librerie di .NET Core, questi criteri possono essere usati dagli sviluppatori di librerie per valutare le modifiche alle librerie destinate a più versioni e implementazioni di .NET.

## <a name="modifications-to-the-public-contract"></a>Modifiche al contratto pubblico

Le modifiche apportate a questa categoria modificano la superficie di attacco pubblica di un tipo. La maggior parte delle modifiche incluse in questa categoria non è consentita perché viola la *compatibilità con le versioni precedenti*, ovvero la capacità di un'applicazione sviluppata con una versione precedente di un'API di essere eseguita senza ricompilazione in una versione successiva.

### <a name="types"></a>Tipi

- ✔️ **consentito: rimozione di un'implementazione dell'interfaccia da un tipo quando l'interfaccia è già implementata da un tipo di base**

- ❓ **Richiede un giudizio: aggiunta di una nuova implementazione dell'interfaccia a un tipo**

  Questa è una modifica accettabile perché non ha effetti negativi sui client esistenti. Affinché la nuova implementazione rimanga accettabile, le modifiche al tipo devono rimanere entro i limiti delle modifiche accettabili definite di seguito. È necessario prestare particolare attenzione quando si aggiungono interfacce che influiscono direttamente sulla capacità di una finestra di progettazione o un serializzatore di generare codice o dati che non possono essere utilizzati nelle versioni precedenti. Un esempio è costituito dall'interfaccia <xref:System.Runtime.Serialization.ISerializable>.

- ❓ È **necessario giudicare: Introduzione a una nuova classe di base**

  Un tipo può essere introdotto in una gerarchia tra due tipi esistenti se non introduce nuovi membri [astratti](../../csharp/language-reference/keywords/abstract.md) o modifica la semantica o il comportamento dei tipi esistenti. Ad esempio, in .NET Framework 2.0, la classe <xref:System.Data.Common.DbConnection> è diventata una nuova classe di base per <xref:System.Data.SqlClient.SqlConnection>, che in precedenza derivava direttamente da <xref:System.ComponentModel.Component>.

- ✔️ **consentito: trasferimento di un tipo da un assembly a un altro**

  L'assembly *precedente* deve essere contrassegnato con la <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> che punta al nuovo assembly.

- ✔️ **consentito: modifica di un tipo [struct](../../csharp/language-reference/keywords/struct.md) in un tipo di `readonly struct`**

  La modifica di un tipo di `readonly struct` in un tipo di `struct` non è consentita.

- ✔️ **consentito: aggiunta della parola chiave [sealed](../../csharp/language-reference/keywords/sealed.md) o [abstract](../../csharp/language-reference/keywords/abstract.md) a un tipo quando non sono presenti costruttori *accessibili* (pubblici o protetti)**

- ✔️ **consentito: espansione della visibilità di un tipo**

- ❌ non **consentito: modifica dello spazio dei nomi o del nome di un tipo**

- ❌ non **consentito: ridenominazione o rimozione di un tipo pubblico**

   Questa operazione causa l'interruzione di tutto il codice che usa il tipo rinominato o rimosso.

- ❌ non **consentito: modifica del tipo sottostante di un'enumerazione**

   Si tratta di una modifica che causa un'interruzione a livello di compilazione, comportamento e codice binario che può rendere non analizzabili gli argomenti degli attributi.

- ❌ non **consentito: sealing di un tipo precedentemente non sealed**

- ❌ non **consentito: aggiunta di un'interfaccia al set di tipi di base di un'interfaccia**

   Se un'interfaccia implementa un'interfaccia che in precedenza non implementava, tutti i tipi che implementavano la versione originale dell'interfaccia vengono interrotti.

- ❓ **Richiede il giudizio: rimozione di una classe dal set di classi di base o di un'interfaccia dal set di interfacce implementate**

  Esiste un'unica eccezione alla regola per la rimozione di un'interfaccia. È possibile aggiungere l'implementazione di un'interfaccia che deriva dall'interfaccia rimossa. È ad esempio possibile rimuovere <xref:System.IDisposable> se il tipo o l'interfaccia implementa ora <xref:System.ComponentModel.IComponent>, che implementa a sua volta l'interfaccia <xref:System.IDisposable>.

- ❌ non **consentito: modifica di un tipo di `readonly struct` in un tipo [struct](../../csharp/language-reference/keywords/struct.md)**

  Tuttavia, è consentita la modifica di un tipo di `struct` in un tipo di `readonly struct`.

- ❌ non **consentito: modifica di un tipo [struct](../../csharp/language-reference/keywords/struct.md) in un tipo di `ref struct` e** viceversa

- ❌ non **consentito: riduzione della visibilità di un tipo**

   L'espansione della visibilità di un tipo è tuttavia consentita.

### <a name="members"></a>Membri

- ✔️ **consentito: espansione della visibilità di un membro che non è [virtuale](../../csharp/language-reference/keywords/sealed.md)**

- ✔️ **consentito: aggiunta di un membro astratto a un tipo pubblico senza costruttori *accessibili* (pubblici o protetti) oppure il tipo è [sealed](../../csharp/language-reference/keywords/sealed.md)**

  Non è tuttavia consentita l'aggiunta di un membro astratto a un tipo pubblico che ha costruttori accessibili (pubblici o protetti) e che non è `sealed`.

- ✔️ **consentito: limitazione della visibilità di un membro [protetto](../../csharp/language-reference/keywords/protected.md) quando il tipo non dispone di costruttori accessibili (pubblici o protetti) oppure il tipo è [sealed](../../csharp/language-reference/keywords/sealed.md)**

- ✔️ **consentito: lo stato di un membro viene spostato in una classe superiore nella gerarchia rispetto al tipo da cui è stato rimosso**

- ✔️ **consentito: aggiunta o rimozione di una sostituzione**

  L'introduzione di una sostituzione può causare l'omissione da parte dei consumer precedenti dell'override durante la chiamata di [base](../../csharp/language-reference/keywords/base.md).

- ✔️ **consentita: aggiunta di un costruttore a una classe, insieme a un costruttore senza parametri se la classe non ha in precedenza costruttori**

   Non è tuttavia consentita l'aggiunta di un costruttore a una classe che in precedenza era priva di costruttori *senza* aggiungere il costruttore senza parametri.

- ✔️ **consentito: modifica di un membro da [abstract](../../csharp/language-reference/keywords/abstract.md) a [Virtual](../../csharp/language-reference/keywords/virtual.md)**

- ✔️ **consentito: modifica da un `ref readonly` a un valore restituito `ref` (ad eccezione di metodi o interfacce virtuali)**

- ✔️ **consentito: rimozione di [ReadOnly](../../csharp/language-reference/keywords/readonly.md) da un campo, a meno che il tipo statico del campo non sia un tipo di valore modificabile**

- ✔️ **consentito: chiamata a un nuovo evento che non è stato definito in precedenza**

- ❓ È **necessario giudicare: aggiunta di un nuovo campo di istanza a un tipo**

   Questa modifica ha impatto sulla serializzazione.

- ❌ non **consentito: ridenominazione o rimozione di un membro o un parametro pubblico**

   Questa operazione causa l'interruzione di tutto il codice che usa il parametro o il membro rinominato o rimosso.

   Ciò include la rimozione o la ridenominazione di un getter o un setter da una proprietà, nonché la ridenominazione o la rimozione dei membri dell'enumerazione.

- ❌ non **consentito: aggiunta di un membro a un'interfaccia**

- ❌ non **consentito: modifica del valore di una costante pubblica o di un membro di enumerazione**

- ❌ non **consentito: modifica del tipo di una proprietà, un campo, un parametro o un valore restituito**

- ❌ non **consentito: aggiunta, rimozione o modifica dell'ordine dei parametri**

- ❌ non **consentito: aggiunta o rimozione della parola chiave [in](../../csharp/language-reference/keywords/in.md), [out](../../csharp/language-reference/keywords/out.md) o [ref](../../csharp/language-reference/keywords/ref.md) da un parametro**

- ❌ non **consentito: ridenominazione di un parametro (inclusa la modifica del case)**

  Questa viene considerata una modifica che causa un'interruzione per due motivi:

  - Interrompe gli scenari con associazione tardiva, ad esempio la funzionalità di associazione tardiva in Visual Basic e [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) in C#.

  - Interrompe la [compatibilità a livello di codice sorgente](categories.md#source-compatibility) quando gli sviluppatori usano [argomenti denominati](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments).

- ❌ non **consentito: modifica da un valore restituito `ref` a un valore restituito `ref readonly`**

- ❌️ non **consentito: passaggio da un `ref readonly` a un `ref` valore restituito su un metodo o un'interfaccia virtuale**

- ❌ non **consentito: aggiunta o rimozione di un oggetto [abstract](../../csharp/language-reference/keywords/abstract.md) da un membro**

- ❌ non **consentito: rimozione della parola chiave [Virtual](../../csharp/language-reference/keywords/virtual.md) da un membro**

  Anche se spesso questa non è una modifica che causa un'interruzione perché il compilatore C# tende a generare istruzioni [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) in linguaggio intermedio (IL) per chiamare metodi non virtuali (diversamente da una normale chiamata, `callvirt` esegue un controllo null), questo comportamento non è invariabile per diversi motivi:
  - C# non è l'unico linguaggio di destinazione di .NET.

  - Il compilatore C# tenta sempre più di ottimizzare `callvirt` in una normale chiamata ogni volta che il metodo di destinazione non è virtuale e presumibilmente non è null (ad esempio quando si accede a un metodo tramite l'[operatore di propagazione null ?.](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-)).

  Quando un metodo viene impostato come virtuale, spesso il codice consumer finisce per chiamarlo in modo non virtuale.

- ❌ non **consentito: aggiunta della parola chiave [Virtual](../../csharp/language-reference/keywords/virtual.md) a un membro**

- ❌ non **consentito: creazione di un membro virtuale abstract**

  Un [membro virtuale](../../csharp/language-reference/keywords/virtual.md) fornisce un'implementazione di metodo che *può essere* sottoposta a override da una classe derivata. Un [membro astratto](../../csharp/language-reference/keywords/abstract.md) non fornisce alcuna implementazione e *deve essere* sottoposto a override.

- ❌ **non consentito: aggiunta di un membro astratto a un tipo pubblico con costruttori accessibili (pubblici o protetti) e non [sealed](../../csharp/language-reference/keywords/sealed.md)**

- ❌ non **consentito: aggiunta o rimozione della parola chiave [static](../../csharp/language-reference/keywords/static.md) da un membro**

- ❌ non **consentito: aggiunta di un overload che impedisce un overload esistente e definisce un comportamento diverso**

  Questa modifica causa un'interruzione dei client esistenti associati all'overload precedente. Se, ad esempio, una classe dispone di una singola versione di un metodo che accetta uno struct <xref:System.UInt32>, un consumer esistente viene correttamente associato a tale overload quando viene passato un valore <xref:System.Int32>. Se tuttavia si aggiunge un overload che accetta uno struct <xref:System.Int32>, quando viene eseguita la ricompilazione o viene usata l'associazione tardiva, il compilatore stabilisce l'associazione con il nuovo overload. In caso di comportamento diverso, si tratta di una modifica che causa un'interruzione.

- ❌ **non consentito: aggiunta di un costruttore a una classe che in precedenza non aveva alcun costruttore senza aggiungere il costruttore senza parametri**

- ❌️ non **consentito: aggiunta di [ReadOnly](../../csharp/language-reference/keywords/readonly.md) a un campo**

- ❌ non **consentito: riduzione della visibilità di un membro**

   Ciò include la riduzione della visibilità di un membro [protetto](../../csharp/language-reference/keywords/protected.md) quando sono presenti costruttori *accessibili* (`public` o `protected`) e il tipo *non* è [sealed](../../csharp/language-reference/keywords/sealed.md). Se questo non avviene, la limitazione della visibilità di un membro protetto è consentita.

   L'aumento della visibilità di un membro è consentito.

- ❌ non **consentito: modifica del tipo di un membro**

   Il valore restituito di un metodo o il tipo di una proprietà o di un campo non può essere modificato. Ad esempio, la firma di un metodo che restituisce un tipo <xref:System.Object> non può essere modificata in modo da restituire un tipo <xref:System.String> o viceversa.

- ❌ **non consentito: aggiunta di un campo a uno struct che in precedenza non aveva stato**

  Determinate regole di assegnazione consentono l'uso di variabili non inizializzate, purché il tipo di variabile sia uno struct senza stato. Se lo struct è definito con stato, può verificarsi un problema di mancata inizializzazione dei dati del codice. Si tratta potenzialmente di una modifica che causa un'interruzione a livello di codice sorgente e di codice binario.

- ❌ non **consentito: generazione di un evento esistente quando non è mai stato generato prima**

## <a name="behavioral-changes"></a>Modifiche del comportamento

### <a name="assemblies"></a>Assemblies

- ✔️ **consentito: creazione di un assembly portabile quando le stesse piattaforme sono ancora supportate**

- ❌ non **consentito: modifica del nome di un assembly**
- ❌ non **consentito: modifica della chiave pubblica di un assembly**

### <a name="properties-fields-parameters-and-return-values"></a>Proprietà, campi, parametri e valori restituiti

- ✔️ **consentito: modifica del valore di una proprietà, un campo, un valore restituito o un parametro [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) in un tipo più derivato**

  Ad esempio, un metodo che restituisce un tipo <xref:System.Object> può restituire un'istanza di <xref:System.String>. Non è tuttavia possibile modificare la firma del metodo.

- ✔️ **consentito: aumento dell'intervallo di valori accettati per una proprietà o un parametro se il membro non è [virtuale](../../csharp/language-reference/keywords/virtual.md)**

  Mentre l'intervallo di valori che possono essere passati al metodo o restituiti dal membro può espandersi, il tipo del parametro o del membro non può essere. Ad esempio, i valori passati a un metodo possono aumentare da 0-124 a 0-255, ma il tipo di parametro non può cambiare da <xref:System.Byte> a <xref:System.Int32>.

- ❌ non **consentito: aumento dell'intervallo di valori accettati per una proprietà o un parametro se il membro è [virtuale](../../csharp/language-reference/keywords/virtual.md)**

   Questa modifica interrompe i membri sottoposti a override esistenti, che non funzioneranno correttamente per l'intervallo di valori esteso.

- ❌ non **consentito: riduzione dell'intervallo di valori accettati per una proprietà o un parametro**

- ❌ non **consentito: aumento dell'intervallo di valori restituiti per una proprietà, un campo, un valore restituito o un parametro [out](../../csharp/language-reference/keywords/out-parameter-modifier.md)**

- ❌ non **consentito: modifica dei valori restituiti per una proprietà, un campo, un valore restituito del metodo o un parametro [out](../../csharp/language-reference/keywords/out-parameter-modifier.md)**

- ❌ non **consentito: modifica del valore predefinito di una proprietà, un campo o un parametro**

- ❌ non **consentito: modifica della precisione di un valore restituito numerico**

- ❓ **Richiede il giudizio: una modifica nell'analisi dell'input e la generazione di nuove eccezioni (anche se il comportamento di analisi non è specificato nella documentazione**

### <a name="exceptions"></a>Eccezioni

- ✔️ **consentita: generazione di un'eccezione più derivata rispetto a un'eccezione esistente**

  Poiché la nuova eccezione è una sottoclasse di un'eccezione esistente, il codice che gestisce l'eccezione precedente continua a gestire quella nuova. In .NET Framework 4, ad esempio, i metodi per la creazione e il recupero delle impostazioni cultura hanno iniziato a generare <xref:System.Globalization.CultureNotFoundException> anziché <xref:System.ArgumentException> in caso di impossibilità di trovare le impostazioni cultura. Poiché <xref:System.Globalization.CultureNotFoundException> deriva da <xref:System.ArgumentException>, questa è una modifica accettabile.

- ✔️ **consentito: generazione di un'eccezione più specifica rispetto a <xref:System.NotSupportedException>, <xref:System.NotImplementedException><xref:System.NullReferenceException>**

- ✔️ **consentita: generazione di un'eccezione considerata irreversibile**

  Le eccezioni irreversibili non devono essere intercettate, ma devono essere gestite da un gestore catch-all di alto livello. Non è quindi previsto che gli utenti abbiano codice che intercetta queste eccezioni esplicite. Le eccezioni irreversibili comprendono:

  - <xref:System.AccessViolationException>
  - <xref:System.ExecutionEngineException>
  - <xref:System.Runtime.InteropServices.SEHException>
  - <xref:System.StackOverflowException>

- ✔️ **consentito: generazione di una nuova eccezione in un nuovo percorso di codice**

  L'eccezione deve essere applicata solo a un nuovo percorso di codice che viene eseguito con nuovi valori di parametro o stato e che non può essere eseguito da codice esistente destinato alla versione precedente.

- ✔️ **consentito: rimozione di un'eccezione per consentire un comportamento più affidabile o nuovi scenari**

  Ad esempio, un metodo `Divide` che in precedenza gestiva solo valori positivi, generando un'eccezione <xref:System.ArgumentOutOfRangeException> negli altri casi, può essere modificato in modo da supportare valori negativi e positivi senza generare un'eccezione.

- ✔️ **consentito: modifica del testo di un messaggio di errore**

  Gli sviluppatori non devono basarsi sul testo dei messaggi di errore, che cambiano anche in base alle impostazioni cultura dell'utente.

- ❌ **non consentito: generazione di un'eccezione in qualsiasi altro caso non elencato sopra**

- ❌ **non consentito: rimozione di un'eccezione in altri casi non elencati in precedenza**

### <a name="attributes"></a>Attributi

- ✔️ **consentito: modifica del valore di un attributo *non* osservabile**

- ❌ non **consentito: modifica del valore di un attributo osservabile**

- ❓ **Richiede il giudizio: rimozione di un attributo**

  Nella maggior parte dei casi, la rimozione di un attributo (ad esempio <xref:System.NonSerializedAttribute>) è una modifica che causa un'interruzione.

## <a name="platform-support"></a>Supporto per piattaforme

- ✔️ **consentito: supporto di un'operazione in una piattaforma non supportata in precedenza**

- ❌ **non consentito: non supporta o ora richiede un Service Pack specifico per un'operazione precedentemente supportata in una piattaforma**

## <a name="internal-implementation-changes"></a>Modifiche all'implementazione interna

- ❓ **Richiede il giudizio: modifica della superficie di attacco di un tipo interno**

   Queste modifiche sono in genere consentite, anche se interrompono la reflection privata. È tuttavia possibile che in alcuni casi non lo siano, ad esempio quando le librerie di terze parti più diffuse o numerosi sviluppatori dipendono dalle API interne.

- ❓ È **necessario giudicare: modifica dell'implementazione interna di un membro**

  Queste modifiche sono in genere consentite, anche se interrompono la reflection privata. È tuttavia possibile che in alcuni casi non lo siano, ad esempio quando il codice cliente dipende spesso dalla reflection privata o la modifica presenta effetti collaterali imprevisti.

- ✔️ **consentito: miglioramento delle prestazioni di un'operazione**

   La possibilità di modificare le prestazioni di un'operazione è essenziale, ma tali modifiche possono interrompere il codice che si basa la velocità corrente di un'operazione. Questo vale in particolare per il codice che dipende dalla tempistica delle operazioni asincrone. La modifica delle prestazioni non deve avere alcun effetto sull'altro comportamento dell'API in questione. in caso contrario, la modifica verrà interrotta.

- ✔️ **consentito: modificare indirettamente (e spesso negativamente) le prestazioni di un'operazione**

  La modifica in questione è accettabile se non è classificata per altri motivi come modifica che causa un'interruzione. È spesso necessario eseguire azioni che includono operazioni supplementari o che aggiungono nuove funzionalità. Questo ha quasi sempre effetto sulle prestazioni, ma può essere fondamentale per fare in modo che l'API in questione funzioni come previsto.

- ❌ non **consentito: modifica di un'API sincrona in asincrona (e viceversa)**

## <a name="code-changes"></a>Modifiche al codice

- ✔️ **consentito: aggiunta di [parametri](../../csharp/language-reference/keywords/params.md) a un parametro**

- ❌ non **consentito: modifica di uno [struct](../../csharp/language-reference/keywords/struct.md) in una [classe](../../csharp/language-reference/keywords/class.md) e viceversa**

- ❌ non **consentito: aggiunta della parola chiave [checked](../../csharp/language-reference/keywords/virtual.md) a un blocco di codice**

   Per effetto di questa modifica, il codice eseguito in precedenza può generare un'eccezione <xref:System.OverflowException> e non essere accettabile.

- ❌ non **consentito: rimozione di [params](../../csharp/language-reference/keywords/params.md) da un parametro**

- ❌ non **consentito: modifica dell'ordine in cui vengono generati gli eventi**

  Gli sviluppatori possono ragionevolmente aspettarsi che gli eventi vengano generati nello stesso ordine e il codice degli sviluppatori spesso dipende dall'ordine di generazione degli eventi.

- ❌ non **consentito: rimozione della generazione di un evento in un'azione specificata**

- ❌ non **consentito: la modifica del numero di volte in cui vengono chiamati gli eventi specificati**

- ❌ non **consentito: aggiunta del <xref:System.FlagsAttribute> a un tipo di enumerazione**
