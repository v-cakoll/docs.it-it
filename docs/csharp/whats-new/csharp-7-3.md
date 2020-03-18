---
title: Novità di C# 7.3
description: Panoramica delle nuove funzionalità in C# 7.3
ms.date: 05/16/2018
ms.openlocfilehash: ba4cea302d91b395e88940d087fcaed306920840
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74204549"
---
# <a name="whats-new-in-c-73"></a>Novità di C# 7.3

Esistono due temi principali per C# versione 7.3. Un tema comprende funzionalità che consentono al codice gestito di offrire prestazioni altrettanto elevate di quelle del codice non gestito. Il secondo tema comprende miglioramenti incrementali delle funzionalità esistenti. Inoltre, in questa versione sono state aggiunte nuove opzioni del compilatore.

Le nuove funzionalità seguenti supportano il tema del miglioramento delle prestazioni per il codice gestito:

- È possibile accedere a campi fissi senza blocco.
- È possibile riassegnare le variabili locali `ref`.
- È possibile usare gli inizializzatori nelle matrici `stackalloc`.
- È possibile usare istruzioni `fixed` con qualsiasi tipo che supporta un modello.
- È possibile usare vincoli generici aggiuntivi.

Sono stati apportati i miglioramenti seguenti alle funzionalità esistenti:

- È possibile testare `==` e `!=` con i tipi di tupla.
- È possibile usare le variabili di espressione in più posizioni.
- È possibile associare gli attributi al campo sottostante delle proprietà implementate automaticamente.
- È stata migliorata la risoluzione del metodo quando gli argomenti sono diversi da `in`.
- La risoluzione dell'overload ora presenta un minor numero di casi ambigui.

Le nuove opzioni del compilatore sono le seguenti:

- `-publicsign` per abilitare la firma degli assembly con software open source.
- `-pathmap` per fornire un mapping per le directory di origine.

Il resto di questo articolo fornisce informazioni dettagliate e collegamenti a risorse aggiuntive per ciascuno dei miglioramenti. È possibile esplorare queste funzionalità nell'ambiente in uso tramite lo strumento globale `dotnet try`:

1. Installare lo strumento globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).
1. Clonare il repository [dotnet/try-samples](https://github.com/dotnet/try-samples).
1. Impostare la directory corrente sulla sottodirectory *csharp7* per il repository *try-samples*.
1. Eseguire `dotnet try`.

## <a name="enabling-more-efficient-safe-code"></a>Miglioramento dell'efficienza del codice gestito

È possibile scrivere codice C# in modo gestito con prestazioni altrettanto elevate di quelle del codice non gestito. Il codice gestito evita classi di errori come sovraccarichi del buffer, puntatori errati e altri errori di accesso alla memoria. Queste nuove funzionalità espandono le capacità del codice gestito verificabile. È possibile scrivere una parte più ampia del codice usando costrutti gestiti. Queste funzionalità rendono più semplice tale attività.

### <a name="indexing-fixed-fields-does-not-require-pinning"></a>I campi di indicizzazione `fixed` non richiedono il blocco

Si prenda in considerazione lo struct seguente:

```csharp
unsafe struct S
{
    public fixed int myFixedField[10];
}
```

Nelle versioni precedenti di C# era necessario bloccare una variabile per accedere a uno dei valori Integer che fanno parte di `myFixedField`. Il codice seguente viene ora compilato senza bloccare la variabile `p` in un'istruzione `fixed` separata:

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        int p = s.myFixedField[5];
    }
}
```

La variabile `p` accede a un elemento `myFixedField`. Non è necessario dichiarare una variabile `int*` distinta. Si noti che è comunque necessario un contesto `unsafe`. Nelle versioni precedenti di C# era necessario dichiarare un secondo puntatore fisso:

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        fixed (int* ptr = s.myFixedField)
        {
            int p = ptr[5];
        }
    }
}
```

Per ulteriori informazioni, vedere l'articolo [ `fixed` sull'istruzione](../language-reference/keywords/fixed-statement.md).

### <a name="ref-local-variables-may-be-reassigned"></a>Le variabili locali `ref` possono essere riassegnate

Ora è possibile riassegnare le variabili locali `ref` per fare riferimento a istanze diverse dopo l'inizializzazione. Il codice seguente ora consente di eseguire la compilazione:

```csharp
ref VeryLargeStruct refLocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

Per ulteriori informazioni, vedere l'articolo sui [`foreach`](../language-reference/keywords/foreach-in.md) [ `ref` resi e `ref` ](../programming-guide/classes-and-structs/ref-returns.md)le variabili locali e l'articolo su .

### <a name="stackalloc-arrays-support-initializers"></a>Le matrici `stackalloc` supportano gli inizializzatori

In precedenza era possibile specificare i valori per gli elementi in una matrice al momento dell'inizializzazione:

```csharp
var arr = new int[3] {1, 2, 3};
var arr2 = new int[] {1, 2, 3};
```

Ora la stessa sintassi può essere applicata alle matrici dichiarate con `stackalloc`:

```csharp
int* pArr = stackalloc int[3] {1, 2, 3};
int* pArr2 = stackalloc int[] {1, 2, 3};
Span<int> arr = stackalloc [] {1, 2, 3};
```

Per altre informazioni, vedere [ `stackalloc` l'articolo dell'operatore.](../language-reference/operators/stackalloc.md)

### <a name="more-types-support-the-fixed-statement"></a>L'istruzione `fixed` è supportata da più tipi

L'istruzione `fixed` supportava un set di tipi limitato. A partire da C# 7.3, qualsiasi tipo che contiene un metodo `GetPinnableReference()` che restituisce `ref T` oppure `ref readonly T` può essere `fixed`. L'aggiunta di questa funzionalità implica che è possibile usare `fixed` con <xref:System.Span%601?displayProperty=nameWithType> e i tipi correlati.

Per altre informazioni, vedere [ `fixed` l'articolo sull'istruzione](../language-reference/keywords/fixed-statement.md) nel riferimento al linguaggio.

### <a name="enhanced-generic-constraints"></a>Miglioramento dei vincoli generici

Ora è possibile specificare il tipo <xref:System.Enum?displayProperty=nameWithType> o <xref:System.Delegate?displayProperty=nameWithType> come vincoli di classe di base per un parametro di tipo.

È inoltre possibile `unmanaged` utilizzare il nuovo vincolo per specificare che un parametro di tipo deve essere un [tipo non gestito](../language-reference/builtin-types/unmanaged-types.md)nullable.

Per ulteriori informazioni, vedere gli articoli sui [ `where` vincoli generici](../language-reference/keywords/where-generic-type-constraint.md) e [sui vincoli sui parametri](../programming-guide/generics/constraints-on-type-parameters.md)di tipo .

L'aggiunta di questi vincoli ai tipi esistenti è una [modifica incompatibile](version-update-considerations.md#incompatible-changes). I tipi generici chiusi potrebbero non soddisfare più questi nuovi vincoli.

## <a name="make-existing-features-better"></a>Miglioramenti delle funzionalità esistenti

Il secondo tema comprende i miglioramenti delle funzionalità del linguaggio. Queste funzionalità migliorano la produttività durante la creazione di codice in C#.

### <a name="tuples-support--and-"></a>Le tuple supportano `==` e `!=`

I tipi di tupla di C# ora supportano `==` e `!=`. Per altre informazioni, vedere la sezione relativa all'[uguaglianza](../tuples.md#equality-and-tuples) nell'articolo sulle [tuple](../tuples.md).

### <a name="attach-attributes-to-the-backing-fields-for-auto-implemented-properties"></a>Associare gli attributi al campo sottostante per le proprietà implementate automaticamente

Questa sintassi ora è supportata:

```csharp
[field: SomeThingAboutFieldAttribute]
public int SomeProperty { get; set; }
```

L'attributo `SomeThingAboutFieldAttribute` viene applicato al campo sottostante generato dal compilatore per `SomeProperty`. Per altre informazioni, vedere la sezione relativa agli [attributi](../programming-guide/concepts/attributes/index.md) nella Guida per programmatori C#.

### <a name="in-method-overload-resolution-tiebreaker"></a>Risoluzione dell'overload del metodo `in`

Quando si aggiungeva il modificatore dell'argomento `in`, questi due metodi causavano un'ambiguità:

```csharp
static void M(S arg);
static void M(in S arg);
```

Ora l'overload in base al valore (il primo nell'esempio precedente) è migliore dalla versione con il riferimento di sola lettura. Per chiamare la versione con l'argomento di riferimento di sola lettura, è necessario includere il modificatore `in` durante la chiamata del metodo.

> [!NOTE]
> Questo comportamento è stato implementato come una correzione di bug. Non si tratta più di una situazione ambigua anche quando la versione del linguaggio è impostata su "7.2".

Per ulteriori informazioni, vedere l'articolo sul [ `in` modificatore](../language-reference/keywords/in-parameter-modifier.md)di parametro .

### <a name="extend-expression-variables-in-initializers"></a>Estensione delle variabili di espressione negli inizializzatori

La sintassi aggiunta in C# 7.0 per consentire le dichiarazioni di variabili `out` è stata estesa in modo da includere inizializzatori di campo, inizializzatori di proprietà, inizializzatori di costruttore e clausole di query. Questo consente l'uso di codice simile al seguente:

```csharp
public class B
{
   public B(int i, out int j)
   {
      j = i;
   }
}

public class D : B
{
   public D(int i) : base(i, out var j)
   {
      Console.WriteLine($"The value of 'j' is {j}");
   }
}
```

### <a name="improved-overload-candidates"></a>Miglioramento dei candidati per l'overload

In ogni versione, le regole di risoluzione dell'overload vengono aggiornate per gestire le situazioni in cui le chiamate di metodi ambigui presentano una scelta "ovvia". Questa versione aggiunge tre nuove regole per aiutare il compilatore a selezionare la scelta ovvia:

1. Quando un gruppo di metodi contiene sia membri di istanza che membri statici, il compilatore ignora i membri di istanza se il metodo è stato richiamato senza un contesto o un ricevitore di istanza. Se il metodo è stato richiamato con un ricevitore di istanza, il compilatore ignora i membri statici. Quando non è presente alcun ricevitore, il compilatore include solo i membri statici in un contesto statico. In caso contrario, include sia i membri statici che quelli di istanza. Quando il ricevitore è in modo ambiguo un'istanza o un tipo, il compilatore include entrambi. Un contesto statico, in cui non è possibile usare un ricevitore di istanza `this` implicito, include il corpo dei membri in cui non è definito `this`, ad esempio i membri statici, nonché i punti in cui non può essere usato `this`, ad esempio gli inizializzatori di campo e gli inizializzatori di costruttore.
1. Quando un gruppo di metodi include alcuni metodi generici i cui argomenti di tipo non soddisfano i vincoli, questi membri vengono rimossi dal set di candidati.
1. Per la conversione di un gruppo di metodi, i metodi candidati il cui tipo restituito non corrisponde al quello del delegato vengono rimossi dal set.

Sarà possibile notare questa modifica solo perché saranno presenti meno errori del compilatore per overload di metodi ambigui quando si sa con certezza quale metodo è preferibile.

## <a name="new-compiler-options"></a>Nuove opzioni del compilatore

Le nuove opzioni del compilatore supportano nuovi scenari di compilazione e DevOps per i programmi in C#.

### <a name="public-or-open-source-signing"></a>Firma pubblica o open source

L'opzione del compilatore `-publicsign` indica al compilatore di firmare l'assembly usando una chiave pubblica. L'assembly viene contrassegnato come firmato, ma la firma proviene dalla chiave pubblica. Questa opzione consente di compilare assembly firmati da progetti open source con una chiave pubblica.

Per altre informazioni, vedere l'articolo sull'[opzione del compilatore -publicsign](../language-reference/compiler-options/publicsign-compiler-option.md).

### <a name="pathmap"></a>pathmap

L'opzione del compilatore `-pathmap` indica al compilatore di sostituire i percorsi di origine dall'ambiente di compilazione con i percorsi di origine mappati. L'opzione `-pathmap` controlla il percorso di origine scritto dal compilatore nei file PDB o per <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.

Per altre informazioni, vedere l'articolo sull'[opzione del compilatore -pathmap](../language-reference/compiler-options/pathmap-compiler-option.md).
