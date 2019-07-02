---
title: Valutare le modifiche che causano un'interruzione - .NET Core
description: Informazioni sui modi in cui .NET Core tenta di garantire la compatibilità tra le versioni di .NET per sviluppatori.
author: rpetrusha
ms.author: ronpet
ms.date: 06/10/2019
ms.openlocfilehash: b58edd9ff0bd56b12b861162cc92d484a3b36c8b
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/21/2019
ms.locfileid: "67307549"
---
# <a name="evaluate-breaking-changes-in-net-core"></a>Valutare le modifiche che causano un'interruzione

Nel corso del tempo, .NET ha tentato di mantenere un elevato livello di compatibilità tra le diverse versioni. Questo è vero anche per .NET Core. Anche se la tecnologia .NET Core può essere considerata indipendente da .NET Framework, due fattori principali limitano la possibilità di .NET Core di discostarsi da .NET Framework:

- Numerosi sviluppatori hanno originariamente sviluppato o continuano a sviluppare applicazioni .NET Framework e si aspettano un comportamento coerente in tutte le implementazioni di .NET.

- I progetti di libreria .NET Standard consentono agli sviluppatori di creare librerie per API comuni condivise da .NET Core e .NET Framework. Gli sviluppatori si aspettano che una libreria usata in un'applicazione .NET Core debba comportarsi in modo identico alla stessa libreria usata in un'applicazione .NET Framework.

Oltre alla compatibilità tra le implementazioni di .NET, gli sviluppatori si aspettano un elevato livello di compatibilità tra le versioni di .NET Core. In particolare, il codice scritto per una versione precedente di .NET Core dovrebbe essere eseguito senza problemi in una versione successiva di .NET Core. In realtà, molti gli sviluppatori si aspettano che le nuove API incluse nelle nuove versioni rilasciate di .NET Core siano compatibili anche con le versioni non definitive in cui sono state introdotte le API.

Questo articolo descrive le categorie di modifiche di compatibilità (o che causano un'interruzione) e il modo in cui le modifiche di ogni categoria vengono valutate dal team di .NET. Le informazioni sull'approccio del team di .NET alle possibili modifiche che causano un'interruzione sono particolarmente utili per gli sviluppatori che aprono richieste pull nel repository [dotnet/corefx](https://github.com/dotnet/corefx) di GitHub per modificare il comportamento di API esistenti.

> [!NOTE]
> Per una definizione delle categorie di compatibilità, come la compatibilità a livello di codice binario e la compatibilità con le versioni precedenti, vedere [Categorie di modifiche che causano un'interruzione](categories.md).

Le sezioni seguenti descrivono le categorie delle modifiche apportate alle API di .NET Core e il relativo impatto sulla compatibilità delle applicazioni. L'icona ✔️ indica che una modifica di un determinato tipo è consentita, ❌ indica che non è consentita e ❓ indica che può essere o non essere consentita. Le modifiche di quest'ultima categoria richiedono una valutazione della prevedibilità, ovvietà e coerenza del comportamento precedente.

> [!NOTE]
> Oltre a servire da guida per la valutazione delle modifiche alle librerie di .NET Core, questi criteri possono essere usati dagli sviluppatori di librerie per valutare le modifiche alle librerie destinate a più versioni e implementazioni di .NET.

## <a name="modifications-to-the-public-contract"></a>Modifiche al contratto pubblico

Le modifiche di questa categoria *interessano* la superficie di attacco pubblica di un tipo. La maggior parte delle modifiche incluse in questa categoria non è consentita perché viola la *compatibilità con le versioni precedenti*, ovvero la capacità di un'applicazione sviluppata con una versione precedente di un'API di essere eseguita senza ricompilazione in una versione successiva.

### <a name="types"></a>Tipi

- **✔️ Rimozione di un'implementazione dell'interfaccia da un tipo quando l'interfaccia è già implementata da un tipo di base**

- **❓ Aggiunta di una nuova implementazione dell'interfaccia a un tipo**

  Questa è una modifica accettabile perché non ha effetti negativi sui client esistenti. Affinché la nuova implementazione rimanga accettabile, le modifiche al tipo devono rimanere entro i limiti delle modifiche accettabili definite di seguito. È necessario prestare particolare attenzione quando si aggiungono interfacce che influiscono direttamente sulla capacità di una finestra di progettazione o un serializzatore di generare codice o dati che non possono essere utilizzati nelle versioni precedenti. Un esempio è costituito dall'interfaccia <xref:System.Runtime.Serialization.ISerializable>.

- **❓ Introduzione di una nuova classe di base**

  Un tipo può essere introdotto in una gerarchia tra due tipi esistenti se non introduce nuovi membri [astratti](../../csharp/language-reference/keywords/abstract.md) o modifica la semantica o il comportamento di tipi esistenti. Ad esempio, in .NET Framework 2.0, la classe <xref:System.Data.Common.DbConnection> è diventata una nuova classe di base per <xref:System.Data.SqlClient.SqlConnection>, che in precedenza derivava direttamente da <xref:System.ComponentModel.Component>.

- **✔️ Spostamento di un tipo da un assembly a un altro**

  Si noti che l'assembly *precedente* deve essere contrassegnato con l'attributo <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> che punta al nuovo assembly.

- **✔️ Modifica di un tipo [struct](../../csharp/language-reference/keywords/struct.md) in un tipo `readonly struct`**

  Si noti che la modifica un tipo `readonly struct` in un tipo `struct` non è consentita.
  
- **✔️ Aggiunta della parola chiave [sealed](../../csharp/language-reference/keywords/sealed.md) o [abstract](../../csharp/language-reference/keywords/abstract.md) a un tipo quando non sono presenti costruttori *accessibili* (pubblici o protetti)**

- **✔️ Espansione della visibilità di un tipo**

- **❌ Modifica dello spazio dei nomi o del nome di un tipo**

- **❌ Ridenominazione o rimozione di un tipo pubblico**

   Questa operazione causa l'interruzione di tutto il codice che usa il tipo rinominato o rimosso.

- **❌ Modifica del tipo sottostante di un'enumerazione**

   Si tratta di una modifica che causa un'interruzione a livello di compilazione, comportamento e codice binario che può rendere non analizzabili gli argomenti degli attributi.

- **❌ Sealing di un tipo che in precedenza era non sealed**

- **❌ Aggiunta di un'interfaccia al set di tipi di base di un'interfaccia**

   Se un'interfaccia implementa un'interfaccia che in precedenza non implementava, tutti i tipi che implementavano la versione originale dell'interfaccia vengono interrotti.

- **❓ Rimozione di una classe da un set di classi di base o di un'interfaccia dal set di interfacce implementate**

  Esiste un'unica eccezione alla regola per la rimozione di un'interfaccia. È possibile aggiungere l'implementazione di un'interfaccia che deriva dall'interfaccia rimossa. È ad esempio possibile rimuovere <xref:System.IDisposable> se il tipo o l'interfaccia implementa ora <xref:System.ComponentModel.IComponent>, che implementa a sua volta l'interfaccia <xref:System.IDisposable>.

- **❌ Modifica di un tipo `readonly struct` in un tipo [struct](../../csharp/language-reference/keywords/struct.md)**

  Si noti che la modifica di un tipo `struct` in un tipo `readonly struct` è consentita.

- **❌ Modifica di un tipo [struct](../../csharp/language-reference/keywords/struct.md) in un tipo `ref struct` e viceversa**

- **❌ Limitazione della visibilità di un tipo**

   L'espansione della visibilità di un tipo è tuttavia consentita.

### <a name="members"></a>Membri

- **✔️ Espansione della visibilità di un membro non [virtuale](../../csharp/language-reference/keywords/sealed.md)**

- **✔️ Aggiunta di un membro astratto a un tipo pubblico che non ha costruttori *accessibili* (pubblici o protetti) o che è [sealed](../../csharp/language-reference/keywords/sealed.md)**

  Non è tuttavia consentita l'aggiunta di un membro astratto a un tipo pubblico che ha costruttori accessibili (pubblici o protetti) e che non è `sealed`.

- **✔️ Limitazione della visibilità di un membro [protetto](../../csharp/language-reference/keywords/protected.md) quando il tipo non ha costruttori accessibili (pubblici o protetti) oppure è [sealed](../../csharp/language-reference/keywords/sealed.md)**

- **✔️ Spostamento di un membro in una classe di livello superiore nella gerarchia rispetto al tipo da cui è stato rimosso**

- **✔️ Aggiunta o rimozione di un override**

  Si noti che, se si introduce un override, i consumer precedenti potrebbero ignorare l'override quando eseguono la chiamata a [base](../../csharp/language-reference/keywords/base.md).

- **✔️ Aggiunta di un costruttore a una classe, insieme a un costruttore predefinito (senza parametri), se in precedenza la classe era priva di costruttori**

   Non è tuttavia consentita l'aggiunta di un costruttore a una classe che in precedenza era priva di costruttori *senza* aggiungere il costruttore predefinito.

- **✔️ Modifica di un membro da [astratto](../../csharp/language-reference/keywords/abstract.md) a [virtuale](../../csharp/language-reference/keywords/virtual.md)**

- **✔️ Modifica da un `ref readonly` a un valore restituito `ref` (ad eccezione dei metodi o delle interfacce virtuali)**

- **✔️ Rimozione di [readonly](../../csharp/language-reference/keywords/readonly.md) da un campo, a meno che il tipo statico del campo non sia un tipo di valore modificabile**

- **✔️ Chiamata di un nuovo evento non definito in precedenza**

- **❓ Aggiunta del campo di una nuova istanza a un tipo**

   Questa modifica ha impatto sulla serializzazione.

- **❌ Ridenominazione o rimozione di un parametro o un membro pubblico**

   Questa operazione causa l'interruzione di tutto il codice che usa il parametro o il membro rinominato o rimosso.

   Si noti che questo include la rimozione o la ridenominazione di un getter o un setter da una proprietà, nonché la ridenominazione o la rimozione dei membri di un'enumerazione.

- **❌ Aggiunta di un membro a un'interfaccia**

- **❌ Modifica del valore di una costante pubblica o del membro di un'enumerazione**

- **❌ Modifica del tipo di una proprietà, di un campo, di un parametro o di un valore restituito**

- **❌ Aggiunta, rimozione o modifica dell'ordine dei parametri**

- **❌ Aggiunta o rimozione della parola chiave [in](../../csharp/language-reference/keywords/in.md), [out](../../csharp/language-reference/keywords/out.md) o [ref](../../csharp/language-reference/keywords/ref.md) in un parametro**

- **❌ Ridenominazione di un parametro (inclusa la modifica di maiuscole e minuscole)**

  Questa viene considerata una modifica che causa un'interruzione per due motivi:
  
  - Interrompe gli scenari con associazione tardiva, ad esempio la funzionalità di associazione tardiva in Visual Basic e [dynamic](../../csharp/language-reference/keywords/dynamic.md) in C#.
  
  - Interrompe la [compatibilità a livello di codice sorgente](categories.md#source-compatibility) quando gli sviluppatori usano [argomenti denominati](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments).

- **❌ Modifica di un valore restituito `ref` in un valore restituito `ref readonly`**

- **✔️ Modifica di un `ref readonly` in un valore restituito `ref` su un metodo o un'interfaccia virtuale**

- **❌ Aggiunta o rimozione della parola chiave [abstract](../../csharp/language-reference/keywords/abstract.md) in un membro**

- **❌ Rimozione della parola chiave [virtual](../../csharp/language-reference/keywords/virtual.md) da un membro**

  Anche se spesso questa non è una modifica che causa un'interruzione perché il compilatore C# tende a generare istruzioni [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) in linguaggio intermedio (IL) per chiamare metodi non virtuali (diversamente da una normale chiamata, `callvirt` esegue un controllo null), questo comportamento non è invariabile per diversi motivi:
  - C# non è l'unico linguaggio di destinazione di .NET.
  
  - Il compilatore C# tenta sempre più di ottimizzare `callvirt` in una normale chiamata ogni volta che il metodo di destinazione non è virtuale e presumibilmente non è null (ad esempio quando si accede a un metodo tramite l'[operatore di propagazione null ?.](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-)).
  
  Quando un metodo viene impostato come virtuale, spesso il codice consumer finisce per chiamarlo in modo non virtuale.

- **❌ Aggiunta della parola chiave [virtual](../../csharp/language-reference/keywords/virtual.md) a un membro**

- **❌ Impostazione di un membro virtuale come astratto**

  Un [membro virtuale](../../csharp/language-reference/keywords/virtual.md) fornisce un'implementazione di metodo che *può essere* sottoposta a override da una classe derivata. Un [membro astratto](../../csharp/language-reference/keywords/abstract.md) non fornisce alcuna implementazione e *deve essere* sottoposto a override.

- **❌ Aggiunta di un membro astratto a un tipo pubblico che ha costruttori accessibili (pubblici o protetti) e che non è [sealed](../../csharp/language-reference/keywords/sealed.md)**

- **❌ Aggiunta o rimozione della parola chiave [static](../../csharp/language-reference/keywords/static.md) in un membro**

- **❌ Aggiunta di un overload che preclude un overload esistente e che definisce un comportamento diverso**

  Questa modifica causa un'interruzione dei client esistenti associati all'overload precedente. Se, ad esempio, una classe dispone di una singola versione di un metodo che accetta uno struct <xref:System.UInt32>, un consumer esistente viene correttamente associato a tale overload quando viene passato un valore <xref:System.Int32>. Se tuttavia si aggiunge un overload che accetta uno struct <xref:System.Int32>, quando viene eseguita la ricompilazione o viene usata l'associazione tardiva, il compilatore stabilisce l'associazione con il nuovo overload. In caso di comportamento diverso, si tratta di una modifica che causa un'interruzione.

- **❌ Aggiunta di un costruttore a una classe che in precedenza era priva di costruttori senza aggiungere il costruttore predefinito**

- **❌️ Aggiunta di [readonly](../../csharp/language-reference/keywords/readonly.md) a un campo**

- **❌ Limitazione della visibilità di un membro**

   Ciò include la limitazione della visibilità di un membro [protetto](../../csharp/language-reference/keywords/protected.md) quando non sono presenti costruttori *accessibili* (pubblici o protetti) e il tipo *non* è [sealed](../../csharp/language-reference/keywords/sealed.md). Se questo non avviene, la limitazione della visibilità di un membro protetto è consentita.

   L'espansione della visibilità di un membro è tuttavia consentita.

- **❌ Modifica del tipo di un membro**

   Il valore restituito di un metodo o il tipo di una proprietà o di un campo non può essere modificato. Ad esempio, la firma di un metodo che restituisce un tipo <xref:System.Object> non può essere modificata in modo da restituire un tipo <xref:System.String> o viceversa.

- **❌ Aggiunta di un campo a uno struct che in precedenza era senza stato**

  Determinate regole di assegnazione consentono l'uso di variabili non inizializzate, purché il tipo di variabile sia uno struct senza stato. Se lo struct è definito con stato, può verificarsi un problema di mancata inizializzazione dei dati del codice. Si tratta potenzialmente di una modifica che causa un'interruzione a livello di codice sorgente e di codice binario.

- **❌ Generazione di un evento esistente che in precedenza non veniva mai generato**

## <a name="behavioral-changes"></a>Modifiche funzionali

### <a name="assemblies"></a>Assembly

- **✔️ Rendere portabile un assembly quando le stesse piattaforme sono ancora supportate**

- **❌ Modifica del nome di un assembly**
- **❌ Modifica della chiave pubblica di un assembly**

### <a name="properties-fields-parameters-and-return-values"></a>Proprietà, campi, parametri e valori restituiti

- **✔️ Modifica del valore di una proprietà, di un campo, di un valore restituito o di un parametro [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) in un tipo più derivato**

  Ad esempio, un metodo che restituisce un tipo <xref:System.Object> può restituire un'istanza di <xref:System.String>. Non è tuttavia possibile modificare la firma del metodo.

- **✔️ Aumento dell'intervallo di valori accettati per una proprietà o un parametro se il membro non è [virtuale](../../csharp/language-reference/keywords/virtual.md)**

  Si noti che l'intervallo di valori che possono essere passati al metodo o che vengono restituiti dal membro può essere esteso, ma il tipo di parametro o di membro deve rimanere invariato. Ad esempio, i valori passati a un metodo possono aumentare da 0-124 a 0-255, ma il tipo di parametro non può cambiare da <xref:System.Byte> a <xref:System.Int32>.

- **✔️ Aumento dell'intervallo di valori accettati per una proprietà o un parametro se il membro è [virtuale](../../csharp/language-reference/keywords/virtual.md)**

   Questa modifica interrompe i membri sottoposti a override esistenti, che non funzioneranno correttamente per l'intervallo di valori esteso.

- **❌ Riduzione dell'intervallo di valori accettati per una proprietà o un parametro**

- **❌ Aumento dell'intervallo di valori restituiti per una proprietà, un campo, un valore restituito o un parametro [out](../../csharp/language-reference/keywords/out-parameter-modifier.md)**

- **❌ Modifica dei valori restituiti per una proprietà, un campo, un valore restituito da un metodo o un parametro [out](../../csharp/language-reference/keywords/out-parameter-modifier.md)**

- **❌ Modifica del valore predefinito di una proprietà, un campo o un parametro**

- **❌ Modifica della precisione di un valore numerico restituito**

- **❓ Modifica nell'analisi dell'input e nella generazione di nuove eccezioni (anche se il comportamento dell'analisi non è specificato nella documentazione**

### <a name="exceptions"></a>Eccezioni

- **✔️ Generazione di un'eccezione più derivata rispetto a un'eccezione esistente**

  Poiché la nuova eccezione è una sottoclasse di un'eccezione esistente, il codice che gestisce l'eccezione precedente continua a gestire quella nuova. In .NET Framework 4, ad esempio, i metodi per la creazione e il recupero delle impostazioni cultura hanno iniziato a generare <xref:System.Globalization.CultureNotFoundException> anziché <xref:System.ArgumentException> in caso di impossibilità di trovare le impostazioni cultura. Poiché <xref:System.Globalization.CultureNotFoundException> deriva da <xref:System.ArgumentException>, questa è una modifica accettabile.

- **✔️ Generazione di un'eccezione più specifica rispetto a <xref:System.NotSupportedException>, <xref:System.NotImplementedException>, <xref:System.NullReferenceException>**

- **✔️ Generazione di un'eccezione considerata irreversibile**

  Le eccezioni irreversibili non devono essere intercettate, ma devono essere gestite da un gestore catch-all di alto livello. Non è quindi previsto che gli utenti abbiano codice che intercetta queste eccezioni esplicite. Le eccezioni irreversibili comprendono:

  - <xref:System.AccessViolationException>
  - <xref:System.ExecutionEngineException>
  - <xref:System.Runtime.InteropServices.SEHException>
  - <xref:System.StackOverflowException>

- **✔️ Generazione di una nuova eccezione in un nuovo percorso del codice**

  L'eccezione deve interessare solo un nuovo percorso del codice che viene eseguito con un nuovo stato o nuovi valori di parametro e non può essere eseguito da codice esistente creato per la versione precedente.

- **✔️ Rimozione di un'eccezione per abilitare nuovi scenari o un comportamento più efficace**

  Ad esempio, un metodo `Divide` che in precedenza gestiva solo valori positivi, generando un'eccezione <xref:System.ArgumentOutOfRangeException> negli altri casi, può essere modificato in modo da supportare valori negativi e positivi senza generare un'eccezione.

- **✔️ Modifica del testo di un messaggio di errore**

  Gli sviluppatori non devono basarsi sul testo dei messaggi di errore, che cambiano anche in base alle impostazioni cultura dell'utente.

- **❌ Generazione di un'eccezione in tutti gli altri casi non elencati**

- **❌ Rimozione di un'eccezione in tutti gli altri casi non elencati**

### <a name="attributes"></a>Attributi

- **✔️ Modifica del valore di un attributo che *non* è osservabile**

- **✔️ Modifica del valore di un attributo che *è* osservabile**

- **❓ Rimozione di un attributo**

  Nella maggior parte dei casi, la rimozione di un attributo (ad esempio <xref:System.NonSerializedAttribute>) è una modifica che causa un'interruzione.

## <a name="platform-support"></a>Supporto per piattaforme

- **✔️ Supporto di un'operazione su una piattaforma che in precedenza non era supportata**

- **❌ Mancato supporto o nuova richiesta di uno specifico Service Pack per un'operazione che in precedenza era supportata su una piattaforma**

## <a name="internal-implementation-changes"></a>Modifiche all'implementazione interna

- **❓ Modifica della superficie di attacco di un tipo interno**

   Queste modifiche sono in genere consentite, anche se interrompono la reflection privata. È tuttavia possibile che in alcuni casi non lo siano, ad esempio quando le librerie di terze parti più diffuse o numerosi sviluppatori dipendono dalle API interne.

- **❓ Modifica dell'implementazione interna di un membro**

  Queste modifiche sono in genere consentite, anche se interrompono la reflection privata. È tuttavia possibile che in alcuni casi non lo siano, ad esempio quando il codice cliente dipende spesso dalla reflection privata o la modifica presenta effetti collaterali imprevisti.

- **✔️ Miglioramento delle prestazioni di un'operazione**

   La possibilità di modificare le prestazioni di un'operazione è essenziale, ma tali modifiche possono interrompere il codice che si basa la velocità corrente di un'operazione. Questo vale in particolare per il codice che dipende dalla tempistica delle operazioni asincrone. Si noti che la modifica delle prestazioni non deve avere alcun effetto su altri comportamenti dell'API in questione. In caso contrario, la modifica causerà un'interruzione.

- **✔️ Modifica indiretta (e spesso con effetti negativi) delle prestazioni di un'operazione**

  La modifica in questione è accettabile se non è classificata per altri motivi come modifica che causa un'interruzione. È spesso necessario eseguire azioni che includono operazioni supplementari o che aggiungono nuove funzionalità. Questo ha quasi sempre effetto sulle prestazioni, ma può essere fondamentale per fare in modo che l'API in questione funzioni come previsto.

- **❌ Modifica di un'API sincrona in una asincrona (e viceversa)**

## <a name="code-changes"></a>Modifiche al codice

- **✔️ Aggiunta di [params](../../csharp/language-reference/keywords/params.md) a un parametro**

- **❌ Modifica di uno [struct](../../csharp/language-reference/keywords/struct.md) in una [classe](../../csharp/language-reference/keywords/class.md) e viceversa**

- **❌ Aggiunta della parola chiave [checked](../../csharp/language-reference/keywords/virtual.md) a un blocco di codice**

   Per effetto di questa modifica, il codice eseguito in precedenza può generare un'eccezione <xref:System.OverflowException> e non essere accettabile.

- **❌ Rimozione di [params](../../csharp/language-reference/keywords/params.md) da un parametro**

- **❌ Modifica dell'ordine di generazione degli eventi**

  Gli sviluppatori possono ragionevolmente aspettarsi che gli eventi vengano generati nello stesso ordine e il codice degli sviluppatori spesso dipende dall'ordine di generazione degli eventi.

- **❌ Rimozione della generazione di un evento per effetto di una determinata azione**

- **❌ Modifica del numero di volte in cui vengono chiamati determinati eventi**

- **❌ Aggiunta di <xref:System.FlagsAttribute> a un tipo di enumerazione**
