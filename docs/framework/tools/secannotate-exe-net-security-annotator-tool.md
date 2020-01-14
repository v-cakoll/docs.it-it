---
title: SecAnnotate.exe (strumento .NET Security Annotator)
ms.date: 03/30/2017
helpviewer_keywords:
- SecAnnotate.exe
- Security Annotator tool
ms.assetid: 8104d208-7813-4a1d-8a75-58f9a7bcb8c9
ms.openlocfilehash: ffc275c588775fb79da276be904ada90a5a31bad
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937919"
---
# <a name="secannotateexe-net-security-annotator-tool"></a>SecAnnotate.exe (strumento .NET Security Annotator)
Lo strumento .NET Security Annotator (SecAnnotate.exe) è un'applicazione da riga di comando che identifica le parti `SecurityCritical` e `SecuritySafeCritical` di uno o più assembly.  
  
 Un'estensione di Visual Studio, [Security Annotator](https://marketplace.visualstudio.com/items?itemName=sheldonb.SecurityAnnotator), offre un'interfaccia utente grafica a SecAnnotate.exe e consente di eseguire lo strumento da Visual Studio.  
  
 Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7). Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).  
  
 Al prompt dei comandi, digitare quanto segue, i cui *parametri* vengono illustrati nella sezione seguente e gli *assembly* consistono di uno o più nomi di assembly separati da spazi vuoti:  
  
## <a name="syntax"></a>Sintassi  
  
```console  
SecAnnotate.exe [parameters] [assemblies]  
```  
  
## <a name="parameters"></a>Parametri  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|`/a`<br /><br /> oppure<br /><br /> `/showstatistics`|Mostra le statistiche sull'utilizzo della trasparenza negli assembly analizzati.|  
|*directory* `/d:`<br /><br /> oppure<br /><br /> *directory* `/referencedir:`|Specifica una directory in cui cercare gli assembly dipendenti durante l'annotazione.|  
|`/i`<br /><br /> oppure<br /><br /> `/includesignatures`|Include informazioni estese sulle firme nel file di rapporto sulle annotazioni.|  
|`/n`<br /><br /> oppure<br /><br /> `/nogac`|Interrompe la ricerca degli assembly di riferimento nella Global Assembly Cache.|  
|`/o:` *output. XML*<br /><br /> oppure<br /><br /> `/out:` *output. XML*|Specifica il file delle annotazioni di output.|  
|`/p:` *maxpasses*<br /><br /> oppure<br /><br /> `/maximumpasses:` *maxpasses*|Specifica il numero massimo di passaggi di aggiunta annotazioni da effettuare sugli assembly prima di interrompere la generazione di nuove annotazioni.|  
|`/q`<br /><br /> oppure<br /><br /> `/quiet`|Specifica una modalità non interattiva, nella quale l'annotatore non restituisce messaggi di stato, ma solo informazioni sugli errori.|  
|*assembly* `/r:`<br /><br /> oppure<br /><br /> *assembly* `/referenceassembly:`|Include l'assembly specificato quando vengono risolti gli assembly dipendenti durante l'annotazione. Gli assembly di riferimento sono prioritari rispetto agli assembly trovati nel percorso di riferimento.|  
|`/s:` *RuleName*<br /><br /> oppure<br /><br /> `/suppressrule:` *RuleName*|Elimina l'esecuzione della regola di trasparenza specificata sugli assembly di input.|  
|`/t`<br /><br /> oppure<br /><br /> `/forcetransparent`|Forza lo strumento di annotazione a trattare tutti gli assembly che non dispongono di alcuna annotazione di trasparenza come se fossero completamente trasparenti.|  
|`/t`:*assembly*<br /><br /> oppure<br /><br /> `/forcetransparent`:*assembly*|Forza la trasparenza per l'assembly specificato, a prescindere dalle relative annotazioni correnti a livello di assembly.|  
|||  
|`/v`<br /><br /> oppure<br /><br /> `/verify`|Verifica solo che le annotazioni di un assembly siano corrette. Non tenta di eseguire più passaggi per trovare tutte le annotazioni necessarie se non supera la verifica.|  
|`/x`<br /><br /> oppure<br /><br /> `/verbose`|Specifica un output dettagliato durante l'annotazione.|  
|*directory* `/y:`<br /><br /> oppure<br /><br /> *directory* `/symbolpath:`|Include la directory specificata quando si ricercano file di simboli durante l'annotazione.|  
  
## <a name="remarks"></a>Note  
 Parametri e assembly possono essere forniti anche in un file di risposta specificato sulla riga di comando, preceduti dal simbolo di chiocciola (@). Ogni riga nel file di risposta deve contenere un solo parametro o nome di assembly.  
  
 Per altre informazioni su .NET Security Annotator, vedere il post [Using SecAnnotate to Analyze Your Assemblies for Transparency Violations](https://docs.microsoft.com/archive/blogs/shawnfa/using-secannotate-to-analyze-your-assemblies-for-transparency-violations-an-example) (Uso di SecAnnotate per analizzare gli assembly con lo scopo di identificare violazioni di trasparenza) nel blog .NET Security.  
  
## <a name="examples"></a>Esempi
