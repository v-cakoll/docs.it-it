---
title: Algoritmo di caricamento degli assembly gestiti-.NET Core
description: Descrizione dei dettagli dell'algoritmo di caricamento dell'assembly gestito in .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: bf95cbd0eebed064f0198ae9b0f7a4288a938f8a
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2019
ms.locfileid: "70234602"
---
# <a name="managed-assembly-loading-algorithm"></a>Algoritmo di caricamento assembly gestito

Gli assembly gestiti vengono individuati e caricati con un algoritmo che prevede varie fasi.

Tutti gli assembly gestiti ad eccezione degli `WinRT` assembly satellite e degli assembly utilizzano lo stesso algoritmo.

## <a name="when-are-managed-assemblies-loaded"></a>Quando vengono caricati gli assembly gestiti?

Il meccanismo più comune per attivare un caricamento dell'assembly gestito è un riferimento a un assembly statico. Questi riferimenti vengono inseriti dal compilatore ogni volta che il codice utilizza un tipo definito in un altro assembly. Questi assembly vengono caricati (`load-by-name`) in base alle esigenze del runtime.

Anche l'uso diretto di API specifiche attiverà i caricamenti:

|API  |Descrizione  |`Active` <xref:System.Runtime.Loader.AssemblyLoadContext> |
|---------|---------|---------|
|<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromAssemblyName%2A?displayProperty=nameWithType>|`Load-by-name`|Istanza [di](../../csharp/language-reference/keywords/this.md) .|
|<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromAssemblyPath%2A?displayProperty=nameWithType><p><xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromNativeImagePath%2A?displayProperty=nameWithType>|Carica da percorso.|Istanza [di](../../csharp/language-reference/keywords/this.md) .|
<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromStream%2A?displayProperty=nameWithType>|Caricamento da un oggetto.|Istanza [di](../../csharp/language-reference/keywords/this.md) .|
|<xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType>|Carica da percorso in una nuova <xref:System.Runtime.Loader.AssemblyLoadContext> istanza|Nuova istanza di <xref:System.Runtime.Loader.AssemblyLoadContext>.|
<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>|Caricamento dal percorso nell' <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> istanza di.<p>Aggiunge un <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving> gestore a <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>. Il gestore caricherà le dipendenze dell'assembly dalla relativa directory.|Istanza di <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.|
|<xref:System.Reflection.Assembly.Load(System.Reflection.AssemblyName)?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.Load(System.String)?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>|`Load-by-name`.|Dedotto dal chiamante.<p>Preferire <xref:System.Runtime.Loader.AssemblyLoadContext> i metodi.|
|<xref:System.Reflection.Assembly.Load(System.Byte[])?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.Load(System.Byte[],System.Byte[])?displayProperty=nameWithType>|Caricamento da un oggetto.|Dedotto dal chiamante.<p>Preferire <xref:System.Runtime.Loader.AssemblyLoadContext> i metodi.|
<xref:System.Type.GetType(System.String)?displayProperty=nameWithType><p><xref:System.Type.GetType(System.String,System.Boolean)?displayProperty=nameWithType><p><xref:System.Type.GetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType>|[https://login.microsoftonline.com/common/](`Load-by-name`).|Dedotto dal chiamante.<p>Preferisce <xref:System.Type.GetType%2A?displayProperty=nameWithType> i metodi con `assemblyResolver` un argomento.|
<xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>|Se il `name` tipo descrive un tipo generico completo di assembly, `Load-by-name`attivare un oggetto.|Dedotto dal chiamante.<p>Preferisce <xref:System.Type.GetType%2A?displayProperty=nameWithType> quando si usano nomi di tipo completi di assembly.|
<xref:System.Activator.CreateInstance(System.String,System.String)?displayProperty=nameWithType><p><xref:System.Activator.CreateInstance(System.String,System.String,System.Object[])?displayProperty=nameWithType><p><xref:System.Activator.CreateInstance(System.String,System.String,System.Boolean,System.Reflection.BindingFlags,System.Reflection.Binder,System.Object[],System.Globalization.CultureInfo,System.Object[])?displayProperty=nameWithType>|[https://login.microsoftonline.com/consumers/](`Load-by-name`).|Dedotto dal chiamante.<p>Preferisce <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> che i metodi <xref:System.Type> accettino un argomento.|

## <a name="algorithm"></a>Algoritmo

Nell'algoritmo seguente viene descritto il modo in cui il runtime carica un assembly gestito.

1. `active` Determinare .<xref:System.Runtime.Loader.AssemblyLoadContext>

    - Per un riferimento a un assembly statico `active` , <xref:System.Runtime.Loader.AssemblyLoadContext> è l'istanza che ha caricato l'assembly di riferimento.
    - `active` Le<xref:System.Runtime.Loader.AssemblyLoadContext> API preferite rendono esplicito.
    - Altre API `active` <xref:System.Runtime.Loader.AssemblyLoadContext>derivano. Per queste API, viene <xref:System.Runtime.Loader.AssemblyLoadContext.CurrentContextualReflectionContext?displayProperty=nameWithType> utilizzata la proprietà. Se il valore è `null`, viene utilizzata l' <xref:System.Runtime.Loader.AssemblyLoadContext> istanza dedotta.
    - Vedere la tabella sopra.

2. Per i `Load-by-name` metodi, il metodo <xref:System.Runtime.Loader.AssemblyLoadContext> attivo carica l'assembly. In ordine di priorità:
    - Verifica della `cache-by-name`relativa.

    - Chiamata della <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> funzione.

    - Controllo della <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> cache delle istanze e esecuzione della logica di [sondaggio predefinita dell'assembly gestito](default-probing.md#managed-assembly-default-probing) .

    - Generazione dell' <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> evento per il AssemblyLoadContext attivo.

    - Generazione dell' <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> evento.

3. Per gli altri tipi di caricamenti, `active` <xref:System.Runtime.Loader.AssemblyLoadContext> carica l'assembly. In ordine di priorità:
    - Verifica della `cache-by-name`relativa.

    - Caricamento dal percorso specificato o dall'oggetto assembly non elaborato.

4. In entrambi i casi, se un assembly viene caricato di nuovo,:
   - Viene generato l'evento <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType>.
   - Viene aggiunto un riferimento all' <xref:System.Runtime.Loader.AssemblyLoadContext> `cache-by-name`istanza dell'assembly.

5. Se l'assembly viene trovato, viene aggiunto un riferimento in base alle esigenze `active` per l' `cache-by-name`oggetto <xref:System.Runtime.Loader.AssemblyLoadContext> dell'istanza.
