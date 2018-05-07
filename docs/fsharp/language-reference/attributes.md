---
title: Attributi (F#)
description: 'Informazioni su come gli attributi di F # Abilita i metadati da applicare a un costrutto di programmazione.'
ms.date: 05/16/2016
ms.openlocfilehash: 107f5d9cbcce28c97fc5b738759ef27649fc45a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="attributes"></a>Attributi

Attributi Abilita i metadati da applicare a un costrutto di programmazione.

## <a name="syntax"></a>Sintassi

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a>Note

Nella sintassi precedente, il *destinazione* è facoltativo e, se presente, specifica il tipo di entità del programma a cui si applica l'attributo. I valori validi per *destinazione* vengono visualizzati nella tabella riportata più avanti in questo documento.

Il *-nome dell'attributo* fa riferimento al nome (eventualmente qualificato con spazi dei nomi) di un tipo di attributo valido, con o senza il suffisso `Attribute` in genere utilizzato nei nomi di tipi di attributo. Ad esempio, il tipo `ObsoleteAttribute` può essere abbreviato semplicemente `Obsolete` in questo contesto.

Il *argomenti* sono gli argomenti del costruttore del tipo di attributo. Se un attributo ha un costruttore predefinito, è possibile omettere l'elenco di argomenti e le parentesi. Gli attributi supportano sia gli argomenti posizionali e argomenti denominati. *Gli argomenti posizionali* sono argomenti utilizzati nell'ordine in cui appaiono. Se l'attributo dispone di proprietà pubbliche, è possono utilizzare argomenti denominati. È possibile impostare questi eventi utilizzando la sintassi seguente nell'elenco di argomenti.

```
*property-name* = *property-value*
```

Tali inizializzazioni delle proprietà possono essere in qualsiasi ordine, ma devono seguire tutti gli argomenti posizionali. Ecco un esempio di un attributo che usa argomenti posizionali e inizializzazioni delle proprietà.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

In questo esempio, l'attributo è `DllImportAttribute`, utilizzato nella forma abbreviata. Il primo argomento è un parametro posizionale e la seconda è una proprietà.

Gli attributi sono un costrutto di programmazione .NET che consente a un oggetto noto come un *attributo* da associare a un tipo o altro elemento del programma. L'elemento di programma a cui viene applicato un attributo è noto come il *la destinazione dell'attributo*. L'attributo è in genere contiene i metadati relativi alla sua destinazione. In questo contesto, i metadati potrebbe essere tutti i dati sul tipo diverso di campi e membri.

Attributi in F # possono essere applicati per i costrutti di programmazione seguenti: funzioni, metodi, assembly, moduli, tipi (classi, record, strutture, interfacce, delegati, enumerazioni, unioni e così via), costruttori, proprietà, campi, parametri, parametri di tipo e valori restituiti. Gli attributi non consentiti su `let` associazioni all'interno di classi, espressioni o espressioni del flusso di lavoro.

In genere, la dichiarazione di attributo viene visualizzato direttamente prima della dichiarazione dell'attributo di destinazione. Insieme, come indicato di seguito, è possono utilizzare più dichiarazioni di attributo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

È possibile eseguire query di attributi in fase di esecuzione tramite la reflection .NET.

È possibile dichiarare più attributi singoli, come nell'esempio di codice precedente, oppure è possibile dichiararli in un set di parentesi, se si utilizza un punto e virgola per separare i singoli attributi e i costruttori, come illustrato di seguito.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

In genere, gli attributi includono il `Obsolete` attributi, gli attributi per motivi di sicurezza, gli attributi per il supporto COM, gli attributi relativi alla proprietà del codice e gli attributi che indica se un tipo può essere serializzato. Nell'esempio seguente viene illustrato l'utilizzo del `Obsolete` attributo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

Per le destinazioni degli attributi `assembly` e `module`, applicare gli attributi di un livello principale `do` associazione dell'assembly. È possibile includere la parola `assembly` o `module` nella dichiarazione di attributo, come indicato di seguito.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

Se si omette l'attributo di destinazione per un attributo applicato a un `do` associazione, il compilatore F # tenta di determinare l'attributo di destinazione appropriato per tale attributo. Molte classi di attributo dispongono di un attributo di tipo `System.AttributeUsageAttribute` che include informazioni sulle possibili destinazioni per l'attributo è supportato. Se il `System.AttributeUsageAttribute` indica che l'attributo supporta le funzioni come destinazione, l'attributo viene applicato al punto di ingresso principale del programma. Se il `System.AttributeUsageAttribute` indica che l'attributo supporta gli assembly come destinazione, il compilatore prende l'attributo da applicare all'assembly. La maggior parte degli attributi non sono applicano per le funzioni e gli assembly, ma nei casi in cui avviene, è necessario l'attributo si applica alla funzione principale del programma. Se l'attributo di destinazione è specificato in modo esplicito, l'attributo viene applicato alla destinazione specificata.

Anche se in genere è necessario specificare l'attributo di destinazione in modo esplicito, i valori validi per *destinazione* in un attributo sono illustrati nella tabella seguente, insieme a esempi di utilizzo.

<table>
  <tr>
    <th>Attributo di destinazione</td>
    <th>Esempio</td> 
  </tr>
  <tr>
    <td>assembly</td>
    <td>`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</td> 
  </tr>
  <tr>
    <td>return</td>
    <td>' function1 let x: [<return: Obsolete>] int = x + 1'</td> 
  </tr>
  <tr>
    <td>campo</td>
    <td>' [<field: DefaultValue>] x: int modificabile val'</td> 
  </tr>
  <tr>
    <td>proprietà</td>
    <td>' [<property: Obsolete>] questo. MyProperty = x'</td> 
  </tr>
  <tr>
    <td>Param</td>
    <td>' membro questo. MyMethod ([<param: Out>] x: ref<int>) = x: = 10"</td> 
  </tr>
  <tr>
    <td>tipo</td>
    <td>
        ```
        [<type: StructLayout(Sequential)>] digitare MyStruct = struct x: y byte: fine int ```
    </td> 
  </tr>
</table>

## <a name="see-also"></a>Vedere anche

[Riferimenti per il linguaggio F#](index.md)
