---
title: Attributes
description: Informazioni su F# come gli attributi consentono l'applicazione dei metadati a un costrutto di programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: 1e42dc61d44f31930a7b34799f28a68a2db69c8c
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504110"
---
# <a name="attributes"></a>Attributes

Gli attributi consentono di applicare i metadati a un costrutto di programmazione.

## <a name="syntax"></a>Sintassi

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a>Osservazioni

Nella sintassi precedente, la *destinazione* è facoltativa e, se presente, specifica il tipo di entità programma a cui si applica l'attributo. I valori validi per la *destinazione* sono illustrati nella tabella riportata più avanti in questo documento.

Il *nome dell'attributo* fa riferimento al nome (possibilmente qualificato con gli spazi dei nomi) di un tipo di attributo valido, con o senza il suffisso `Attribute` usato in genere nei nomi dei tipi di attributo. Il tipo `ObsoleteAttribute`, ad esempio, può essere abbreviato in modo da `Obsolete` solo in questo contesto.

Gli *argomenti* sono gli argomenti del costruttore per il tipo di attributo. Se un attributo ha un costruttore senza parametri, è possibile omettere l'elenco di argomenti e le parentesi. Gli attributi supportano sia gli argomenti posizionali che gli argomenti denominati. Gli *argomenti posizionali* sono argomenti utilizzati nell'ordine in cui sono visualizzati. Gli argomenti denominati possono essere utilizzati se l'attributo dispone di proprietà pubbliche. È possibile impostarle usando la sintassi seguente nell'elenco di argomenti.

```fsharp
property-name = property-value
```

Tali inizializzazioni di proprietà possono essere in qualsiasi ordine, ma devono seguire qualsiasi argomento posizionale. Di seguito è riportato un esempio di un attributo che usa gli argomenti posizionali e le inizializzazioni delle proprietà:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

In questo esempio l'attributo è `DllImportAttribute`, in questo caso viene usato in formato abbreviato. Il primo argomento è un parametro posizionale e il secondo è una proprietà.

Gli attributi sono un costrutto di programmazione .NET che consente a un oggetto noto come *attributo* di essere associato a un tipo o a un altro elemento del programma. L'elemento Program a cui è applicato un attributo è noto come *destinazione dell'attributo*. L'attributo contiene in genere i metadati sulla relativa destinazione. In questo contesto, i metadati possono essere di qualsiasi tipo, ad eccezione dei relativi campi e membri.

Gli attributi F# in possono essere applicati ai seguenti costrutti di programmazione: funzioni, metodi, assembly, moduli, tipi (classi, record, strutture, interfacce, delegati, enumerazioni, unioni e così via), costruttori, proprietà, campi, parametri, parametri di tipo e valori restituiti. Gli attributi non sono consentiti nelle associazioni `let` all'interno di classi, espressioni o espressioni del flusso di lavoro.

In genere, la dichiarazione di attributo viene visualizzata direttamente prima della dichiarazione della destinazione dell'attributo. È possibile utilizzare contemporaneamente più dichiarazioni di attributo, come indicato di seguito:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

È possibile eseguire query sugli attributi in fase di esecuzione usando la reflection .NET.

È possibile dichiarare più attributi singolarmente, come nell'esempio di codice precedente, oppure è possibile dichiararli in un set di parentesi quadre se si usa un punto e virgola per separare i singoli attributi e costruttori, come indicato di seguito:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

Gli attributi rilevati in genere includono l'attributo `Obsolete`, gli attributi per considerazioni sulla sicurezza, gli attributi per il supporto COM, gli attributi correlati alla proprietà del codice e gli attributi che indicano se un tipo può essere serializzato. Nell'esempio seguente viene illustrato l'utilizzo dell'attributo `Obsolete`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

Per le destinazioni degli attributi `assembly` e `module`, applicare gli attributi a un'associazione di `do` di primo livello nell'assembly. È possibile includere la parola `assembly` o `module` nella dichiarazione dell'attributo, come indicato di seguito:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

Se si omette la destinazione dell'attributo per un attributo applicato a un `do` binding, F# il compilatore tenta di determinare la destinazione dell'attributo che ha senso per tale attributo. Molte classi Attribute hanno un attributo di tipo `System.AttributeUsageAttribute` che include informazioni sulle possibili destinazioni supportate per tale attributo. Se il `System.AttributeUsageAttribute` indica che l'attributo supporta funzioni come destinazioni, l'attributo viene accettato per essere applicato al punto di ingresso principale del programma. Se il `System.AttributeUsageAttribute` indica che l'attributo supporta gli assembly come destinazioni, il compilatore accetta l'attributo da applicare all'assembly. La maggior parte degli attributi non si applica sia alle funzioni che agli assembly, ma nei casi in cui lo fanno, l'attributo viene accettato per essere applicato alla funzione principale del programma. Se la destinazione dell'attributo viene specificata in modo esplicito, l'attributo viene applicato alla destinazione specificata.

Anche se in genere non è necessario specificare la destinazione dell'attributo in modo esplicito, i valori validi per la *destinazione* in un attributo insieme ad esempi di utilizzo sono illustrati nella tabella seguente:

<table>
  <tr>
    <th>Destinazione attributo</td>
    <th>Esempio</td>
  </tr>
  <tr>
    <td>assembly</td>
    <td><pre lang="fsharp"><code>[&lt;assembly: AssemblyVersionAttribute("1.0.0.0")&gt;]</code></pre></td>
  </tr>
  <tr>
    <td>return</td>
    <td><pre lang="fsharp"><code>let function1 x : [&lt;return: Obsolete&gt;] int = x + 1</code></pre></td>
  </tr>
  <tr>
    <td>campo</td>
    <td><pre lang="fsharp"><code>[&lt;field: DefaultValue&gt;] val mutable x: int</code></pre></td>
  </tr>
  <tr>
    <td>proprietà</td>
    <td><pre lang="fsharp"><code>[&lt;property: Obsolete&gt;] this.MyProperty = x</code></pre></td>
  </tr>
  <tr>
    <td>param</td>
    <td><pre lang="fsharp"><code>member this.MyMethod([&lt;param: Out&gt;] x : ref&lt;int&gt;) = x := 10</code></pre></td>
  </tr>
  <tr>
    <td>type</td>
    <td>
        <pre lang="fsharp"><code>
[&lt;type: StructLayout(LayoutKind.Sequential)&gt;]
type MyStruct =
  struct
    val x : byte
    val y : int
  end</code></pre>
    </td>
  </tr>
</table>

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
