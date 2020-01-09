---
title: Controllo delle versioni del linguaggio C# - Guida a C#
description: Informazioni su come viene determinata la versione del linguaggio C# in base al progetto e sui diversi valori ai quali è possibile adattarlo manualmente.
ms.date: 07/10/2019
ms.openlocfilehash: 90624816a68de694cacd0017c6d3162f6a89431c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713867"
---
# <a name="c-language-versioning"></a>Controllo delle versioni del linguaggio C#

Il compilatore C# più recente determina la versione di un linguaggio predefinito in base ai framework di destinazione del progetto. Il linguaggio C# può infatti includere funzionalità che si basano su tipi o componenti di runtime che non sono disponibili in ogni implementazione .NET. Ciò garantisce anche che, per qualsiasi framework di destinazione del progetto, si otterrà per impostazione predefinita la versione del linguaggio maggiormente compatibile.

Le regole in questo articolo si applicano al compilatore fornito con Visual Studio 2019 o .NET Core 3.0 SDK. I compilatori C# che fanno parte dell'installazione di Visual Studio 2017 o di versioni precedenti di .NET Core SDK usano C# 7.0 come destinazione per impostazione predefinita. 

## <a name="defaults"></a>Impostazioni predefinite

Il compilatore determina un'impostazione predefinita in base a queste regole:

|Framework di destinazione|Versione di|Impostazione predefinita della versione del linguaggio C#|
|----------------|-------|---------------------------|
|.NET Core|3.x|C# 8.0|
|.NET Core|2.x|C# 7.3|
|.NET Standard|2.1|C# 8.0|
|.NET Standard|2.0|C# 7.3|
|.NET Standard|1.x|C# 7.3|
|.NET Framework|tutti|C# 7.3|

## <a name="default-for-previews"></a>Impostazione predefinita per le anteprime

Quando il progetto ha come destinazione un framework in anteprima con una versione del linguaggio in anteprima corrispondente, la versione del linguaggio usata è la versione del linguaggio in anteprima. In questo modo, sarà possibile usare le funzionalità più recenti che sicuramente funzioneranno con l'anteprima in qualsiasi ambiente senza alcun effetto sui progetti che hanno come destinazione una versione rilasciata di .NET Core.

## <a name="override-a-default"></a>Sostituire un valore predefinito

Se è necessario specificare in modo esplicito la versione di C#, è possibile farlo in diversi modi:

- Modificare manualmente il [file di progetto](#edit-the-project-file).
- Impostare la versione del linguaggio [per più progetti in una sottodirectory](#configure-multiple-projects).
- Configurare l'[opzione del compilatore `-langversion`](compiler-options/langversion-compiler-option.md).

### <a name="edit-the-project-file"></a>Modificare il file di progetto

È possibile impostare la versione del linguaggio nel file di progetto. Ad esempio, se si vuole accedere esplicitamente alle funzionalità di anteprima, aggiungere un elemento simile a questo:

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

Il valore `preview` usa la versione del linguaggio C# in anteprima disponibile più recente supportata dal compilatore.

### <a name="configure-multiple-projects"></a>Configurare più progetti

È possibile creare un file **Directory.build.props** che contiene l'elemento `<LangVersion>` per configurare più directory. Questa operazione viene in genere eseguita nella directory della soluzione. Aggiungere il codice seguente a un file **Directory.Build.props** nella directory della soluzione:

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

Ora le build presenti in ogni sottodirectory della directory contenente il file useranno la versione di C# in anteprima. Per altre informazioni, vedere l'articolo [Personalizzare la compilazione](/visualstudio/msbuild/customize-your-build).

## <a name="c-language-version-reference"></a>Informazioni di riferimento sulle versioni del linguaggio C#

La tabella seguente illustra tutte le versioni del linguaggio C# correnti. Il compilatore in uso potrebbe non riconoscere necessariamente ogni valore, se è antecedente. Se si installa .NET Core 3.0, si avrà accesso a tutti gli elementi elencati.

|Valore|Significato|
|------------|-------------|
|preview|Il compilatore accetta tutte le sintassi di linguaggio valide dalla versione di anteprima più recente.|
|latest|Il compilatore accetta la sintassi dalla versione rilasciata più recente del compilatore (inclusa la versione secondaria).|
|latestMajor|Il compilatore accetta la sintassi dalla versione principale più recente rilasciata del compilatore.|
|8.0|Il compilatore accetta solo la sintassi inclusa in C# 8.0 o versione precedente.|
|7.3|Il compilatore accetta solo la sintassi inclusa in C# 7.3 o versione precedente.|
|7.2|Il compilatore accetta solo la sintassi inclusa in C# 7.2 o versione precedente.|
|7.1|Il compilatore accetta solo la sintassi inclusa in C# 7.1 o versione precedente.|
|7|Il compilatore accetta solo la sintassi inclusa in C# 7.0 o versione precedente.|
|6|Il compilatore accetta solo la sintassi inclusa in C# 6.0 o versione precedente.|
|5|Il compilatore accetta solo la sintassi inclusa in C# 5.0 o versione precedente.|
|4|Il compilatore accetta solo la sintassi inclusa in C# 4.0 o versione precedente.|
|3\.|Il compilatore accetta solo la sintassi inclusa in C# 3.0 o versione precedente.|
|ISO-2|Il compilatore accetta solo la sintassi inclusa nella specifica ISO/IEC 23270:2006 C# (2.0) |
|ISO-1|Il compilatore accetta solo la sintassi inclusa nella specifica ISO/IEC 23270:2003 C# (1.0/1.2) |
