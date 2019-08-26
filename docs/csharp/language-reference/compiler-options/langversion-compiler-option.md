---
title: -langversion (opzioni del compilatore C#)
ms.date: 05/14/2018
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 5675099f66ec99c652ef95a5328f31c360e2dc59
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602837"
---
# <a name="-langversion-c-compiler-options"></a>-langversion (opzioni del compilatore C#)

Imposta il compilatore in modo da accettare solo sintassi inclusa nella specifica di linguaggio C# selezionata.  
  
## <a name="syntax"></a>Sintassi  

```console
-langversion:option  
```

## <a name="arguments"></a>Argomenti

 `option`  
 Di seguito vengono illustrati i valori validi.  
  
|Opzione|Significato|  
|------------|-------------|  
|preview|Il compilatore accetta tutte le sintassi di linguaggio valide dalla versione di anteprima più recente supportata.|
|latest|Il compilatore accetta tutte le sintassi di linguaggio valide dalla versione più recente (incluse le versioni secondarie) supportata.|
|latestMajor|Il compilatore accetta tutte le sintassi di linguaggio valide dalla versione principale più recente supportata.|
|8.0|Il compilatore accetta solo la sintassi inclusa in C# 8.0 o versione precedente. <sup id="TCS80">[CS80](#FCS80)</sup>|
|7.3|Il compilatore accetta solo la sintassi inclusa in C# 7.3 o versione inferiore <sup id="TCS73">[CS73](#FCS73)</sup>|
|7.2|Il compilatore accetta solo la sintassi inclusa in C# 7.2 o versione inferiore <sup id="TCS72">[CS72](#FCS72)</sup>|
|7.1|Il compilatore accetta solo la sintassi inclusa in C# 7.1 o versione inferiore <sup id="TCS71">[CS71](#FCS71)</sup>|
|7|Il compilatore accetta solo la sintassi inclusa in C# 7.0 o versione inferiore <sup id="TCS7">[CS7](#FCS7)</sup>|
|6|Il compilatore accetta solo la sintassi inclusa in C# 6.0 o versione inferiore <sup id="TCS6">[CS6](#FCS6)</sup>|
|5|Il compilatore accetta solo la sintassi inclusa in C# 5.0 o versione inferiore <sup id="TCS5">[CS5](#FCS5)</sup>|
|4|Il compilatore accetta solo la sintassi inclusa in C# 4.0 o versione inferiore <sup id="TCS4">[CS4](#FCS4)</sup>|
|3|Il compilatore accetta solo la sintassi inclusa in C# 3.0 o versione inferiore <sup id="TCS3">[CS3](#FCS3)</sup>|
|ISO-2|Il compilatore accetta solo la sintassi inclusa nella specifica di linguaggio ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup>|
|ISO-1|Il compilatore accetta solo la sintassi inclusa nella specifica di linguaggio ISO/IEC 23270:2003 C# (1.0/1.2) <sup id="TISO1">[ISO1](#FISO1)</sup>|  

## <a name="remarks"></a>Osservazioni

 I metadati a cui viene fatto riferimento nell'applicazione C# non sono soggetti all'opzione del compilatore **-langversion**.  
  
 Poiché ogni versione del compilatore C# contiene estensioni per la specifica del linguaggio, **-langversion** non offre la funzionalità equivalente di una versione precedente del compilatore.  

 Inoltre, mentre gli aggiornamenti di versione di C# coincidono in genere con le versioni principali di .NET Framework, la nuova sintassi e le nuove funzionalità non sono necessariamente correlate alla versione specifica del framework. Sebbene le nuove funzionalità richiedano un nuovo aggiornamento del compilatore, anch'esso rilasciato insieme alla revisione di C#, ogni funzionalità specifica presenta requisiti minimi in termini di API .NET o Common Language Runtime che ne consentono l'esecuzione in versioni di Framework di livello inferiore, inclusi pacchetti NuGet o altre librerie.
  
 Indipendentemente dall'impostazione di **-langversion** specificata, per creare il file con estensione exe o dll viene usata la versione corrente di Common Language Runtime. Un'eccezione è costituita dagli assembly Friend e da [-moduleassemblyname (opzione del compilatore C#)](./moduleassemblyname-compiler-option.md), che vengono eseguiti con **-langversion:ISO-1**.  

 Per altri metodi per la specifica della versione del linguaggio C#, vedere l'argomento [Select the C# language version](../configure-language-version.md) (Selezionare la versione del linguaggio C#).
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.  

## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C#](index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)

### <a name="c-language-specification"></a>Specifiche del linguaggio C#

|Versione|Collegamento|DESCRIZIONE|
|-------|----|-----------|
|C# 7.0 e versioni successive||Attualmente non disponibile|
|C# 6.0|[Collegamento](../language-specification/index.md)|Specifica del linguaggio C# versione 6 - Bozza non ufficiale: .NET Foundation|
|C# 5.0|[Scaricare PDF](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf)|Standard ECMA-334, quinta edizione|
|C# 3.0|[Scaricare DOC](https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc)|Specifiche del linguaggio C# versione 3.0: Microsoft Corporation|
|C# 2.0|[Scaricare PDF](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf)|Standard ECMA-334, quarta edizione|
|C# 1.2|[Scaricare DOC](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf)|Specifiche del linguaggio C# versione 1.2: Microsoft Corporation|
|C# 1.0|[Scaricare DOC](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf)|Specifiche del linguaggio C# versione 1.0: Microsoft Corporation|

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a>Versione minima del compilatore necessaria per supportare tutte le funzionalità del linguaggio

[↩](#TCS80)<a name="FCS80">CS80</a>: Microsoft Visual Studio/Build Tools 2019 versione 16 o .NET Core 3.0 SDK  
[↩](#TCS73)<a name="FCS73">CS73</a>: Microsoft Visual Studio/Build Tools 2017 versione 15.7  
[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 2017 versione 15.5  
[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 2017 versione 15.3  
[↩](#TCS7)<a name="FCS7">CS7</a>: Microsoft Visual Studio/Build Tools 2017  
[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015  
[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 o compilatore di .Net Framework 4.5 in bundle  
[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 o compilatore di .Net Framework 4.0 in bundle  
[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 o compilatore di .Net Framework 3.5 in bundle  
[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 o compilatore di .Net Framework 2.0 in bundle  
[↩](#TISO1)<a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .NET 2002 o compilatore di .NET Framework 1.0 in bundle  
