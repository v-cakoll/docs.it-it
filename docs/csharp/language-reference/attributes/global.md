---
title: 'Attributi riservati di C: attributi globali'
ms.date: 04/09/2020
description: Gli attributi forniscono metadati utilizzati dal compilatore per comprendere una maggiore semantica del programmaAttributes provide metadata the compiler uses to understand more semantics of your program
ms.openlocfilehash: f855f32cd7349da34ffbd20fededdf42c3023938
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389856"
---
# <a name="reserved-attributes-assembly-level-attributes"></a>Attributi riservati: attributi a livello di assieme

La maggior parte degli attributi viene applicata a elementi specifici del linguaggio quali classi o metodi. Alcuni attributi sono invece globali e vengono applicati a un intero assembly o a un intero modulo. Ad esempio, l'attributo <xref:System.Reflection.AssemblyVersionAttribute> può essere usato per incorporare informazioni sulla versione in un assembly, nel modo seguente:

```csharp
[assembly: AssemblyVersion("1.0.0.0")]
```

Gli attributi globali vengono visualizzati `using` nel codice sorgente dopo qualsiasi direttiva di primo livello e prima di qualsiasi dichiarazione di tipo, modulo o spazio dei nomi. Gli attributi globali possono apparire in più file di origine, ma i file devono essere compilati in un'unica operazione di compilazione. Visual Studio aggiunge attributi globali al file AssemblyInfo.cs nei progetti .NET Framework. Questi attributi non vengono aggiunti ai progetti .NET Core.These attributes aren't added to .NET Core projects.

Gli attributi dell'assembly sono valori che forniscono informazioni relative a un assembly. Sono suddivisi nelle seguenti categorie:

- Attributi relativi all'identità dell'assembly
- Attributi informativi
- Attributi relativi al manifesto dell'assembly

## <a name="assembly-identity-attributes"></a>Attributi relativi all'identità dell'assembly

Tre attributi (con un nome sicuro, se disponibile), consentono di determinare l'identità di un assembly: il nome, la versione e le impostazioni cultura. Questi attributi formano il nome completo dell'assembly e sono necessari per creare riferimenti all'assembly nel codice. È possibile usare gli attributi per impostare la versione e le impostazioni cultura di un assembly. Tuttavia, il valore del nome viene impostato dal compilatore, dall'IDE di Visual Studio nella finestra di [dialogo Informazioni assembly](/visualstudio/ide/reference/assembly-information-dialog-box)o da Assembly Linker (Al.exe) quando viene creato l'assembly. Il nome dell'assembly è basato sul manifesto dell'assembly. L'attributo <xref:System.Reflection.AssemblyFlagsAttribute> specifica se è supportata la coesistenza di più copie dell'assembly.

La tabella seguente visualizza gli attributi relativi all'identità.

|Attributo|Scopo|
|---------------|-------------|
|<xref:System.Reflection.AssemblyVersionAttribute>|Specifica la versione di un assembly.|
|<xref:System.Reflection.AssemblyCultureAttribute>|Specifica le impostazioni cultura supportate dall'assembly.|
|<xref:System.Reflection.AssemblyFlagsAttribute>|Specifica se un assembly supporta l'esecuzione side-by-side nello stesso computer, nello stesso processo o nello stesso dominio dell'applicazione.|

## <a name="informational-attributes"></a>Attributi informativi

Gli attributi informativi vengono utilizzati per fornire informazioni aggiuntive sulla società o sul prodotto per un assembly. La tabella seguente mostra gli attributi informativi definiti nello spazio dei nomi <xref:System.Reflection?displayProperty=nameWithType>.

|Attributo|Scopo|
|---------------|-------------|
|<xref:System.Reflection.AssemblyProductAttribute>|Specifica un nome di prodotto per un manifesto dell'assembly.|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|Specifica un marchio per un manifesto dell'assembly.|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|Specifica una versione informativa per un manifesto dell'assembly.|
|<xref:System.Reflection.AssemblyCompanyAttribute>|Specifica un nome di società per un manifesto dell'assembly.|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|Definisce un attributo personalizzato che specifica un copyright per un manifesto dell'assembly.|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|Imposta un numero di versione specifico per la risorsa versione del file Win32.|
|<xref:System.CLSCompliantAttribute>|Indica se l'assembly è conforme a CLS (Common Language Specification).|

## <a name="assembly-manifest-attributes"></a>Attributi relativi al manifesto dell'assembly

È possibile usare gli attributi relativi al manifesto dell'assembly per includere informazioni nel manifesto dell'assembly. Gli attributi includono titolo, descrizione, alias predefinito e configurazione. La tabella seguente visualizza gli attributi del manifesto dell'assembly definiti nello spazio dei nomi <xref:System.Reflection?displayProperty=nameWithType>.

|Attributo|Scopo|
|---------------|-------------|
|<xref:System.Reflection.AssemblyTitleAttribute>|Specifica un titolo dell'assembly per un manifesto dell'assembly.|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|Specifica una descrizione dell'assembly per un manifesto dell'assembly.|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|Specifica una configurazione di assembly (ad esempio vendita al dettaglio o debug) per un manifesto dell'assembly.|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|Definisce un alias predefinito descrittivo per un manifesto dell'assembly.|
