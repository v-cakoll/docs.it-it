---
title: Proprietà
description: Informazioni sulle proprietà di C#, tra cui funzionalità per la convalida, valori calcolati, valutazione lazy e notifiche di modifica di proprietà.
ms.technology: csharp-fundamentals
ms.date: 04/25/2018
ms.openlocfilehash: bda8a4f58f71b57248296dd4ba9f9bf4cbed40d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399413"
---
# <a name="properties"></a>Proprietà

Le proprietà sono elementi fondamentali in C#. Il linguaggio definisce la sintassi che consente agli sviluppatori di scrivere codice che esprime in modo preciso la finalità della progettazione.

Quando viene eseguito l'accesso, le proprietà si comportano come i campi.
Tuttavia, a differenza dei campi, le proprietà vengono implementate con funzioni di accesso che definiscono le istruzioni eseguite al momento dell'accesso e dell'assegnazione della proprietà.

## <a name="property-syntax"></a>Sintassi delle proprietà

La sintassi delle proprietà è un'estensione naturale dei campi. Un campo definisce una posizione di archiviazione:

[!code-csharp[Person class with public fields](../../samples/snippets/csharp/properties/Person.cs#1)]

La definizione di una proprietà contiene le dichiarazioni di una funzione di accesso `get` e `set` che recupera e assegna il valore della proprietà:

[!code-csharp[Person class with public properties](../../samples/snippets/csharp/properties/Person.cs#2)]

La sintassi illustrata sopra è la sintassi della *proprietà automatica*. Il compilatore genera la posizione di archiviazione per il campo che esegue il backup della proprietà. Il compilatore implementa anche il corpo delle funzioni di accesso `get` e `set`.

In alcuni casi è necessario inizializzare una proprietà con un valore diverso da quello predefinito per il suo tipo.  In C# questa operazione è possibile impostando un valore dopo la parentesi graffa chiusa della proprietà. Per la proprietà `FirstName` è preferibile usare come valore iniziale una stringa vuota anziché `null`. Ecco come eseguire questa operazione:

[!code-csharp[Person class with properties and initializer](../../samples/snippets/csharp/properties/Person.cs#3)]

L'inizializzazione specifica è particolarmente utile per le proprietà di sola lettura, come si vedrà più avanti in questo articolo.

È anche possibile definire l'archiviazione manualmente, come illustrato di seguito:

[!code-csharp[Person class with properties and backing field](../../samples/snippets/csharp/properties/Person.cs#4)]

Se l'implementazione di una proprietà corrisponde a un'espressione singola, è possibile usare *membri con corpo di espressione* per il getter o il setter:

[!code-csharp[Person class with properties and expression bodied getters and setters](../../samples/snippets/csharp/properties/Person.cs#5)]

Questa sintassi semplificata verrà usata ovunque applicabile in questo articolo.

La definizione della proprietà illustrata sopra è una proprietà di lettura/scrittura. Si noti la parola chiave `value` nella funzione di accesso impostata. La funzione di accesso `set` ha sempre un singolo parametro denominato `value`. La funzione di accesso `get` deve restituire un valore che è convertibile nel tipo della proprietà (in questo esempio `string`).

Queste sono le nozioni di basi sulla sintassi. Esistono numerose varianti che supportano un'ampia gamma di termini di progettazione diversi. Di seguito sono descritte le opzioni di sintassi per ogni termine.

## <a name="scenarios"></a>Scenari

Gli esempi precedenti hanno illustrato uno dei casi più semplici di definizione delle proprietà, ovvero una proprietà di lettura/scrittura senza convalida. Scrivendo il codice desiderato nelle funzioni di accesso `get` e `set` è possibile creare scenari diversi.

### <a name="validation"></a>Convalida

È possibile scrivere codice nella funzione di accesso `set` per assicurarsi che i valori rappresentati da una proprietà siano sempre validi. Ad esempio, si supponga che una regola per la classe `Person` preveda che il nome non può essere vuoto o uno spazio vuoto. Sarà necessario scrivere:

[!code-csharp[Validating property setters](../../samples/snippets/csharp/properties/Person.cs#6)]

L'esempio precedente può essere semplificato usando un'espressione `throw` come parte della convalida del setter della proprietà:

[!code-csharp[Validating property setters](../../samples/snippets/csharp/properties/Person.cs#7)]

L'esempio precedente applica la regola che prevede che il nome non può essere vuoto o uno spazio vuoto. Se lo sviluppatore scrive

```csharp
hero.FirstName = "";
```

L'assegnazione genera `ArgumentException`. Poiché la funzione di accesso di un insieme di proprietà deve avere un tipo restituito void, gli errori vengono segnalati nella funzione di accesso dell'insieme generando un'eccezione.

La stessa sintassi può essere estesa a ogni elemento necessario nello scenario. È possibile controllare le relazioni tra le diverse proprietà o eseguire la convalida in base a qualsiasi condizione esterna. Tutte le istruzioni C# valide sono valide nella funzione di accesso di una proprietà.

### <a name="read-only"></a>Sola lettura

Le definizioni di proprietà descritte fino a questo punto si riferiscono a proprietà di lettura/scrittura con funzioni di accesso pubbliche. Non si tratta tuttavia dell'unica accessibilità valida per le proprietà.
È possibile creare proprietà di sola lettura o assegnare un'accessibilità diversa alle funzioni di accesso set e get. Si supponga che la classe `Person` debba consentire soltanto la modifica del valore della proprietà `FirstName` da altri metodi della classe. È possibile assegnare alla funzione di accesso set l'accessibilità `private` anziché `public`:

[!code-csharp[Using a private setter for a publicly readonly property](../../samples/snippets/csharp/properties/Person.cs#8)]

L'accesso alla proprietà `FirstName` potrà quindi essere eseguito da qualsiasi codice, ma la proprietà potrà essere assegnata soltanto da altro codice della classe `Person`.

È possibile aggiungere qualsiasi modificatore di accesso restrittivo alle funzioni di accesso set o get. Il modificatore di accesso inserito nella singola funzione di accesso deve essere più restrittivo del modificatore di accesso della definizione della proprietà. Il codice precedente è valido poiché la proprietà `FirstName` è `public` e la funzione di accesso set è `private`. Non è possibile dichiarare una proprietà `private` con una funzione di accesso `public`. Le dichiarazioni di proprietà possono anche essere dichiarate `protected`, `internal`, `protected internal` o anche `private`.

È anche consentito inserire il modificatore più restrittivo nella funzione di accesso `get`. Ad esempio, è possibile avere una proprietà `public` e limitare la funzione di accesso `get` a `private`. Questo scenario viene usato raramente.

È anche possibile limitare le modifiche a una proprietà, in modo che possa essere impostata solo in un costruttore o in un inizializzatore di proprietà. È possibile modificare in tal senso la classe `Person` come segue:

[!code-csharp[A readonly auto implemented property](../../samples/snippets/csharp/properties/Person.cs#9)]

Questa funzionalità viene in genere usata per l'inizializzazione delle raccolte esposte come proprietà di sola lettura:

```csharp
public class Measurements
{
    public ICollection<DataPoint> points { get; } = new List<DataPoint>();
}
```

### <a name="computed-properties"></a>Proprietà calcolate

Una proprietà non si limita a restituire il valore di un campo membro. È possibile creare proprietà che restituiscono un valore calcolato. Espandere l'oggetto `Person` per restituire il nome completo, calcolato concatenando il nome e il cognome:

[!code-csharp[A computed property](../../samples/snippets/csharp/properties/Person.cs#10)]

L'esempio precedente usa la funzionalità di [interpolazione delle stringhe](./language-reference/tokens/interpolated.md) per creare la stringa formattata per il nome completo.

È anche possibile usare un *membro con corpo di espressione* che consente di creare la proprietà calcolata `FullName` in modo più conciso:

[!code-csharp[A computed property using an expression bodied member](../../samples/snippets/csharp/properties/Person.cs#11)]

I *membri con corpo di espressione* usano la sintassi delle *espressioni lambda* per definire i metodi che contengono una singola espressione. In questo caso, l'espressione restituisce il nome completo per l'oggetto person.

### <a name="cached-evaluated-properties"></a>Proprietà con valutazione memorizzata nella cache

È possibile unire il concetto di proprietà calcolata al concetto di archiviazione e creare una *proprietà con valutazione memorizzata nella cache*.  Ad esempio, è possibile aggiornare la proprietà `FullName` in modo che venga eseguita soltanto la formattazione della stringa al primo accesso:

[!code-csharp[Caching the value of a computed property](../../samples/snippets/csharp/properties/Person.cs#12)]

Il codice riportato sopra tuttavia contiene un bug. Se il codice aggiorna il valore della proprietà `FirstName` o `LastName`, il campo `fullName` valutato in precedenza non è valido. Modificare le funzioni di accesso `set` della proprietà `FirstName` e `LastName` in modo che il campo `fullName` venga calcolato nuovamente:

[!code-csharp[Invalidating the cache correctly](../../samples/snippets/csharp/properties/Person.cs#13)]

La versione finale valuta la proprietà `FullName` solo quando necessario.
Se è valida, viene usata la versione calcolata in precedenza. Se un'altra modifica dello stato annulla la validità della versione calcolata in precedenza, la versione verrà ricalcolata. Non è necessario che gli sviluppatori che usano questa classe siano a conoscenza dei dettagli dell'implementazione. Nessuna di queste modifiche interne ha effetto sull'uso dell'oggetto Person. Questo è il motivo principale dell'uso delle proprietà per l'esposizione dei membri dati di un oggetto.

### <a name="attaching-attributes-to-auto-implemented-properties"></a>Collegamento di attributi a proprietà implementate automaticamente

A partire da C# 7.3 è possibile collegare gli attributi campo al campo sottostante generato dal compilatore nelle proprietà implementate automaticamente. Si consideri ad esempio una revisione della classe `Person` che aggiunge una proprietà `Id` al valore intero univoco.
Si scrive la proprietà `Id` usando una proprietà implementata automaticamente, ma la progettazione non esegue la chiamata per salvare in modo permanente la proprietà `Id`. La classe <xref:System.NonSerializedAttribute> può essere collegata soltanto a campi, non a proprietà. È possibile collegare la classe <xref:System.NonSerializedAttribute> al campo sottostante per la proprietà `Id` usando l'identificatore `field:` dell'attributo, come illustrato nell'esempio seguente:

[!code-csharp[Attaching attributes to a backing field](../../samples/snippets/csharp/properties/Person.cs#14)]

Questa tecnica funziona con qualsiasi attributo collegato al campo sottostante nella proprietà implementate automaticamente.

### <a name="implementing-inotifypropertychanged"></a>Implementazione di NotifyPropertyChanged

Uno scenario finale in cui è necessario scrivere codice nella funzione di accesso di una proprietà è quello finalizzato al supporto dell'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged> usata per inviare ai client di data binding la notifica della modifica di un valore. Quando viene modificato il valore di una proprietà, l'oggetto genera l'evento <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged?displayProperty=nameWithType> per indicare la modifica. Le librerie di data binding aggiornano a loro volta gli elementi visualizzati in base alla modifica. Il codice seguente illustra come implementare `INotifyPropertyChanged` per la proprietà `FirstName` della classe person.

[!code-csharp[invalidating the cache correctly](../../samples/snippets/csharp/properties/Person.cs#15)]

L'operatore `?.` è chiamato *operatore condizionale Null*. L'operatore cerca un riferimento Null prima di eseguire la valutazione della parte destra dell'operatore. Se non vengono trovati sottoscrittori dell'evento `PropertyChanged`, il codice che genera l'evento non viene eseguito. In questo caso, verrà generato `NullReferenceException` senza eseguire il controllo. Per ulteriori informazioni, vedere [`events`](events-overview.md). Questo esempio usa anche il nuovo operatore `nameof` per convertire il simbolo del nome della proprietà nella rappresentazione di testo.
L'uso di `nameof` può ridurre gli errori nel caso in cui il nome della proprietà sia stato digitato erroneamente.

L'implementazione di <xref:System.ComponentModel.INotifyPropertyChanged> è quindi un esempio di caso in cui è possibile scrivere codice nelle funzioni di accesso per supportare gli scenari necessari.

## <a name="summing-up"></a>Riepilogo

Le proprietà sono una forma di campi intelligenti in una classe o un oggetto. All'esterno dell'oggetto, vengono visualizzate come campi dell'oggetto. Tuttavia, le proprietà possono essere implementate usando l'intera gamma di funzionalità di C#.
È possibile specificare la convalida, un'accessibilità diversa, la valutazione lazy o tutti i requisiti necessari negli scenari.
