---
title: Algoritmo di caricamento degli assembly gestiti-.NET Core
description: Descrizione dei dettagli dell'algoritmo di caricamento dell'assembly gestito in .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 312a320676be6eb453697e0704ab771a6707618b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973506"
---
# <a name="managed-assembly-loading-algorithm"></a>Algoritmo di caricamento assembly gestito

Gli assembly gestiti vengono individuati e caricati con un algoritmo che prevede varie fasi.

Tutti gli assembly gestiti ad eccezione degli assembly satellite e degli assembly `WinRT` utilizzano lo stesso algoritmo.

## <a name="when-are-managed-assemblies-loaded"></a>Quando vengono caricati gli assembly gestiti?

Il meccanismo più comune per attivare un caricamento dell'assembly gestito è un riferimento a un assembly statico. Questi riferimenti vengono inseriti dal compilatore ogni volta che il codice utilizza un tipo definito in un altro assembly. Questi assembly vengono caricati (`load-by-name`) in base alle esigenze del runtime.

Anche l'uso diretto di API specifiche attiverà i caricamenti:

|API  |Descrizione  |`Active` <xref:System.Runtime.Loader.AssemblyLoadContext> |
|---------|---------|---------|
|<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromAssemblyName%2A?displayProperty=nameWithType>|`Load-by-name`|Istanza [di](../../csharp/language-reference/keywords/this.md) .|
|<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromAssemblyPath%2A?displayProperty=nameWithType><p><xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromNativeImagePath%2A?displayProperty=nameWithType>|Carica da percorso.|Istanza [di](../../csharp/language-reference/keywords/this.md) .|
<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromStream%2A?displayProperty=nameWithType>|Caricamento da un oggetto.|Istanza [di](../../csharp/language-reference/keywords/this.md) .|
|<xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType>|Carica da percorso in una nuova istanza di <xref:System.Runtime.Loader.AssemblyLoadContext>|Nuova istanza di <xref:System.Runtime.Loader.AssemblyLoadContext>.|
<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>|Carica da percorso nell'istanza di <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.<p>Aggiunge un gestore di <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving> al <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>. Il gestore caricherà le dipendenze dell'assembly dalla relativa directory.|Istanza di <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.|
|<xref:System.Reflection.Assembly.Load(System.Reflection.AssemblyName)?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.Load(System.String)?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>|`Load-by-name`|Dedotto dal chiamante.<p>Preferisce <xref:System.Runtime.Loader.AssemblyLoadContext> metodi.|
|<xref:System.Reflection.Assembly.Load(System.Byte[])?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.Load(System.Byte[],System.Byte[])?displayProperty=nameWithType>|Caricamento da un oggetto in una nuova istanza di <xref:System.Runtime.Loader.AssemblyLoadContext>.|Nuova istanza di <xref:System.Runtime.Loader.AssemblyLoadContext>.|
<xref:System.Type.GetType(System.String)?displayProperty=nameWithType><p><xref:System.Type.GetType(System.String,System.Boolean)?displayProperty=nameWithType><p><xref:System.Type.GetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType>|`Load-by-name`|Dedotto dal chiamante.<p>Preferisce <xref:System.Type.GetType%2A?displayProperty=nameWithType> metodi con un argomento `assemblyResolver`.|
<xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>|Se Type `name` descrive un tipo generico completo di assembly, attivare una `Load-by-name`.|Dedotto dal chiamante.<p>Preferisce <xref:System.Type.GetType%2A?displayProperty=nameWithType> quando si usano nomi di tipo completi di assembly.|
<xref:System.Activator.CreateInstance(System.String,System.String)?displayProperty=nameWithType><p><xref:System.Activator.CreateInstance(System.String,System.String,System.Object[])?displayProperty=nameWithType><p><xref:System.Activator.CreateInstance(System.String,System.String,System.Boolean,System.Reflection.BindingFlags,System.Reflection.Binder,System.Object[],System.Globalization.CultureInfo,System.Object[])?displayProperty=nameWithType>|`Load-by-name`|Dedotto dal chiamante.<p>Preferisce <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> metodi che accettano un argomento <xref:System.Type>.|

## <a name="algorithm"></a>Algoritmo

Nell'algoritmo seguente viene descritto il modo in cui il runtime carica un assembly gestito.

1. Determinare l'<xref:System.Runtime.Loader.AssemblyLoadContext>di `active`.

    - Per un riferimento a un assembly statico, il `active` <xref:System.Runtime.Loader.AssemblyLoadContext> è l'istanza che ha caricato l'assembly di riferimento.
    - Le API preferite rendono esplicito il `active` <xref:System.Runtime.Loader.AssemblyLoadContext>.
    - Altre API derivano i <xref:System.Runtime.Loader.AssemblyLoadContext>di `active`. Per queste API, viene utilizzata la proprietà <xref:System.Runtime.Loader.AssemblyLoadContext.CurrentContextualReflectionContext?displayProperty=nameWithType>. Se il valore è `null`, viene utilizzata l'istanza <xref:System.Runtime.Loader.AssemblyLoadContext> dedotta.
    - Vedere la tabella sopra.

2. Per i metodi di `Load-by-name`, il <xref:System.Runtime.Loader.AssemblyLoadContext> attivo carica l'assembly. In ordine di priorità:
    - Verifica della `cache-by-name`.

    - Chiamata della funzione <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>.

    - Controllo della cache delle istanze <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> e esecuzione della logica di [Probe predefinita dell'assembly gestito](default-probing.md#managed-assembly-default-probing) .

    - Generazione dell'evento <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> per il AssemblyLoadContext attivo.

    - Generazione dell'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.

3. Per gli altri tipi di caricamenti, il `active` <xref:System.Runtime.Loader.AssemblyLoadContext> carica l'assembly. In ordine di priorità:
    - Verifica della `cache-by-name`.

    - Caricamento dal percorso specificato o dall'oggetto assembly non elaborato.

4. In entrambi i casi, se un assembly viene caricato di nuovo,:
   - Viene generato l'evento <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType>.
   - Viene aggiunto un riferimento al `cache-by-name`dell'istanza di <xref:System.Runtime.Loader.AssemblyLoadContext> dell'assembly.

5. Se l'assembly viene trovato, viene aggiunto un riferimento in base alle esigenze al `cache-by-name`dell'istanza di <xref:System.Runtime.Loader.AssemblyLoadContext> di `active`.
