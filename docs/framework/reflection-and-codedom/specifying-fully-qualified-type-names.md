---
title: Specifica di nomi di tipo completi
description: Per un input valido per le operazioni di reflection, usare nomi di tipo completi, che includono specifiche del nome di assembly, specifiche dello spazio dei nomi e nomi di tipi.
ms.date: 02/21/2019
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- reflection, fully qualified type names
- names [.NET Framework], assemblies
- tokens
- BNF
- assemblies [.NET Framework], names
- languages, grammar
- fully qualified type names
- type names
- special characters
- IDENTIFIER
ms.assetid: d90b1e39-9115-4f2a-81c0-05e7e74e5580
ms.openlocfilehash: ff33b6abd31a82c6b80aa794564c5c48648cde63
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865229"
---
# <a name="specifying-fully-qualified-type-names"></a>Specifica di nomi di tipo completi

È necessario specificare nomi di tipi per avere input validi per le diverse operazioni di reflection. Un nome completo consiste in una specifica del nome di assembly, in una specifica dello spazio dei nomi e in un nome di tipo. Le specifiche dei nomi di tipi vengono usate dai metodi, quali <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType> e <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>.

## <a name="grammar-for-type-names"></a>Grammatica per i nomi dei tipi

 La grammatica definisce la sintassi di linguaggi formali. La tabella seguente elenca le regole lessicali che descrivono come riconoscere un input valido. I terminali (ovvero gli elementi che non sono ulteriormente riducibili) vengono visualizzati in lettere maiuscole. I non terminali (ovvero gli elementi che sono ulteriormente riducibili) vengono visualizzati in stringhe miste di maiuscole e minuscole o in stringhe tra virgolette singole, ma la virgoletta singola (') non è parte della sintassi stessa. Il carattere barra verticale (& #124;) indica regole che includono sottoregole.

<!-- markdownlint-disable MD010 -->
```antlr
TypeSpec
    : ReferenceTypeSpec
    | SimpleTypeSpec
    ;

ReferenceTypeSpec
    : SimpleTypeSpec '&'
    ;

SimpleTypeSpec
    : PointerTypeSpec
    | GenericTypeSpec
    | TypeName
    ;

GenericTypeSpec
   : SimpleTypeSpec ` NUMBER

PointerTypeSpec
    : SimpleTypeSpec '*'
    ;

ArrayTypeSpec
    : SimpleTypeSpec '[ReflectionDimension]'
    | SimpleTypeSpec '[ReflectionEmitDimension]'
    ;

ReflectionDimension
    : '*'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

ReflectionEmitDimension
    : '*'
    | Number '..' Number
    | Number '…'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

Number
    : [0-9]+
    ;

TypeName
    : NamespaceTypeName
    | NamespaceTypeName ',' AssemblyNameSpec
    ;

NamespaceTypeName
    : NestedTypeName
    | NamespaceSpec '.' NestedTypeName
    ;

NestedTypeName
    : IDENTIFIER
    | NestedTypeName '+' IDENTIFIER
    ;

NamespaceSpec
    : IDENTIFIER
    | NamespaceSpec '.' IDENTIFIER
    ;

AssemblyNameSpec
    : IDENTIFIER
    | IDENTIFIER ',' AssemblyProperties
    ;

AssemblyProperties
    : AssemblyProperty
    | AssemblyProperties ',' AssemblyProperty
    ;

AssemblyProperty
    : AssemblyPropertyName '=' AssemblyPropertyValue
    ;
```
<!-- markdownlint-enable MD010 -->

## <a name="specifying-special-characters"></a>Specifica di caratteri speciali

In un nome di tipo, IDENTIFIER corrisponde a un qualsiasi nome valido determinato dalle regole di un linguaggio.

Usare la barra rovesciata (\\) come carattere di escape per separare i token seguenti quando vengono usati come parte di IDENTIFIER.

|token|Significato|
|-----------|-------------|
|\\,|Separatore di assembly.|
|\\+|Separatore di tipo annidato.|
|\\&|Tipo di riferimento.|
|\\*|Tipo di puntatore.|
|\\[|Delimitatore delle dimensioni della matrice.|
|\\]|Delimitatore delle dimensioni della matrice.|
|\\.|Usare la barra rovesciata prima di un punto solo se il punto è usato in una specifica di matrice. I punti in NamespaceSpec non accettano la barra rovesciata.|
|\\\|Barra rovesciata se necessaria come stringa letterale.|

Si noti che in tutti i componenti TypeSpec, ad eccezione di AssemblyNameSpec, gli spazi sono rilevanti. In AssemblyNameSpec, gli spazi che precedono il separatore ',' sono rilevanti, ma gli spazi dopo il separatore ',' vengono ignorati.

Le classi reflection, ad esempio <xref:System.Type.FullName%2A?displayProperty=nameWithType>, restituiscono il nome modificato in modo che possa essere usato in una chiamata a <xref:System.Type.GetType%2A>, ad esempio in `MyType.GetType(myType.FullName)`.

Ad esempio, il nome completo per un tipo potrebbe essere `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.

Se lo spazio dei nomi fosse `Ozzy.Out+Back`, il segno di addizione dovrebbe essere preceduto da una barra rovesciata. In caso contrario, il parser lo interpreterebbe come separatore di annidamento. Reflection genera questa stringa come `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.

## <a name="specifying-assembly-names"></a>Specifica dei nomi di assembly

Le informazioni minime necessarie in una specifica di nome di assembly è il nome testuale (IDENTIFIER) dell'assembly. È possibile far seguire l'IDENTIFIER da un elenco delimitato da virgole di coppie proprietà/valore, come descritto nella tabella seguente. La denominazione dell'IDENTIFIER deve seguire le regole di denominazione dei file. La denominazione dell'IDENTIFIER non fa distinzione tra maiuscole e minuscole.

|Nome proprietà|Descrizione|Valori consentiti|
|-------------------|-----------------|----------------------|
|**Version**|Numero di versione dell'assembly|*Major.Minor.Build.Revision*, dove *Major*, *Minor*, *Build* e *Revision* sono numeri interi compresi tra 0 e 65535.|
|**PublicKey**|Chiave pubblica completa|Valore di stringa della chiave pubblica completa in formato esadecimale. Specificare un riferimento Null (**Nothing** in Visual Basic) per indicare in modo esplicito un assembly privato.|
|**PublicKeyToken**|Token di chiave pubblica (hash a 8 byte della chiave pubblica completa)|Valore di stringa del token della chiave pubblica in formato esadecimale. Specificare un riferimento Null (**Nothing** in Visual Basic) per indicare in modo esplicito un assembly privato.|
|**Impostazioni cultura**|Impostazioni cultura dell'assembly|Impostazioni cultura dell'assembly in formato RFC 1766 o "neutral" per gli assembly indipendenti dal linguaggio (non satellite).|
|**Impostazione personalizzata**|BLOB (Binary Large Object, Oggetto binario di grandi dimensioni) personalizzato. Attualmente viene usato solo in assembly generati dal [generatore di immagini native (Ngen)](../tools/ngen-exe-native-image-generator.md).|Stringa personalizzata usata dal generatore di immagini native per notificare alla cache di assembly che l'assembly che si sta installando è un'immagine nativa e deve pertanto essere installato nella cache delle immagini native. Nota anche come stringa zap.|

L'esempio seguente illustra un **AssemblyName** per un assembly a nome semplice con le impostazioni cultura predefinite.

```csharp
com.microsoft.crypto, Culture=""
```

L'esempio seguente illustra un riferimento completo per un assembly con nome sicuro nelle impostazioni cultura "en" (inglese).

```csharp
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

Gli esempi seguenti illustrano un **AssemblyName** parzialmente specificato, che può essere soddisfatto da un assembly con nome sicuro o semplice.

```csharp
com.microsoft.crypto
com.microsoft.crypto, Culture=""
com.microsoft.crypto, Culture=en
```

Gli esempi seguenti illustrano un **AssemblyName** parzialmente specificato, che deve essere soddisfatto da un assembly con nome semplice.

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=null
com.microsoft.crypto, Culture=en, PublicKeyToken=null
```

Gli esempi seguenti illustrano un **AssemblyName** parzialmente specificato, che deve essere soddisfatto da un assembly con nome sicuro.

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=a5d015c7d5a0b012
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

## <a name="specifying-generic-types"></a>Specifica di tipi generici

SimpleTypeSpec\`NUMERO rappresenta un tipo generico aperto con parametri di tipo generico compresi tra 1 e *n*. Per ottenere, ad esempio, un riferimento all'elenco di tipi generici aperti \<T> o all'elenco di tipi generici chiusi \<String> , usare ``Type.GetType("System.Collections.Generic.List`1")`` per ottenere un riferimento al dizionario di tipo generico \<TKey,TValue> , usare ``Type.GetType("System.Collections.Generic.Dictionary`2")`` .

## <a name="specifying-pointers"></a>Specifica dei puntatori

SimpleTypeSpec* rappresenta un puntatore non gestito. Ad esempio, per ottenere un puntatore per il tipo MyType, usare `Type.GetType("MyType*")`. Per ottenere un puntatore a un puntatore per il tipo MyType, usare `Type.GetType("MyType**")`.

## <a name="specifying-references"></a>Specifica dei riferimenti

SimpleTypeSpec & rappresenta un riferimento o puntatore gestito. Ad esempio, per ottenere un riferimento per il tipo MyType, usare `Type.GetType("MyType &")`. Si noti che, a differenza dei puntatori, i riferimenti sono limitati a un solo livello.

## <a name="specifying-arrays"></a>Specifica delle matrici

Nella grammatica BNF, ReflectionEmitDimension si applica solo a definizioni di tipi incomplete recuperate tramite <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>. Le definizioni di tipi incomplete sono oggetti <xref:System.Reflection.Emit.TypeBuilder> costruiti tramite <xref:System.Reflection.Emit?displayProperty=nameWithType> senza chiamare <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType>. ReflectionDimension può essere usato per recuperare qualsiasi definizione di tipo che è stata completata, vale a dire, un tipo che è stato caricato.

Le matrici sono accessibili in reflection specificando l'ordine della matrice:

- `Type.GetType("MyArray[]")` ottiene una matrice unidimensionale con un limite inferiore pari a 0.

- `Type.GetType("MyArray[*]")` ottiene una matrice unidimensionale con un limite inferiore sconosciuto.
- `Type.GetType("MyArray[][]")` ottiene una matrice di matrice bidimensionale.

- `Type.GetType("MyArray[*,*]")` e `Type.GetType("MyArray[,]")` ottengono una matrice rettangolare bidimensionale con limiti inferiori sconosciuti.

Si noti che dal punto di vista del runtime, `MyArray[] != MyArray[*]`, ma per le matrici multidimensionali, le due notazioni sono equivalenti. Vale a dire, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` restituisce **true**.

Per **ModuleBuilder. GetType**, `MyArray[0..5]` indica una matrice a dimensione singola con dimensione 6, limite inferiore 0. `MyArray[4…]` indica una matrice unidimensionale di dimensioni sconosciute e limite inferiore pari a 4.

## <a name="see-also"></a>Vedi anche

- <xref:System.Reflection.AssemblyName>
- <xref:System.Reflection.Emit.ModuleBuilder>
- <xref:System.Reflection.Emit.TypeBuilder>
- <xref:System.Type.FullName%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>
- [Visualizzazione delle informazioni sul tipo](viewing-type-information.md)
