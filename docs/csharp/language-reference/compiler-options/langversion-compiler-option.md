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
ms.openlocfilehash: 2a9501c883fec7478932b22ea2cdcad70865e0fd
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696286"
---
# <a name="-langversion-c-compiler-options"></a>-langversion (opzioni del compilatore C#)
Imposta il compilatore in modo da accettare solo sintassi inclusa nella specifica di linguaggio C# selezionata.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-langversion:option  
```  
  
## <a name="arguments"></a>Argomenti  
 `option`  
 I valori validi sono i seguenti:  
  
|Opzione|Significato|  
|------------|-------------|  
|default|Il compilatore accetta tutte le sintassi di linguaggio valide dalla versione principale più recente supportata.|
|ISO-1|Il compilatore accetta solo la sintassi inclusa nella specifica di linguaggio ISO/IEC 23270:2003 C# (1.0/1.2) <sup id="TISO1">[ISO1](#FISO1)</sup>|  
|ISO-2|Il compilatore accetta solo la sintassi inclusa nella specifica di linguaggio ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup>|
|3|Il compilatore accetta solo la sintassi inclusa in C# 3.0 o versione inferiore <sup id="TCS3">[CS3](#FCS3)</sup>|
|4|Il compilatore accetta solo la sintassi inclusa in C# 4.0 o versione inferiore <sup id="TCS4">[CS4](#FCS4)</sup>|
|5|Il compilatore accetta solo la sintassi inclusa in C# 5.0 o versione inferiore <sup id="TCS5">[CS5](#FCS5)</sup>|
|6|Il compilatore accetta solo la sintassi inclusa in C# 6.0 o versione inferiore <sup id="TCS6">[CS6](#FCS6)</sup>|
|7|Il compilatore accetta solo la sintassi inclusa in C# 7.0 o versione inferiore <sup id="TCS7">[CS7](#FCS7)</sup>|
|7.1|Il compilatore accetta solo la sintassi inclusa in C# 7.1 o versione inferiore <sup id="TCS71">[CS71](#FCS71)</sup>|
|7.2|Il compilatore accetta solo la sintassi inclusa in C# 7.2 o versione inferiore <sup id="TCS72">[CS72](#FCS72)</sup>|
|7.3|Il compilatore accetta solo la sintassi inclusa in C# 7.3 o versione inferiore <sup id="TCS73">[CS73](#FCS73)</sup>|
|latest|Il compilatore accetta tutte le sintassi di linguaggio valide.|

<!--- Uncomment and move these above
|8|The compiler accepts only syntax that is included in C# 8 or lower <sup id="TCS8">[CS8](#FCS8)</sup>|
-->

  
## <a name="remarks"></a>Note  
 I metadati a cui viene fatto riferimento nell'applicazione C# non sono soggetti all'opzione del compilatore **-langversion**.  
  
 Poiché ogni versione del compilatore C# contiene estensioni per la specifica del linguaggio, **-langversion** non offre la funzionalità equivalente di una versione precedente del compilatore.  
 
 Inoltre, mentre gli aggiornamenti di versione di C# coincidono in genere con le versioni principali di .NET Framework, la nuova sintassi e le nuove funzionalità non sono necessariamente correlate alla versione specifica del framework. Sebbene le nuove funzionalità richiedano un nuovo aggiornamento del compilatore, anch'esso rilasciato insieme alla revisione di C#, ogni funzionalità specifica presenta requisiti minimi in termini di API .NET o Common Language Runtime che ne consentono l'esecuzione in versioni di Framework di livello inferiore, inclusi pacchetti NuGet o altre librerie.
  
 Indipendentemente dall'impostazione di **-langversion** specificata, per creare il file con estensione exe o dll viene usata la versione corrente di Common Language Runtime. Un'eccezione è costituita dagli assembly Friend e da [-moduleassemblyname (opzione del compilatore C#)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), che vengono eseguiti con **-langversion:ISO-1**.  
 
 Per altri metodi per la specifica della versione del linguaggio C#, vedere l'argomento [Select the C# language version](../configure-language-version.md) (Selezionare la versione del linguaggio C#).
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.  
    
## <a name="see-also"></a>Vedere anche  
 [Opzioni del compilatore C#](index.md)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)  
 
### <a name="c-language-specification"></a>Specifiche del linguaggio C#

|Versione|Collegamento|Descrizione|
|-------|----|-----------|
|C# 1.0|[Scaricare DOC](http://download.microsoft.com/download/a/9/e/a9e229b9-fee5-4c3e-8476-917dee385062/csharp%20language%20specification%20v1.0.doc)|Specifica del linguaggio C# versione 1.0: Microsoft Corporation|
|C# 1.2|[Scaricare DOC](http://download.microsoft.com/download/5/e/5/5e58be0a-b02b-41ac-a4a3-7a22286214ff/csharp%20language%20specification%20v1.2.doc)|Specifica del linguaggio C# versione 1.2: Microsoft Corporation|
|C# 2.0|[Scaricare PDF](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/Ecma-334%204th%20edition%20June%202006.pdf)|Standard ECMA-334, quarta edizione|
|C# 3.0|[Scaricare DOC](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc)|Specifica del linguaggio C# versione 3.0: Microsoft Corporation|
|C# 5.0|[Scaricare PDF](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf)|Standard ECMA-334, quinta edizione|
|C# 6.0|[Collegamento](../language-specification/index.md)|Specifica del linguaggio C# versione 6 - Bozza non ufficiale: .NET Foundation|
|C# 7.0 e versioni successive||Attualmente non disponibile|

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a>Versione minima del compilatore necessaria per supportare tutte le funzionalità del linguaggio   
[↩](#TISO1)<a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .Net 2002 o compilatore di .Net Framework 1.0 in bundle     
[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 o compilatore di .Net Framework 2.0 in bundle    
[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 o compilatore di .Net Framework 3.5 in bundle    
[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 o compilatore di .Net Framework 4.0 in bundle    
[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 o compilatore di .Net Framework 4.5 in bundle    
[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015    
[↩](#TCS7)<a name="FCS7">CS7</a>: Microsoft Visual Studio/Build Tools 2017   
[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 2017, versione 15.3    
[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 2017, versione 15.5    
[↩](#TCS73)<a name="FCS73">CS73</a>: Microsoft Visual Studio/Build Tools 2017, versione 15.7    

<!--- Uncomment and add to the above when they become officially released
[↩](#TCS8)<a name="FCS8">CS8</a>: Microsoft Visual Studio/Build Tools 20??    
-->
