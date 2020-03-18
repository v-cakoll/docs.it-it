---
title: Algoritmo di caricamento di assembly gestito - .NET CoreManaged assembly loading algorithm - .NET Core
description: Descrizione dei dettagli dell'algoritmo di caricamento dell'assembly gestito in .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 312a320676be6eb453697e0704ab771a6707618b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73973506"
---
# <a name="managed-assembly-loading-algorithm"></a>Algoritmo di caricamento dell'assembly gestito

Gli assembly gestiti vengono individuati e caricati con un algoritmo che coinvolge varie fasi.

Tutti gli assembly gestiti, ad eccezione degli assembly e `WinRT` assembly satellite, utilizzano lo stesso algoritmo.

## <a name="when-are-managed-assemblies-loaded"></a>Quando vengono caricati gli assembly gestiti?

Il meccanismo più comune per attivare il caricamento di un assembly gestito è un riferimento statico all'assembly. Questi riferimenti vengono inseriti dal compilatore ogni volta che il codice utilizza un tipo definito in un altro assembly. Questi assembly vengono`load-by-name`caricati ( ) in base alle esigenze del runtime.

Anche l'uso diretto di API specifiche attiverà i caricamenti:

|API  |Descrizione  |`Active` <xref:System.Runtime.Loader.AssemblyLoadContext> |
|---------|---------|---------|
|<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromAssemblyName%2A?displayProperty=nameWithType>|`Load-by-name`|L'istanza [di questa.](../../csharp/language-reference/keywords/this.md)|
|<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromAssemblyPath%2A?displayProperty=nameWithType><p><xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromNativeImagePath%2A?displayProperty=nameWithType>|Carica dal percorso.|L'istanza [di questa.](../../csharp/language-reference/keywords/this.md)|
<xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromStream%2A?displayProperty=nameWithType>|Carica dall'oggetto.|L'istanza [di questa.](../../csharp/language-reference/keywords/this.md)|
|<xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType>|Carica dal percorso <xref:System.Runtime.Loader.AssemblyLoadContext> in una nuova istanza|Nuova istanza di <xref:System.Runtime.Loader.AssemblyLoadContext>.|
<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>|Caricare dal percorso <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> nell'istanza.<p>Aggiunge <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving> un <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>gestore a . Il gestore caricherà le dipendenze dell'assembly dalla relativa directory.|Istanza <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.|
|<xref:System.Reflection.Assembly.Load(System.Reflection.AssemblyName)?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.Load(System.String)?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>|`Load-by-name`.|Dedotta dal chiamante.<p>Preferisci i <xref:System.Runtime.Loader.AssemblyLoadContext> metodi.|
|<xref:System.Reflection.Assembly.Load(System.Byte[])?displayProperty=nameWithType><p><xref:System.Reflection.Assembly.Load(System.Byte[],System.Byte[])?displayProperty=nameWithType>|Caricare dall'oggetto <xref:System.Runtime.Loader.AssemblyLoadContext> in una nuova istanza.|Nuova istanza di <xref:System.Runtime.Loader.AssemblyLoadContext>.|
<xref:System.Type.GetType(System.String)?displayProperty=nameWithType><p><xref:System.Type.GetType(System.String,System.Boolean)?displayProperty=nameWithType><p><xref:System.Type.GetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType>|`Load-by-name`.|Dedotta dal chiamante.<p>Preferisci <xref:System.Type.GetType%2A?displayProperty=nameWithType> i `assemblyResolver` metodi con un argomento.|
<xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>|Se `name` type descrive un tipo generico `Load-by-name`qualificato dall'assembly, attivare un file .|Dedotta dal chiamante.<p>Preferire <xref:System.Type.GetType%2A?displayProperty=nameWithType> quando si utilizzano i nomi di tipo completo dell'assembly.|
<xref:System.Activator.CreateInstance(System.String,System.String)?displayProperty=nameWithType><p><xref:System.Activator.CreateInstance(System.String,System.String,System.Object[])?displayProperty=nameWithType><p><xref:System.Activator.CreateInstance(System.String,System.String,System.Boolean,System.Reflection.BindingFlags,System.Reflection.Binder,System.Object[],System.Globalization.CultureInfo,System.Object[])?displayProperty=nameWithType>|`Load-by-name`.|Dedotta dal chiamante.<p>Preferire <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> i <xref:System.Type> metodi che prendono un argomento.|

## <a name="algorithm"></a>Algoritmo

L'algoritmo seguente descrive il modo in cui il runtime carica un assembly gestito.

1. Determinare `active` <xref:System.Runtime.Loader.AssemblyLoadContext>il file .

    - Per un riferimento statico `active` <xref:System.Runtime.Loader.AssemblyLoadContext> all'assembly, è l'istanza che ha caricato l'assembly di riferimento.
    - Le API preferite `active` <xref:System.Runtime.Loader.AssemblyLoadContext> rendono l'explicit.
    - Altre API deducono il `active` <xref:System.Runtime.Loader.AssemblyLoadContext>file . Per queste API, <xref:System.Runtime.Loader.AssemblyLoadContext.CurrentContextualReflectionContext?displayProperty=nameWithType> viene utilizzata la proprietà. Se il `null`valore è , <xref:System.Runtime.Loader.AssemblyLoadContext> viene utilizzata l'istanza dedotta.
    - Vedere la tabella precedente.

2. Per `Load-by-name` i metodi, <xref:System.Runtime.Loader.AssemblyLoadContext> l'attivo carica l'assieme. In ordine di priorità per:
    - Verifica `cache-by-name`del suo file .

    - Chiamata <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> della funzione.

    - Controllo <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> della cache delle istanze e esecuzione della logica di probe predefinita dell'assembly [gestito.](default-probing.md#managed-assembly-default-probing)

    - Generazione <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> dell'evento per l'oggetto AssemblyLoadContext attivo.

    - Generazione <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> dell'evento.

3. Per gli altri tipi `active` <xref:System.Runtime.Loader.AssemblyLoadContext> di carichi, l'assieme viene caricato. In ordine di priorità per:
    - Verifica `cache-by-name`del suo file .

    - Caricamento dal percorso specificato o dall'oggetto assembly non elaborato.

4. In entrambi i casi, se un assembly è appena caricato, allora:
   - Viene generato l'evento <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType>.
   - Viene aggiunto un riferimento all'istanza <xref:System.Runtime.Loader.AssemblyLoadContext> `cache-by-name`dell'assembly.

5. Se l'assembly viene trovato, viene aggiunto `active` <xref:System.Runtime.Loader.AssemblyLoadContext> un `cache-by-name`riferimento in base alle esigenze dell'istanza .
