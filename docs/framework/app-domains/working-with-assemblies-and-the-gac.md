---
title: Utilizzo di assembly e della Global Assembly Cache
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, benefits
- ACLs [.NET Framework]
- GAC (global assembly cache), benefits
- access control lists [.NET Framework]
ms.assetid: 8a18e5c2-d41d-49ef-abcb-7c27e2469433
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0331e0ad30743d5f0bba125e8e61e636e1c2a5be
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053031"
---
# <a name="working-with-assemblies-and-the-global-assembly-cache"></a>Utilizzo di assembly e della Global Assembly Cache

Se si vuole condividere un assembly tra diverse applicazioni, è possibile installarlo nella Global Assembly Cache. Tale cache di codice a livello di computer si trova su ogni computer in cui è installato Common Language Runtime. La Global Assembly Cache memorizza gli assembly specificamente designati per essere condivisi da più applicazioni sul computer. L'assembly deve avere un nome sicuro per essere installato nella Global Assembly Cache.  
  
> [!NOTE]
> Gli assembly nella Global Assembly Cache devono avere lo stesso nome di assembly e lo stesso nome di file, ad esclusione dell'estensione del nome del file. Ad esempio, un assembly con il nome assembly myAssembly deve avere un nome di file myAssembly.exe o myAssembly.dll.  
  
Per condividere gli assembly, installarli nella Global Assembly Cache solo quando è necessario. Come regola generale, mantenere le dipendenze degli assembly private e individuare gli assembly nella directory dell'applicazione, a meno che la condivisione di un assembly non venga richiesta in modo esplicito. Non è necessario installare gli assembly nella Global Assembly Cache per renderli accessibili al codice non gestito o all'interoperabilità COM.  
  
Esistono diverse ragioni per cui installare un assembly nella Global Assembly Cache:  
  
- Percorso condiviso.  
  
     Gli assembly che devono essere usati dalle applicazioni possono essere inseriti nella Global Assembly Cache. Ad esempio, se tutte le applicazioni devono usare un assembly nella Global Assembly Cache, è possibile aggiungere un'istruzione di criteri di versione al file Machine.config che reindirizza i riferimenti all'assembly.  
  
- Sicurezza dei file.  
  
     Gli amministratori spesso proteggono la directory systemroot usando un elenco di controllo di accesso (ACL) per controllare l'accesso in scrittura ed esecuzione. Poiché la Global Assembly Cache viene installata nella directory systemroot, eredita l'ACL di tale directory. È consigliabile che solo gli utenti con privilegi di amministratore siano autorizzati a eliminare file dalla Global Assembly Cache.  
  
- Controllo delle versioni side-by-side.  
  
     Nella Global Assembly Cache possono essere gestite più copie di assembly con lo stesso nome ma con informazioni di versione diverse.  
  
- Altri percorsi di ricerca.  
  
     Common language runtime cerca nella Global Assembly Cache un assembly che corrisponda alla richiesta di assembly prima di effettuare l'esecuzione del probe o usare le informazioni della base di codici in un file di configurazione.  
  
 Si noti che esistono scenari in cui si sceglie in modo esplicito di non installare un assembly nella Global Assembly Cache. Se si inserisce uno degli assembly che costituiscono un'applicazione nella Global Assembly Cache, non sarà più possibile replicare o installare l'applicazione usando il comando XCOPY per copiare la directory dell'applicazione. In questo caso è necessario anche spostare l'assembly nella Global Assembly Cache.  
  
## <a name="in-this-section"></a>In questa sezione  
[Procedura: Installare un assembly nella Global Assembly Cache](install-assembly-into-gac.md)  
Vengono descritte le modalità di installazione di un assembly nella Global Assembly Cache.  
  
[Procedura: Visualizzare il contenuto della Global Assembly Cache](how-to-view-the-contents-of-the-gac.md)  
Illustra come usare [lo strumento Global Assembly Cache (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) per visualizzare i contenuti della Global Assembly Cache.  
  
[Procedura: Rimuovere un assembly dalla Global Assembly Cache](how-to-remove-an-assembly-from-the-gac.md)  
Illustra come usare [lo strumento Global Assembly Cache (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) per rimuovere un assembly dalla Global Assembly Cache.  
  
[Uso dei componenti serviti con la Global Assembly Cache](use-serviced-components-with-the-gac.md)  
È consigliabile inserire nella Global Assembly Cache i componenti serviti (componenti COM+ di codice gestito).  
  
## <a name="related-sections"></a>Sezioni correlate  

[Creazione degli assembly](../../standard/assembly/create.md)  
Offre una panoramica della creazione di assembly.  
  
[Global Assembly Cache](gac.md)  
Descrive la Global Assembly Cache.  
  
[Procedura: Visualizzare il contenuto degli assembly](../../standard/assembly/view-contents.md)  
Illustra come usare [Ildasm.exe (Disassembler IL)](../tools/ildasm-exe-il-disassembler.md) per visualizzare le informazioni di Microsoft Intermediate Language (MSIL) in un assembly.  
  
[Come il runtime individua gli assembly](../deployment/how-the-runtime-locates-assemblies.md)  
Descrive in che modo Common Language Runtime individua e carica gli assembly che costituiscono l'applicazione.  
  
[Programmazione con gli assembly](../../standard/assembly/program.md)  
Descrive gli assembly, i blocchi predefiniti delle applicazioni gestite.
