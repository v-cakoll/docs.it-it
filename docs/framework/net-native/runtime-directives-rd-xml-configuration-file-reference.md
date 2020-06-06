---
title: Riferimento a file di configurazione di direttive di runtime (rd.xml)
ms.date: 03/30/2017
ms.assetid: 8241523f-d8e1-4fb6-bf6a-b29bfe07b38a
ms.openlocfilehash: e74d34693446cca645003a9f93bc1777849e3182
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "76738413"
---
# <a name="runtime-directives-rdxml-configuration-file-reference"></a>Riferimento a file di configurazione di direttive di runtime (rd.xml)

Un file di direttive di runtime (rd.xml) è un file di configurazione XML che specifica se gli elementi del programma designato sono disponibili per la reflection. Ecco un esempio di un file di direttive di runtime:

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
    <Namespace Name="Contoso.Cloud.AppServices" Serialize="Required Public" />
    <Namespace Name="ContosoClient.ViewModels" Serialize="Required Public" />
    <Namespace Name="ContosoClient.DataModel" Serialize="Required Public" />
    <Namespace Name="Contoso.Reader.UtilityLib" Serialize="Required Public" />

    <Namespace Name="System.Collections.ObjectModel" >
      <TypeInstantiation Name="ObservableCollection"
            Arguments="ContosoClient.DataModel.ProductItem" Serialize="Public" />
      <TypeInstantiation Name="ReadOnlyObservableCollection"
            Arguments="ContosoClient.DataModel.ProductGroup" Serialize="Public" />
    </Namespace>
  </Application>
</Directives>
```

## <a name="the-structure-of-a-runtime-directives-file"></a>La struttura di un file di direttive di runtime

Il file di direttive di runtime usa lo spazio dei nomi `http://schemas.microsoft.com/netfx/2013/01/metadata`.

L'elemento radice è l'elemento [Directives](directives-element-net-native.md). Può contenere zero o più elementi [Library](library-element-net-native.md) e zero o un elemento [Application](application-element-net-native.md), come illustrato nella struttura seguente. Gli attributi dell'elemento [Application](application-element-net-native.md) possono definire criteri di reflection di runtime a livello di applicazione oppure possono fungere da contenitore per gli elementi figlio. L'elemento [Library](library-element-net-native.md), invece, è semplicemente un contenitore. Gli elementi figlio degli elementi [Application](application-element-net-native.md) e [Library](library-element-net-native.md) definiscono i tipi, i metodi, i campi, le proprietà e gli eventi disponibili per la reflection.

Per le informazioni di riferimento, scegliere gli elementi dalla struttura seguente o vedere [Elementi direttiva di runtime](runtime-directive-elements.md). Nella seguente gerarchia, i puntini di sospensione contrassegnano una struttura ricorsiva. Le informazioni tra parentesi quadre indicano se tale elemento è facoltativo oppure obbligatorio e, se viene usato, il numero di istanze consentito (una o molte).

- [Directives](directives-element-net-native.md) [1:1]
  - [Application](application-element-net-native.md) [0:1]
    - [Assembly](assembly-element-net-native.md) [0:M]
      - [Spazio dei nomi](namespace-element-net-native.md) [0: M]. . .
      - [Digitare](type-element-net-native.md) [0: M]. . .
      - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0: M]. . .
    - [Namespace](namespace-element-net-native.md) [0:M]
      - [Spazio dei nomi](namespace-element-net-native.md) [0: M]. . .
      - [Digitare](type-element-net-native.md) [0: M]. . .
      - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0: M]. . .
    - [Type](type-element-net-native.md) [0:M]
      - [Subtypes](subtypes-element-net-native.md) (sottoclassi del tipo contenitore) [O:1]
      - [Digitare](type-element-net-native.md) [0: M]. . .
      - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0: M]. . .
      - [AttributeImplies](attributeimplies-element-net-native.md) (il tipo contenitore è un attributo) [O:1]
      - [GenericParameter](genericparameter-element-net-native.md) [0:M]
      - [Method](method-element-net-native.md) [0:M]
        - [Parameter](parameter-element-net-native.md) [0:M]
        - [TypeParameter](typeparameter-element-net-native.md) [0:M]
        - [GenericParameter](genericparameter-element-net-native.md) [0:M]
      - [MethodInstantiation](methodinstantiation-element-net-native.md) (metodo generico costruito) [0:M]
      - [Property](property-element-net-native.md) [0:M]
      - [Field](field-element-net-native.md) [0:M]
      - [Event](event-element-net-native.md) [0:M]
    - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0:M]
      - [Digitare](type-element-net-native.md) [0: M]. . .
      - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0: M]. . .
      - [Method](method-element-net-native.md) [0:M]
        - [Parameter](parameter-element-net-native.md) [0:M]
        - [TypeParameter](typeparameter-element-net-native.md) [0:M]
        - [GenericParameter](genericparameter-element-net-native.md) [0:M]
      - [MethodInstantiation](methodinstantiation-element-net-native.md) (metodo generico costruito) [0:M]
      - [Property](property-element-net-native.md) [0:M]
      - [Field](field-element-net-native.md) [0:M]
      - [Event](event-element-net-native.md) [0:M]
  - [Library](library-element-net-native.md) [0:M]
    - [Assembly](assembly-element-net-native.md) [0:M]
      - [Spazio dei nomi](namespace-element-net-native.md) [0: M]. . .
      - [Digitare](type-element-net-native.md) [0: M]. . .
      - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0: M]. . .
    - [Namespace](namespace-element-net-native.md) [0:M]
      - [Spazio dei nomi](namespace-element-net-native.md) [0: M]. . .
      - [Digitare](type-element-net-native.md) [0: M]. . .
      - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0: M]. . .
    - [Type](type-element-net-native.md) [0:M]
      - [Subtypes](subtypes-element-net-native.md) (sottoclassi del tipo contenitore) [O:1]
      - [Digitare](type-element-net-native.md) [0: M]. . .
      - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0: M]. . .
      - [AttributeImplies](attributeimplies-element-net-native.md) (il tipo contenitore è un attributo) [O:1]
      - [GenericParameter](genericparameter-element-net-native.md) [0:M]
      - [Method](method-element-net-native.md) [0:M]
      - [MethodInstantiation](methodinstantiation-element-net-native.md) (metodo generico costruito) [0:M]
      - [Property](property-element-net-native.md) [0:M]
      - [Field](field-element-net-native.md) [0:M]
      - [Event](event-element-net-native.md) [0:M]
    - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0:M]
      - [Digitare](type-element-net-native.md) [0: M]. . .
      - [TypeInstantiation](typeinstantiation-element-net-native.md) (tipo generico costruito) [0: M]. . .
      - [Method](method-element-net-native.md) [0:M]
      - [MethodInstantiation](methodinstantiation-element-net-native.md) (metodo generico costruito) [0:M]
      - [Property](property-element-net-native.md) [0:M]
      - [Field](field-element-net-native.md) [0:M]
      - [Event](event-element-net-native.md) [0:M]

L'elemento [Application](application-element-net-native.md) può non avere attributi oppure può avere gli attributi dei criteri descritti nella sezione [Direttive e criteri di runtime](#Directives).

Un elemento [Library](library-element-net-native.md) ha un solo attributo, `Name`, che specifica il nome di una libreria o di un assembly, senza l'estensione del file. Ad esempio, l'elemento [Library](library-element-net-native.md) seguente si applica a un assembly denominato Extensions.dll.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
     <!-- Child elements go here -->
  </Application>
  <Library Name="Extensions">
     <!-- Child elements go here -->
  </Library>
</Directives>
```

<a name="Directives"></a>

## <a name="runtime-directives-and-policy"></a>Direttive e criteri di runtime

L'elemento [Application](application-element-net-native.md) stesso e gli elementi figlio degli elementi [Library](library-element-net-native.md) e [Application](application-element-net-native.md) esprimono criteri, ovvero definiscono il modo in cui un'app può applicare la reflection a un elemento del programma. Il tipo di criterio è definito da un attributo dell'elemento (ad esempio, `Serialize`). Il valore di criterio è definito dal valore dell'attributo (ad esempio, `Serialize="Required"`).

Qualsiasi criterio specificato da un attributo di un elemento si applica a tutti gli elementi figlio che non specificano un valore per tale criterio. Ad esempio, se vengono specificati criteri da un elemento [Type](type-element-net-native.md), tali criteri si applicano a tutti i tipi e membri contenuti per i quali non sono stati esplicitamente specificati i criteri.

I criteri che possono essere espressi dagli elementi [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) e [Type](type-element-net-native.md) differiscono da quelli che possono essere espressi per i singoli membri (dagli elementi [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md) ed [Event](event-element-net-native.md)).

### <a name="specifying-policy-for-assemblies-namespaces-and-types"></a>Specifica di criteri per assembly, spazi dei nomi e tipi

Gli elementi [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) e [Type](type-element-net-native.md) supportano i tipi di criteri seguenti:

- `Activate`. Controlla l'accesso in fase di esecuzione ai costruttori per abilitare l'attivazione di istanze.

- `Browse`. Controlla le query per le informazioni sugli elementi di programma, ma non abilita l'accesso in fase di esecuzione.

- `Dynamic`. Controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica.

- `Serialize`. Controlla l'accesso in fase di esecuzione ai costruttori, ai campi e alle proprietà per abilitare la serializzazione e la deserializzazione delle istanze del tipo da parte di librerie di terze parti, ad esempio il serializzatore JSON di Newtonsoft.

- `DataContractSerializer`. Controlla i criteri per la serializzazione che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.

- `DataContractJsonSerializer`. Controlla i criteri per la serializzazione JSON che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.

- `XmlSerializer`. Controlla i criteri per la serializzazione XML che usano la classe <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.

- `MarshalObject`. Criteri di controlli per effettuare il marshalling dei tipi di riferimento per WinRT e COM.

- `MarshalDelegate`. Controlla i criteri per effettuare il marshalling dei tipi delegati come puntatori a funzioni al codice nativo.

- `MarshalStructure` . Controlla i criteri per effettuare il marshalling delle strutture al codice nativo.

Le impostazioni associate a questi tipi di criteri sono:

- `All`. Attivare il criterio per tutti i tipi e membri che la catena di strumenti non riesce a rimuovere.

- `Auto`. Usare il comportamento predefinito (non specificare un criterio è equivalente a impostare tale criterio su `Auto` a meno che tale criterio sia sottoposto a override, ad esempio da un elemento padre).

- `Excluded`. Disattivare il criterio per l'elemento di programma.

- `Public`. Attivare i criteri per i tipi o i membri pubblici, a meno che la catena di strumenti non determini che il tipo o il membro non è necessario e lo rimuova (in quest'ultimo caso, è necessario usare `Required Public` per garantire che il membro venga mantenuto e abbia funzionalità di reflection.)

- `PublicAndInternal`. Attivare il criterio per i tipi o membri pubblici e interni se la catena di strumenti non li rimuove.

- `Required Public`. Richiedere che la catena di strumenti mantenga i tipi e i membri pubblici, indipendentemente dal fatto che vengano usati o no, e attivare i relativi criteri.

- `Required PublicAndInternal`. Richiedere che la catena di strumenti mantenga i tipi e i membri pubblici e interni, indipendentemente dal fatto che vengano usati o no, e attivare i relativi criteri.

- `Required All`. Richiedere che la catena di strumenti mantenga tutti i tipi e i membri, indipendentemente dal fatto che vengano usati o no, e attivare i relativi criteri.

Il seguente file di direttive di runtime, ad esempio, definisce i criteri per tutti i tipi e membri nell'assembly DataClasses.dll. Consente la reflection per la serializzazione di tutte le proprietà pubbliche, consente di cercare tutti i tipi e membri del tipo, consente l'attivazione per tutti i tipi (a causa dell'attributo `Dynamic`) e abilita la reflection per tutti i tipi e membri pubblici.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"
                Browse="All" Activate="PublicAndInternal"
                Dynamic="Public"  />
   </Application>
   <Library Name="UtilityLibrary">
     <!-- Child elements go here -->
   </Library>
</Directives>
```

### <a name="specifying-policy-for-members"></a>Specifica di criteri per i membri

Gli elementi [Property](property-element-net-native.md) e [Field](field-element-net-native.md) supportano i tipi di criteri seguenti:

- `Browse`: controlla le query per le informazioni su questo membro, ma non abilita l'accesso in fase di esecuzione.

- `Dynamic`: controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica. Controlla anche la ricerca di informazioni sul tipo contenitore.

- `Serialize`: controlla l'accesso in fase di esecuzione al membro per abilitare istanze di tipi da serializzare e deserializzare da parte di librerie quali il serializzatore JSON di Newtonsoft. Questi criteri possono essere applicati a costruttori, campi e proprietà.

Gli elementi [Method](method-element-net-native.md) ed [Event](event-element-net-native.md) supportano i tipi di criteri seguenti:

- `Browse`: controlla le query per le informazioni su questo membro, ma non abilita l'accesso in fase di esecuzione.

- `Dynamic`: controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica. Controlla anche la ricerca di informazioni sul tipo contenitore.

 Le impostazioni associate a questi tipi di criteri sono:

- `Auto`: usare il comportamento predefinito (non specificare un criterio equivale a impostare tale criterio su `Auto` a meno che un elemento esegua l'override).

- `Excluded`: non includere mai i metadati per il membro.

- `Included`: abilitare il criterio se il tipo padre è presente nell'output.

- `Required`: richiedere che la catena di strumenti conservi questo membro anche se sembra non essere in uso e abilitare i relativi criteri.

## <a name="runtime-directives-file-semantics"></a>Semantica dei file di runtime direttive

È possibile definire criteri contemporaneamente per gli elementi di livello più alto e più basso. Ad esempio, è possibile definire dei criteri per un assembly e per alcuni dei tipi di contenuti in tale assembly. Se non è rappresentato un particolare elemento di livello inferiore, esso eredita i criteri del padre. Ad esempio, se è presente un elemento `Assembly`, ma gli elementi `Type` sono assenti, il criterio specificato nell'elemento `Assembly` viene applicato a ciascun tipo nell'assembly. Più elementi possono anche applicare criteri allo stesso elemento di programma. Ad esempio, elementi [Assembly](assembly-element-net-native.md) separati potrebbero definire lo stesso elemento di criteri per lo stesso assembly in modo diverso. Le sezioni seguenti spiegano come risolvere il criterio per un determinato tipo in questi casi.

Un elemento [Type](type-element-net-native.md) o [Method](method-element-net-native.md) di un tipo o un metodo generico applica i relativi criteri a tutte le istanze che non hanno criteri propri. Ad esempio, un elemento `Type` che specifica i criteri per <xref:System.Collections.Generic.List%601> si applica a tutte le istanze costruite di tale tipo generico, a meno che non venga eseguito l'override per un particolare tipo generico costruito (come `List<Int32>`) da un elemento `TypeInstantiation`. In caso contrario, gli elementi definiscono i criteri per l'elemento di programma denominato.

Quando un elemento è ambiguo, il motore ricerca corrispondenze e, se ne trova di esatte, le usa. Se trova più corrispondenze, si riceverà un avviso o un errore.

### <a name="if-two-directives-apply-policy-to-the-same-program-element"></a>Se due direttive applicano criteri allo stesso elemento di programma

Se due elementi in diversi file di direttive di runtime provano a impostare lo stesso tipo di criteri per lo stesso elemento di programma (ad esempio un tipo o assembly) su valori diversi, il conflitto viene risolto come segue:

1. Se l'elemento `Excluded` è presente, ha la precedenza.

2. `Required` ha la precedenza su non `Required`.

3. `All` ha la precedenza su `PublicAndInternal`, che a sua volta ha la precedenza su `Public`.

4. Qualsiasi impostazione esplicita ha la precedenza su `Auto`.

Ad esempio, se un singolo progetto include i due file di direttive di runtime seguenti, i criteri di serializzazione per DataClasses.dll vengono impostati su `Required Public` e `All`. In questo caso, il criterio di serializzazione sarebbe risolto come `Required All`.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"/>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="All" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

Tuttavia, se due direttive in un unico file di direttive di runtime prova a impostare lo stesso tipo di criteri per l'elemento del programma stesso, lo strumento di definizione di schema XML visualizza un messaggio di errore.

### <a name="if-child-and-parent-elements-apply-the-same-policy-type"></a>Se gli elementi figlio e padre applicano lo stesso tipo di criteri

Gli elementi figlio eseguono l'override dei relativi elementi padre, inclusa l'impostazione `Excluded`. L'override è il motivo principale per cui è preferibile specificare `Auto`.

Nell'esempio seguente, l'impostazione dei criteri di serializzazione per tutto quanto presente in `DataClasses` ma assente in `DataClasses.ViewModels` corrisponderebbe a `Required Public`, e tutto quanto presente sia in `DataClasses` sia in `DataClasses.ViewModels` corrisponderebbe a `All`.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="if-open-generics-and-instantiated-elements-apply-the-same-policy-type"></a>Se i generics aperti e gli elementi di un'istanza applicano lo stesso tipo di criteri

Nell'esempio seguente, a `Dictionary<int,int>` viene assegnato il criterio `Browse` solo se il motore ha un motivo differente per assegnare il criterio `Browse` (che altrimenti sarebbe il comportamento predefinito). Per qualsiasi altra istanza di <xref:System.Collections.Generic.Dictionary%602> sarà possibile esplorare tutti i membri.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
      <Namespace Name="DataClasses.Generics" />
      <Type Name="Dictionary" Browse="All" />
      <TypeInstantiation Name="Dictionary"
                         Arguments="System.Int32,System.Int32" Browse="Auto" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="how-policy-is-inferred"></a>Come vengono dedotti i criteri

Ogni tipo di criteri ha un diverso insieme di regole che determinano in che modo la presenza di tale tipo di criterio ha effetto su altri costrutti.

#### <a name="the-effect-of-browse-policy"></a>Effetto del criterio Browse

L'applicazione del criterio `Browse` a un tipo implica le seguenti modifiche:

- Il tipo di base del tipo viene contrassegnato con il criterio `Browse`.

- Se il tipo è un generico istanziato, la versione priva di istanze del tipo è contrassegnata con il criterio `Browse`.

- Se il tipo è un delegato, il metodo `Invoke` del tipo è contrassegnato con il criterio `Dynamic`.

- Ciascuna interfaccia del tipo viene contrassegnata con il criterio `Browse`.

- Il tipo di ciascun attributo applicato al tipo è contrassegnato con il criterio `Browse`.

- Se il tipo è generico, ogni tipo di vincolo è contrassegnato con il criterio `Browse`.

- Se il tipo è generico, i tipi su cui viene creata un'istanza del tipo sono contrassegnati con il criterio `Browse`.

L'applicazione del criterio `Browse` a un metodo implica le seguenti modifiche:

- Ogni tipo di parametro del metodo è contrassegnato con il criterio `Browse`.

- Il tipo restituito del metodo è contrassegnato con il criterio `Browse`.

- Il tipo contenitore del metodo è contrassegnato con il criterio `Browse`.

- Se il metodo è un metodo generico istanziato, il metodo generico privo di istanze è contrassegnato con il criterio `Browse`.

- Il tipo di ciascun attributo applicato al metodo è contrassegnato con il criterio `Browse`.

- Se il metodo è generico, ogni tipo di vincolo è contrassegnato con il criterio `Browse`.

- Se il metodo è generico, i tipi su cui viene creata un'istanza del metodo sono contrassegnati con il criterio `Browse`.

L'applicazione del criterio `Browse` a un campo implica le seguenti modifiche:

- Il tipo di ciascun attributo applicato al campo è contrassegnato con il criterio `Browse`.

- Il tipo del campo viene contrassegnato con il criterio `Browse`.

- Il tipo al quale appartiene il campo viene contrassegnato con il criterio `Browse`.

#### <a name="the-effect-of-dynamic-policy"></a>Effetto dei criteri Dynamic

L'applicazione del criterio `Dynamic` a un tipo implica le seguenti modifiche:

- Il tipo di base del tipo viene contrassegnato con il criterio `Dynamic`.

- Se il tipo è un generico istanziato, la versione priva di istanze del tipo è contrassegnata con il criterio `Dynamic`.

- Se il tipo è un delegato, il metodo `Invoke` del tipo è contrassegnato con il criterio `Dynamic`.

- Ciascuna interfaccia del tipo viene contrassegnata con il criterio `Browse`.

- Il tipo di ciascun attributo applicato al tipo è contrassegnato con il criterio `Browse`.

- Se il tipo è generico, ogni tipo di vincolo è contrassegnato con il criterio `Browse`.

- Se il tipo è generico, i tipi su cui viene creata un'istanza del tipo sono contrassegnati con il criterio `Browse`.

L'applicazione del criterio `Dynamic` a un metodo implica le seguenti modifiche:

- Ogni tipo di parametro del metodo è contrassegnato con il criterio `Browse`.

- Il tipo restituito del metodo è contrassegnato con il criterio `Dynamic`.

- Il tipo contenitore del metodo è contrassegnato con il criterio `Dynamic`.

- Se il metodo è un metodo generico istanziato, il metodo generico privo di istanze è contrassegnato con il criterio `Browse`.

- Il tipo di ciascun attributo applicato al metodo è contrassegnato con il criterio `Browse`.

- Se il metodo è generico, ogni tipo di vincolo è contrassegnato con il criterio `Browse`.

- Se il metodo è generico, i tipi su cui viene creata un'istanza del metodo sono contrassegnati con il criterio `Browse`.

- Il metodo può essere richiamato da `MethodInfo.Invoke` e la creazione del delegato è resa possibile da <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.

L'applicazione del criterio `Dynamic` a un campo implica le seguenti modifiche:

- Il tipo di ciascun attributo applicato al campo è contrassegnato con il criterio `Browse`.

- Il tipo del campo viene contrassegnato con il criterio `Dynamic`.

- Il tipo al quale appartiene il campo viene contrassegnato con il criterio `Dynamic`.

#### <a name="the-effect-of-activation-policy"></a>Effetto del criterio Activation

L'applicazione del criterio Activation a un tipo implica le seguenti modifiche:

- Se il tipo è un generico istanziato, la versione priva di istanze del tipo è contrassegnata con il criterio `Browse`.

- Se il tipo è un delegato, il metodo `Invoke` del tipo è contrassegnato con il criterio `Dynamic`.

- I costruttori del tipo vengono contrassegnati con il criterio `Activation`.

L'applicazione del criterio `Activation` a un metodo implica le seguenti modifiche:

- Il costruttore può essere richiamato dai metodi <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> e <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>. Per i metodi, il criterio `Activation` influisce solo sui costruttori.

L'applicazione del criterio `Activation` a un campo non ha alcun effetto.

#### <a name="the-effect-of-serialize-policy"></a>Effetto del criterio Serialize

Il criterio `Serialize` consente l'utilizzo dei serializzatori basati su reflection più comuni. Tuttavia, poiché gli schemi di accesso alla reflection esatti dei serializzatori non Microsoft non sono noti a Microsoft, questo criterio potrebbe non essere completamente efficace.

L'applicazione del criterio `Serialize` a un tipo implica le seguenti modifiche:

- Il tipo di base del tipo viene contrassegnato con il criterio `Serialize`.

- Se il tipo è un generico istanziato, la versione priva di istanze del tipo è contrassegnata con il criterio `Browse`.

- Se il tipo è un delegato, il metodo `Invoke` del tipo è contrassegnato con il criterio `Dynamic`.

- Se il tipo è un'enumerazione, una matrice del tipo è contrassegnata con il criterio `Serialize`.

- Se il tipo implementa <xref:System.Collections.Generic.IEnumerable%601>, `T` viene contrassegnato con il criterio `Serialize`.

- Se il tipo è <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601> o <xref:System.Collections.Generic.IReadOnlyList%601>, `T[]` e <xref:System.Collections.Generic.List%601> vengono contrassegnati con il criterio `Serialize`, ma nessuno membro del tipo di interfaccia viene contrassegnato con il criterio `Serialize`.

- Se il tipo è <xref:System.Collections.Generic.List%601>, nessun membro del tipo viene contrassegnato con il criterio `Serialize`.

- Se il tipo è <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> viene contrassegnato con il criterio `Serialize`, ma nessun membro del tipo viene contrassegnato con il criterio `Serialize`.

- Se il tipo è <xref:System.Collections.Generic.Dictionary%602>, nessun membro del tipo viene contrassegnato con il criterio `Serialize`.

- Se il tipo implementa <xref:System.Collections.Generic.IDictionary%602>, `TKey` e `TValue` vengono contrassegnati con il criterio `Serialize`.

- Ogni costruttore, ogni funzione di accesso della proprietà e ogni campo è contrassegnato con il criterio `Serialize`.

L'applicazione del criterio `Serialize` a un metodo implica le seguenti modifiche:

- Il tipo contenitore è contrassegnato con il criterio `Serialize`.

- Il tipo restituito del metodo è contrassegnato con il criterio `Serialize`.

L'applicazione del criterio `Serialize` a un campo implica le seguenti modifiche:

- Il tipo contenitore è contrassegnato con il criterio `Serialize`.

- Il tipo del campo viene contrassegnato con il criterio `Serialize`.

#### <a name="the-effect-of-xmlserializer-datacontractserializer-and-datacontractjsonserializer-policies"></a>Effetto dei criteri XmlSerializer, DataContractSerializer e DataContractJsonSerializer

A differenza del `Serialize` criterio, che è destinato ai serializzatori basati su Reflection, i <xref:System.Xml.Serialization.XmlSerializer> <xref:System.Runtime.Serialization.DataContractSerializer> criteri, e <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> vengono utilizzati per abilitare un set di serializzatori noti alla catena di strumenti .NET native. Questi serializzatori non vengono implementati tramite reflection, ma l'insieme di tipi che possono essere serializzati in fase di esecuzione è determinato in modo simile come tipi soggetti a reflection.

L'applicazione di uno di questi criteri a un tipo consente di serializzare il tipo con il serializzatore corrispondente. Inoltre, eventuali tipi che il motore di serializzazione determina come serializzabili saranno indicati come tali.

Questi criteri non hanno alcun effetto sui metodi o campi.

Per altre informazioni, vedere la sezione relativa alle differenze nei serializzatori in [Migrating Your Windows Store App to .NET Native](migrating-your-windows-store-app-to-net-native.md) (Migrazione dell'app di Windows Store a .NET Native).

## <a name="see-also"></a>Vedi anche

- [Elementi direttiva di runtime](runtime-directive-elements.md)
- [Reflection e .NET Native](reflection-and-net-native.md)
