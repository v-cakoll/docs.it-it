---
title: -langversion (opzioni del compilatore C#)
ms.date: 08/23/2019
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 007b10f6f27233c43caad4c1910e3d1158682950
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920362"
---
# <a name="-langversion-c-compiler-options"></a>-langversion (opzioni del compilatore C#)

Imposta il compilatore in modo da accettare solo sintassi inclusa nella specifica di linguaggio C# selezionata.

## <a name="syntax"></a>Sintassi

```console
-langversion:option
```

## <a name="arguments"></a>Argomenti

`option`

I valori seguenti sono validi:

|Opzione|Significato|
|------------|-------------|
|preview|Il compilatore accetta tutte le sintassi di linguaggio valide dalla versione di anteprima più recente supportata.|
|più recenti|Il compilatore accetta tutte le sintassi di linguaggio valide dalla versione più recente (incluse le versioni secondarie) supportata.|
|latestMajor|Il compilatore accetta tutte le sintassi di linguaggio valide dalla versione principale più recente supportata.|
|8.0|Il compilatore accetta solo la sintassi inclusa in C# 8.0 o versione precedente.|
|7.3|Il compilatore accetta solo la sintassi inclusa in C# 7.3 o versione precedente.|
|7.2|Il compilatore accetta solo la sintassi inclusa in C# 7.2 o versione precedente.|
|7.1|Il compilatore accetta solo la sintassi inclusa in C# 7.1 o versione precedente.|
|7|Il compilatore accetta solo la sintassi inclusa in C# 7.0 o versione precedente.|
|6|Il compilatore accetta solo la sintassi inclusa in C# 6.0 o versione precedente.|
|5|Il compilatore accetta solo la sintassi inclusa in C# 5.0 o versione precedente.|
|4|Il compilatore accetta solo la sintassi inclusa in C# 4.0 o versione precedente.|
|3|Il compilatore accetta solo la sintassi inclusa in C# 3.0 o versione precedente.|
|ISO-2|Il compilatore accetta solo la sintassi inclusa in ISO/IEC 23270:2006 in C|
|ISO-1|Il compilatore accetta solo la sintassi inclusa in ISO/IEC 23270:2003 c'è (1.0/1.2).|

La versione del linguaggio predefinita dipende dal framework di destinazione per l'applicazione e dalla versione dell'SDK o di Visual Studio installata. Tali regole sono definite nell'articolo [configurazione della versione della lingua.](../configure-language-version.md#defaults)

## <a name="remarks"></a>Osservazioni

I metadati a cui viene fatto riferimento nell'applicazione C# non sono soggetti all'opzione del compilatore **-langversion**.

Poiché ogni versione del compilatore C# contiene estensioni per la specifica del linguaggio, **-langversion** non offre la funzionalità equivalente di una versione precedente del compilatore.

Inoltre, mentre gli aggiornamenti di versione di C# coincidono in genere con le versioni principali di .NET Framework, la nuova sintassi e le nuove funzionalità non sono necessariamente correlate alla versione specifica del framework. Sebbene le nuove funzionalità richiedano un nuovo aggiornamento del compilatore, anch'esso rilasciato insieme alla revisione di C#, ogni funzionalità specifica presenta requisiti minimi in termini di API .NET o Common Language Runtime che ne consentono l'esecuzione in versioni di Framework di livello inferiore, inclusi pacchetti NuGet o altre librerie.

Indipendentemente dall'impostazione **di -langversion** utilizzata, utilizzare la versione corrente di Common Language Runtime per creare il file exe o dll. Un'eccezione è un'eccezione tra gli assembly Friend e [-moduleassemblyname (opzione del compilatore C)](./moduleassemblyname-compiler-option.md), che funzionano in **-langversion:ISO-1**.

Per altri modi per specificare la versione del linguaggio C, vedere [l'articolo Selezionare la versione del linguaggio C.](../configure-language-version.md)

Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

|Versione|Collegamento|Descrizione|
|-------|----|-----------|
|C# 7.0 e versioni successive||Attualmente non disponibile|
|C# 6.0|[Link](/dotnet/csharp/language-reference/language-specification/introduction)|Specifica del linguaggio C# versione 6 - Bozza non ufficiale: .NET Foundation|
|C# 5.0|[Scarica il PDF](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf)|Standard ECMA-334, quinta edizione|
|C# 3.0|[Scaricare DOC](https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc)|Specifica del linguaggio C# versione 3.0: Microsoft Corporation|
|C# 2.0|[Scarica il PDF](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf)|Standard ECMA-334, quarta edizione|
|C# 1.2|[Scaricare DOC](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf)|Specifica del linguaggio C# versione 1.2: Microsoft Corporation|
|C# 1.0|[Scaricare DOC](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf)|Specifica del linguaggio C# versione 1.0: Microsoft Corporation|

## <a name="minimum-sdk-version-needed-to-support-all-language-features"></a>Versione minima dell'SDK necessaria per supportare tutte le funzionalità del linguaggio

Nella tabella seguente sono elencate le versioni minime dell'SDK con il compilatore di C, che supporta la versione del linguaggio corrispondente:

|Versione di C|Versione minima dell'SDK|
|----------|-------------------|
|C# 8.0| Microsoft Visual Studio/Build Tools 2019, versione 16.3 o .NET Core 3.0 SDK |
|C# 7.3| Microsoft Visual Studio/Build Tools 2017 versione 15.7 |
|C# 7.2| Microsoft Visual Studio/Build Tools 2017 versione 15.5 |
|C# 7.1| Microsoft Visual Studio/Build Tools 2017 versione 15.3 |
|C# 7.0| Microsoft Visual Studio/Build Tools 2017 |
|C# 6| Microsoft Visual Studio/Build Tools 2015 |
|C'è 5| Microsoft Visual Studio/Build Tools 2012 o compilatore di .Net Framework 4.5 in bundle |
|C# 4| Microsoft Visual Studio/Build Tools 2010 o compilatore di .Net Framework 4.0 in bundle |
|C'è 3| Microsoft Visual Studio/Build Tools 2008 o compilatore di .Net Framework 3.5 in bundle |
|C'è 2| Microsoft Visual Studio/Build Tools 2005 o compilatore di .Net Framework 2.0 in bundle |
|1.0/1.2 di C | Microsoft Visual Studio/Strumenti di compilazione .NET 2002 o compilatore .NET Framework 1.0 in bundle |

## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
