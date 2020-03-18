---
title: Tipi di modifiche di rilievo
description: Scopri come .NET Core tenta di mantenere la compatibilità per gli sviluppatori nelle versioni di .NET e il tipo di modifica viene considerato un cambiamento sostanziale.
ms.date: 06/10/2019
ms.openlocfilehash: bf0cc35d69e6bb501640455604a99a1f48962c4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "77628592"
---
# <a name="changes-that-affect-compatibility"></a>Modifiche che influiscono sulla compatibilità

Nel corso del tempo, .NET ha tentato di mantenere un elevato livello di compatibilità tra le diverse versioni. Questo è vero anche per .NET Core. Anche se la tecnologia .NET Core può essere considerata indipendente da .NET Framework, due fattori principali limitano la possibilità di .NET Core di discostarsi da .NET Framework:

- Numerosi sviluppatori hanno originariamente sviluppato o continuano a sviluppare applicazioni .NET Framework e si aspettano un comportamento coerente in tutte le implementazioni di .NET.

- I progetti di libreria .NET Standard consentono agli sviluppatori di creare librerie per API comuni condivise da .NET Core e .NET Framework. Gli sviluppatori si aspettano che una libreria usata in un'applicazione .NET Core debba comportarsi in modo identico alla stessa libreria usata in un'applicazione .NET Framework.

Oltre alla compatibilità tra le implementazioni di .NET, gli sviluppatori si aspettano un elevato livello di compatibilità tra le versioni di .NET Core. In particolare, il codice scritto per una versione precedente di .NET Core dovrebbe essere eseguito senza problemi in una versione successiva di .NET Core. In realtà, molti gli sviluppatori si aspettano che le nuove API incluse nelle nuove versioni rilasciate di .NET Core siano compatibili anche con le versioni non definitive in cui sono state introdotte le API.

Questo articolo descrive le categorie di modifiche di compatibilità (o che causano un'interruzione) e il modo in cui le modifiche di ogni categoria vengono valutate dal team di .NET. Comprendere come il team di .NET si avvicina alle possibili modifiche di rilievo è particolarmente utile per gli sviluppatori che aprono le richieste pull nel repository [GitHub dotnet/runtime](https://github.com/dotnet/runtime) che modificano il comportamento delle API esistenti.

> [!NOTE]
> Per una definizione delle categorie di compatibilità, come la compatibilità a livello di codice binario e la compatibilità con le versioni precedenti, vedere [Categorie di modifiche che causano un'interruzione](categories.md).

Nelle sezioni seguenti vengono descritte le categorie di modifiche apportate alle API .NET Core e il relativo impatto sulla compatibilità delle applicazioni. Le modifiche sono consentite ❌✔️, non sono consentite o richiedono un giudizio e una valutazione di quanto prevedibile, ovvio e coerente sia stato ❓ il comportamento precedente.

> [!NOTE]
> Oltre a servire da guida per la valutazione delle modifiche alle librerie di .NET Core, questi criteri possono essere usati dagli sviluppatori di librerie per valutare le modifiche alle librerie destinate a più versioni e implementazioni di .NET.

## <a name="modifications-to-the-public-contract"></a>Modifiche al contratto pubblico

Le modifiche di questa categoria interessano la superficie di attacco pubblica di un tipo. La maggior parte delle modifiche incluse in questa categoria non è consentita perché viola la *compatibilità con le versioni precedenti*, ovvero la capacità di un'applicazione sviluppata con una versione precedente di un'API di essere eseguita senza ricompilazione in una versione successiva.

### <a name="types"></a>Tipi

- ✔️ **ALLOWED: Rimozione di un'implementazione dell'interfaccia da un tipo quando l'interfaccia è già implementata da un tipo** di base

- ❓ **REQUIRES JUDGMENT: Aggiunta di una nuova implementazione dell'interfaccia a un tipo**

  Questa è una modifica accettabile perché non ha effetti negativi sui client esistenti. Affinché la nuova implementazione rimanga accettabile, le modifiche al tipo devono rimanere entro i limiti delle modifiche accettabili definite di seguito. È necessario prestare particolare attenzione quando si aggiungono interfacce che influiscono direttamente sulla capacità di una finestra di progettazione o un serializzatore di generare codice o dati che non possono essere utilizzati nelle versioni precedenti. Un esempio è costituito dall'interfaccia <xref:System.Runtime.Serialization.ISerializable>.

- ❓ **REQUIRES JUDGMENT: Introduzione di una nuova classe base**

  Un tipo può essere introdotto in una gerarchia tra due tipi esistenti se non introduce nuovi membri [astratti](../../csharp/language-reference/keywords/abstract.md) o modifica la semantica o il comportamento dei tipi esistenti. Ad esempio, in .NET Framework 2.0, la classe <xref:System.Data.Common.DbConnection> è diventata una nuova classe di base per <xref:System.Data.SqlClient.SqlConnection>, che in precedenza derivava direttamente da <xref:System.ComponentModel.Component>.

- ✔️ **ALLOWED: Spostamento di un tipo da un assieme a un altro**

  L'assieme *precedente* deve <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> essere contrassegnato con l'oggetto che punta al nuovo assieme.

- ✔️ **ALLOWED: Modifica di `readonly struct` un tipo [struct](../../csharp/language-reference/builtin-types/struct.md) in un tipo**

  La `readonly struct` modifica di `struct` un tipo in un tipo non è consentita.

- ✔️ **ALLOWED: Aggiunta della parola chiave [sealed](../../csharp/language-reference/keywords/sealed.md) o [abstract](../../csharp/language-reference/keywords/abstract.md) a un tipo quando non sono presenti costruttori *accessibili* (pubblici o protetti)**

- ✔️ **ALLOWED: Ampliare la visibilità di un tipo**

- ❌**DISALLOWED: Modifica dello spazio dei nomi o del nome di un tipo**

- ❌**DISALLOWED: Ridenominazione o rimozione di un tipo pubblico**

   Questa operazione causa l'interruzione di tutto il codice che usa il tipo rinominato o rimosso.

- ❌**DISALLOWED: modifica del tipo sottostante di un'enumerazione**

   Si tratta di una modifica che causa un'interruzione a livello di compilazione, comportamento e codice binario che può rendere non analizzabili gli argomenti degli attributi.

- ❌**DISALLOWED: Sigillare un tipo precedentemente non sigillato**

- ❌**DISALLOWED: Aggiunta di un'interfaccia al set di tipi di base di un'interfaccia**

   Se un'interfaccia implementa un'interfaccia che in precedenza non implementava, tutti i tipi che implementavano la versione originale dell'interfaccia vengono interrotti.

- ❓ **REQUIRES JUDGMENT: Rimozione di una classe dal set di classi base o di un'interfaccia dal set di interfacce implementate**

  Esiste un'unica eccezione alla regola per la rimozione di un'interfaccia. È possibile aggiungere l'implementazione di un'interfaccia che deriva dall'interfaccia rimossa. È ad esempio possibile rimuovere <xref:System.IDisposable> se il tipo o l'interfaccia implementa ora <xref:System.ComponentModel.IComponent>, che implementa a sua volta l'interfaccia <xref:System.IDisposable>.

- ❌**DISALLOWED: Modifica `readonly struct` di un tipo in un tipo [struct](../../csharp/language-reference/builtin-types/struct.md) **

  La modifica `struct` di un `readonly struct` tipo a un tipo è tuttavia consentita.

- ❌**DISALLOWED: Modifica [struct](../../csharp/language-reference/builtin-types/struct.md) di un `ref struct` tipo struct in un tipo e viceversa**

- ❌**DISALLOWED: Riduzione della visibilità di un tipo**

   L'espansione della visibilità di un tipo è tuttavia consentita.

### <a name="members"></a>Members

- ✔️ **ALLOWED: Espansione della visibilità di un membro non [virtuale](../../csharp/language-reference/keywords/sealed.md) **

- ✔️ **ALLOWED: aggiunta di un membro astratto a un tipo pubblico che non dispone di costruttori *accessibili* (pubblici o protetti) o il tipo è [sealed](../../csharp/language-reference/keywords/sealed.md) **

  Non è tuttavia consentita l'aggiunta di un membro astratto a un tipo pubblico che ha costruttori accessibili (pubblici o protetti) e che non è `sealed`.

- ✔️ **ALLOWED: limitazione della visibilità di un membro [protetto](../../csharp/language-reference/keywords/protected.md) quando il tipo non ha costruttori accessibili (pubblici o protetti) o il tipo è [sealed](../../csharp/language-reference/keywords/sealed.md) **

- ✔️ **ALLOWED: Spostamento di un membro in una classe più in alto nella gerarchia rispetto al tipo da cui è stato rimosso**

- ✔️ **ALLOWED: Aggiunta o rimozione di una sostituzione**

  L'introduzione di un override potrebbe causare l'override dei consumer precedenti quando si chiama [in base](../../csharp/language-reference/keywords/base.md).

- ✔️ **ALLOWED: aggiunta di un costruttore a una classe, insieme a un costruttore senza parametri se la classe in precedenza non aveva costruttori**

   Non è tuttavia consentita l'aggiunta di un costruttore a una classe che in precedenza era priva di costruttori *senza* aggiungere il costruttore senza parametri.

- ✔️ **ALLOWED: Modifica di un membro da [astratto](../../csharp/language-reference/keywords/abstract.md) a [virtuale](../../csharp/language-reference/keywords/virtual.md) **

- ✔️ **ALLOWED: passaggio da `ref readonly` un valore a un valore restituito (ad eccezione dei metodi virtuali o delle interfacce)✔️ ALLOWED: Changing from a to a `ref` return value (except for virtual methods or interfaces)**

- ✔️ **ALLOWED: rimozione [readonly](../../csharp/language-reference/keywords/readonly.md) da un campo, a meno che il tipo statico del campo non sia un tipo di valore modificabile**

- ✔️ **ALLOWED: chiamata di un nuovo evento che non è stato definito in precedenza**

- ❓ **REQUIRES JUDGMENT: Aggiunta di un nuovo campo** di istanza a un tipo

   Questa modifica ha impatto sulla serializzazione.

- ❌**DISALLOWED: Ridenominazione o rimozione di un membro o di un parametro pubblico**

   Questa operazione causa l'interruzione di tutto il codice che usa il parametro o il membro rinominato o rimosso.

   Ciò include la rimozione o la ridenominazione di un getter o setter da una proprietà, nonché la ridenominazione o la rimozione di membri di enumerazione.

- ❌**DISALLOWED: Aggiunta di un membro a un'interfaccia**

- ❌**DISALLOWED: modifica del valore di una costante pubblica o** di un membro di enumerazione

- ❌**DISALLOWED: Modifica del tipo di una proprietà, di un campo, di un parametro o** di un valore restituito

- ❌**DISALLOWED: Aggiunta, rimozione o modifica dell'ordine dei parametri**

- ❌**DISALLOWED: Aggiunta o rimozione della parola chiave [in](../../csharp/language-reference/keywords/in.md), [out](../../csharp/language-reference/keywords/out.md) o [ref](../../csharp/language-reference/keywords/ref.md) da un parametro**

- ❌**DISALLOWED: Ridenominazione di un parametro (inclusa la modifica della distinzione tra maiuscole e minuscole)**

  Questa viene considerata una modifica che causa un'interruzione per due motivi:

  - Interrompe gli scenari con associazione tardiva, ad esempio la funzionalità di associazione tardiva in Visual Basic e [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) in C#.

  - Interrompe la [compatibilità a livello di codice sorgente](categories.md#source-compatibility) quando gli sviluppatori usano [argomenti denominati](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments).

- ❌**DISALLOWED: Passaggio `ref` da un `ref readonly` valore restituito a un valore restituito**

- ❌️**DISALLOWED: passaggio `ref readonly` da `ref` un valore a un valore restituito in un metodo virtuale o un'interfaccia**

- ❌**DISALLOWED: Aggiunta o rimozione di [abstract](../../csharp/language-reference/keywords/abstract.md) da un membro**

- ❌**DISALLOWED: Rimozione della parola chiave [virtual](../../csharp/language-reference/keywords/virtual.md) da un membro**

  Anche se spesso questa non è una modifica che causa un'interruzione perché il compilatore C# tende a generare istruzioni [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) in linguaggio intermedio (IL) per chiamare metodi non virtuali (diversamente da una normale chiamata, `callvirt` esegue un controllo null), questo comportamento non è invariabile per diversi motivi:
  - C# non è l'unico linguaggio di destinazione di .NET.

  - Il compilatore C# tenta sempre più di ottimizzare `callvirt` in una normale chiamata ogni volta che il metodo di destinazione non è virtuale e presumibilmente non è null (ad esempio quando si accede a un metodo tramite l'[operatore di propagazione null ?.](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-)).

  Quando un metodo viene impostato come virtuale, spesso il codice consumer finisce per chiamarlo in modo non virtuale.

- ❌**DISALLOWED: Aggiunta della parola chiave [virtual](../../csharp/language-reference/keywords/virtual.md) a un membro**

- ❌**DISALLOWED: Rendere astratto un membro virtuale**

  Un [membro virtuale](../../csharp/language-reference/keywords/virtual.md) fornisce un'implementazione di metodo che *può essere* sottoposta a override da una classe derivata. Un [membro astratto](../../csharp/language-reference/keywords/abstract.md) non fornisce alcuna implementazione e *deve essere* sottoposto a override.

- ❌**DISALLOWED: Aggiunta di un membro astratto a un tipo pubblico con costruttori accessibili (pubblici o protetti) e non [sealed](../../csharp/language-reference/keywords/sealed.md) **

- ❌**DISALLOWED: Aggiunta o rimozione della parola chiave [static](../../csharp/language-reference/keywords/static.md) da un membro**

- ❌**DISALLOWED: Aggiunta di un overload che preclude un overload esistente e definisce un comportamento diverso**

  Questa modifica causa un'interruzione dei client esistenti associati all'overload precedente. Se, ad esempio, una classe dispone di una singola versione di un metodo che accetta uno struct <xref:System.UInt32>, un consumer esistente viene correttamente associato a tale overload quando viene passato un valore <xref:System.Int32>. Se tuttavia si aggiunge un overload che accetta uno struct <xref:System.Int32>, quando viene eseguita la ricompilazione o viene usata l'associazione tardiva, il compilatore stabilisce l'associazione con il nuovo overload. In caso di comportamento diverso, si tratta di una modifica che causa un'interruzione.

- ❌**DISALLOWED: Aggiunta di un costruttore a una classe che in precedenza non aveva costruttore senza aggiungere il costruttore senza parametri**

- ❌️**DISALLOWED: Aggiunta di [readonly](../../csharp/language-reference/keywords/readonly.md) a un campo**

- ❌**DISALLOWED: Riduzione della visibilità di un membro**

   Ciò include la riduzione della visibilità`public` `protected`di un membro [protetto](../../csharp/language-reference/keywords/protected.md) quando sono *accessibili* ( o ) costruttori e il tipo *non* è [sealed](../../csharp/language-reference/keywords/sealed.md). Se questo non avviene, la limitazione della visibilità di un membro protetto è consentita.

   È consentito aumentare la visibilità di un membro.

- ❌**DISALLOWED: Modifica del tipo di membro**

   Il valore restituito di un metodo o il tipo di una proprietà o di un campo non può essere modificato. Ad esempio, la firma di un metodo che restituisce un tipo <xref:System.Object> non può essere modificata in modo da restituire un tipo <xref:System.String> o viceversa.

- ❌**DISALLOWED: Aggiunta di un campo a una struttura che in precedenza non aveva stato**

  Determinate regole di assegnazione consentono l'uso di variabili non inizializzate, purché il tipo di variabile sia uno struct senza stato. Se lo struct è definito con stato, può verificarsi un problema di mancata inizializzazione dei dati del codice. Si tratta potenzialmente di una modifica che causa un'interruzione a livello di codice sorgente e di codice binario.

- ❌**DISALLOWED: Generazione di un evento esistente quando non è mai stato generato prima**

## <a name="behavioral-changes"></a>Modifiche funzionali

### <a name="assemblies"></a>Assembly

- ✔️ **ALLOWED: Rendere un assembly portabile quando le stesse piattaforme sono ancora supportate**

- ❌**DISALLOWED: Modifica del nome di un assieme**
- ❌**DISALLOWED: Modifica della chiave pubblica di un assembly**

### <a name="properties-fields-parameters-and-return-values"></a>Proprietà, campi, parametri e valori restituiti

- ✔️ **ALLOWED: modifica del valore di una proprietà, di un campo, [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) ** di un valore restituito o di un parametro out in un tipo più derivato

  Ad esempio, un metodo che restituisce un tipo <xref:System.Object> può restituire un'istanza di <xref:System.String>. Non è tuttavia possibile modificare la firma del metodo.

- ✔️ **ALLOWED: Aumentare l'intervallo di valori accettati [virtual](../../csharp/language-reference/keywords/virtual.md) per una proprietà o** un parametro se il membro non è virtuale

  Mentre l'intervallo di valori che possono essere passati al metodo o vengono restituiti dal membro può espandersi, il parametro o il tipo di membro non può. Ad esempio, i valori passati a un metodo possono aumentare da 0-124 a 0-255, ma il tipo di parametro non può cambiare da <xref:System.Byte> a <xref:System.Int32>.

- ❌**DISALLOWED: Aumentare l'intervallo di valori accettati [virtual](../../csharp/language-reference/keywords/virtual.md) per una proprietà o** un parametro se il membro è virtuale

   Questa modifica interrompe i membri sottoposti a override esistenti, che non funzioneranno correttamente per l'intervallo di valori esteso.

- ❌**DISALLOWED: Riduzione dell'intervallo di valori accettati per una proprietà o** un parametro

- ❌**DISALLOWED: Incremento dell'intervallo di valori restituiti per una proprietà, un campo, un valore restituito o un parametro [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) **

- ❌**DISALLOWED: modifica dei valori restituiti per una proprietà, [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) un campo, un valore restituito** del metodo o un parametro out

- ❌**DISALLOWED: modifica del valore predefinito di una proprietà, di un campo o** di un parametro

- ❌**DISALLOWED: Modifica della precisione di un valore restituito numerico**

- ❓ **REQUIRES JUDGMENT: una modifica nell'analisi dell'input e nella generazione di nuove eccezioni (anche se il comportamento** di analisi non è specificato nella documentazione

### <a name="exceptions"></a>Eccezioni

- ✔️ **ALLOWED: generazione di un'eccezione più derivata rispetto a un'eccezione esistente**

  Poiché la nuova eccezione è una sottoclasse di un'eccezione esistente, il codice che gestisce l'eccezione precedente continua a gestire quella nuova. In .NET Framework 4, ad esempio, i metodi per la creazione e il recupero delle impostazioni cultura hanno iniziato a generare <xref:System.Globalization.CultureNotFoundException> anziché <xref:System.ArgumentException> in caso di impossibilità di trovare le impostazioni cultura. Poiché <xref:System.Globalization.CultureNotFoundException> deriva da <xref:System.ArgumentException>, questa è una modifica accettabile.

- ✔️ **ALLOWED: generazione di un'eccezione più specifica di <xref:System.NotSupportedException>, <xref:System.NotImplementedException>, <xref:System.NullReferenceException> **

- ✔️ **ALLOWED: generazione di un'eccezione considerata irrecuperabile**

  Le eccezioni irreversibili non devono essere intercettate, ma devono essere gestite da un gestore catch-all di alto livello. Non è quindi previsto che gli utenti abbiano codice che intercetta queste eccezioni esplicite. Le eccezioni irreversibili comprendono:

  - <xref:System.AccessViolationException>
  - <xref:System.ExecutionEngineException>
  - <xref:System.Runtime.InteropServices.SEHException>
  - <xref:System.StackOverflowException>

- ✔️ **ALLOWED: generazione di una nuova eccezione in un nuovo percorso** di codice

  L'eccezione deve essere applicata solo a un nuovo percorso di codice che viene eseguito con nuovi valori di parametro o stato e che non può essere eseguito dal codice esistente destinato alla versione precedente.

- ✔️ **ALLOWED: Rimozione di un'eccezione per abilitare** un comportamento più affidabile o nuovi scenari

  Ad esempio, un metodo `Divide` che in precedenza gestiva solo valori positivi, generando un'eccezione <xref:System.ArgumentOutOfRangeException> negli altri casi, può essere modificato in modo da supportare valori negativi e positivi senza generare un'eccezione.

- ✔️ **ALLOWED: Modifica del testo di un messaggio di errore**

  Gli sviluppatori non devono basarsi sul testo dei messaggi di errore, che cambiano anche in base alle impostazioni cultura dell'utente.

- ❌**DISALLOWED: Generazione di un'eccezione in qualsiasi altro caso non elencato sopra**

- ❌**DISALLOWED: Rimozione di un'eccezione in qualsiasi altro caso non elencato sopra**

### <a name="attributes"></a>Attributes

- ✔️ **ALLOWED: Modifica del valore di un attributo *non* osservabile**

- ❌**DISALLOWED: Modifica del valore *is* di un attributo osservabile**

- ❓ **REQUIRES JUDGMENT: Rimozione di un attributo**

  Nella maggior parte dei casi, la rimozione di un attributo (ad esempio <xref:System.NonSerializedAttribute>) è una modifica che causa un'interruzione.

## <a name="platform-support"></a>Piattaforme supportate

- ✔️ **ALLOWED: supporto di un'operazione su una piattaforma che in precedenza non era supportata**

- ❌**DISALLOWED: non supporta o ora richiede un service pack specifico per un'operazione precedentemente supportata su una piattaforma**

## <a name="internal-implementation-changes"></a>Modifiche all'implementazione interna

- ❓ **REQUIRES JUDGMENT: Modifica della superficie di un tipo interno**

   Queste modifiche sono in genere consentite, anche se interrompono la reflection privata. È tuttavia possibile che in alcuni casi non lo siano, ad esempio quando le librerie di terze parti più diffuse o numerosi sviluppatori dipendono dalle API interne.

- ❓ **REQUIRES JUDGMENT: Modifica dell'implementazione interna di un membro**

  Queste modifiche sono in genere consentite, anche se interrompono la reflection privata. È tuttavia possibile che in alcuni casi non lo siano, ad esempio quando il codice cliente dipende spesso dalla reflection privata o la modifica presenta effetti collaterali imprevisti.

- ✔️ **ALLOWED: Migliorare le prestazioni di un'operazione**

   La possibilità di modificare le prestazioni di un'operazione è essenziale, ma tali modifiche possono interrompere il codice che si basa la velocità corrente di un'operazione. Questo vale in particolare per il codice che dipende dalla tempistica delle operazioni asincrone. La modifica delle prestazioni non dovrebbe avere alcun effetto su altri comportamenti dell'API in questione; in caso contrario, la modifica sarà interruzione.

- ✔️ **ALLOWED: Modifica indiretta (e spesso negativa) delle prestazioni di un'operazione**

  La modifica in questione è accettabile se non è classificata per altri motivi come modifica che causa un'interruzione. È spesso necessario eseguire azioni che includono operazioni supplementari o che aggiungono nuove funzionalità. Questo ha quasi sempre effetto sulle prestazioni, ma può essere fondamentale per fare in modo che l'API in questione funzioni come previsto.

- ❌**DISALLOWED: Modifica di un'API sincrona in asincrona (e viceversa)**

## <a name="code-changes"></a>Modifiche al codice

- ✔️ **ALLOWED: Aggiunta di [parametri](../../csharp/language-reference/keywords/params.md) a un parametro**

- ❌**DISALLOWED: Modifica di una [struttura](../../csharp/language-reference/builtin-types/struct.md) in una [classe](../../csharp/language-reference/keywords/class.md) e viceversa**

- ❌**DISALLOWED: Aggiunta della parola chiave [checked](../../csharp/language-reference/keywords/virtual.md) a un blocco di codice**

   Per effetto di questa modifica, il codice eseguito in precedenza può generare un'eccezione <xref:System.OverflowException> e non essere accettabile.

- ❌**DISALLOWED: Rimozione di [parametri](../../csharp/language-reference/keywords/params.md) da un parametro**

- ❌**DISALLOWED: Modifica dell'ordine di scomposizione** degli eventi

  Gli sviluppatori possono ragionevolmente aspettarsi che gli eventi vengano generati nello stesso ordine e il codice degli sviluppatori spesso dipende dall'ordine di generazione degli eventi.

- ❌**DISALLOWED: Rimozione della raccolta di un evento su una determinata azione**

- ❌**DISALLOWED: Modifica del numero di volte** in cui gli eventi vengono chiamati

- ❌**DISALLOWED: Aggiunta <xref:System.FlagsAttribute> di the a un tipo di enumerazione**
