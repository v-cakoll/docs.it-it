---
title: -langversion (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /langversion
dev_langs:
- CSharp
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
caps.latest.revision: 33
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fc501c5532d27168d74d1a5f293abe59d3beeef1
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="langversion-c-compiler-options"></a>/langversion (opzioni del compilatore C#)
Imposta il compilatore in modo da accettare solo sintassi inclusa nella specifica di linguaggio C# selezionata.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
/langversion:option  
```  
  
## <a name="arguments"></a>Argomenti  
 `option`  
 Di seguito vengono illustrati i valori validi.  
  
|Opzione|Significato|  
|------------|-------------|  
|default|Il compilatore accetta tutte le sintassi di linguaggio valide. <sup id="TDefault">[Default](#FDefault)</sup>| 
|ISO-1|Il compilatore accetta solo la sintassi inclusa nella specifica di linguaggio ISO/IEC 23270:2003 C# (1.0/1.1) <sup id="TISO1">[ISO1](#FISO1)</sup>|  
|ISO-2|Il compilatore accetta solo la sintassi inclusa nella specifica di linguaggio ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup>|
|3|Il compilatore accetta solo la sintassi inclusa in C# 3.0 o versione inferiore <sup id="TCS3">[CS3](#FCS3)</sup>|
|4|Il compilatore accetta solo la sintassi inclusa in C# 4.0 o versione inferiore <sup id="TCS4">[CS4](#FCS4)</sup>|
|5|Il compilatore accetta solo la sintassi inclusa in C# 5.0 o versione inferiore <sup id="TCS5">[CS5](#FCS5)</sup>|
|6|Il compilatore accetta solo la sintassi inclusa in C# 6.0 o versione inferiore <sup id="TCS6">[CS6](#FCS6)</sup>|
|7|Il compilatore accetta solo la sintassi inclusa in C# 7.0 o versione inferiore <sup id="TCS7">[CS7](#FCS7)</sup>|
|latest|Il compilatore accetta tutte le sintassi di linguaggio valide. <sup id="TLatest">[Latest](#FLatest)</sup>|
<!--- Uncomment and move these above
|latest| once they're officially released
|7.1|The compiler accepts only syntax that is included in C# 7.1 or lower <sup id="TCS71">[CS71](#FCS71)</sup>|
|7.2|The compiler accepts only syntax that is included in C# 7.2 or lower <sup id="TCS71">[CS72](#FCS72)</sup>|
|8|The compiler accepts only syntax that is included in C# 8 or lower <sup id="TCS71">[CS8](#FCS8)</sup>|
-->

  
## <a name="remarks"></a>Note  
 I metadati a cui viene fatto riferimento nell'applicazione C# non sono soggetti all'opzione del compilatore **/langversion**.  
  
 Poiché ogni versione del compilatore C# contiene estensioni alla specifica del linguaggio, **/langversion** non fornisce la funzionalità equivalente di una versione precedente del compilatore.  
 
 Inoltre, anche se gli aggiornamenti di versione di C# coincidono in genere con le versioni principali di .Net Framework, la nuova sintassi e le nuove funzionalità non sono necessariamente correlate alla versione specifica di Framework. Sebbene le nuove funzionalità richiedano un nuovo aggiornamento del compilatore, anch'esso rilasciato insieme alla revisione di C#, ogni funzionalità specifica presenta requisiti minimi in termini di API .Net o Common Language Runtime che ne consentono l'esecuzione in versioni di Framework di livello inferiore, inclusi pacchetti NuGet o altre librerie.
  
 Indipendentemente dall'impostazione di **/langversion** specificata, per creare il file con estensione exe o dll verrà usata la versione corrente di Common Language Runtime. Un'eccezione è costituita dagli assembly Friend e da [/moduleassemblyname (opzione del compilatore C#)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), che vengono eseguiti in **/langversion: ISO-1**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1.  Aprire la pagine **Proprietà** del progetto.  
  
2.  Fare clic sulla pagina della proprietà **Compilazione**.  
  
3.  Fare clic su **Avanzate** .  
  
4.  Modificare la proprietà **Versione linguaggio**.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.  
    
## <a name="see-also"></a>Vedere anche  
 [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)   
 
### <a name="c-language-specification"></a>Specifiche del linguaggio C#
 [Informazioni di riferimento sulla specifica di linguaggio C#](../../../csharp/language-reference/language-specification/index.md): .NET Foundation   
 C# 1.0/1.1 [ISO/IEC 23270:2003](https://www.iso.org/standard/36768.html) Information Technology -- Specifica del linguaggio C#: Catalogo ISO   
 C# 2.0 [ISO/IEC 23270:2006](https://www.iso.org/standard/42926.html) Information Technology -- Specifica del linguaggio C#: Catalogo ISO   
 C# 2.0 [c042926_ISO_IEC_23270_2006(E).zip](http://go.microsoft.com/fwlink/?LinkId=144406) ISO/IEC 23270:2006 in formato PDF: Standard ISO disponibili liberamente   
 C# 3.0 [CSharp Language Specification.doc](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc) Versione 3.0 della specifica del linguaggio C#: Microsoft Corporation   
 C# 4.0 [Ecma-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf) Standard ECMA-334, quarta edizione    
 C# 5.0 [CSharp Language Specification.docx](https://www.microsoft.com/en-us/download/details.aspx?id=7029) Versione 5.0 della specifica del linguaggio C#: Microsoft Corporation   
 C# 6.0 [README.md](https://github.com/dotnet/csharplang/blob/master/spec/README.md) Versione 6 della specifica del linguaggio C# - Bozza non ufficiale: .NET Foundation   
 C# 7.0 (attualmente non disponibile)   

<!--- Uncomment and add to the above when they become officially released
 C# 7.1 (spec is not yet finished)   
 C# 7.2 (spec is not yet finished)   
 C# 8.0 (spec is not yet finished)   
-->

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a>Versione minima del compilatore necessaria per supportare tutte le funzionalità del linguaggio   
[↩](#TDefault)<a name="FDefault">Predefinita</a>, <a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .Net 2002 o compilatore di .Net Framework 1.0 in bundle     
[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 o compilatore di .Net Framework 2.0 in bundle    
[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 o compilatore di .Net Framework 3.5 in bundle    
[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 o compilatore di .Net Framework 4.0 in bundle    
[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 o compilatore di .Net Framework 4.5 in bundle    
[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015    
[↩](#TCS7)<a name="FCS7">CS7</a>, <a name="FLatest">Latest</a>: Microsoft Visual Studio/Build Tools 2017   

<!--- Uncomment and add to the above when they become officially released
[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS8)<a name="FCS71">CS8</a>: Microsoft Visual Studio/Build Tools 20??    
-->

