---
title: Uso di assembly e di Global Assembly Cache | Microsoft Docs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, benefits
- ACLs [.NET Framework]
- GAC (global assembly cache), benefits
- access control lists [.NET Framework]
ms.assetid: 8a18e5c2-d41d-49ef-abcb-7c27e2469433
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5a3312180542df8d59e30c6fc803d7ba24c7757e
ms.contentlocale: it-it
ms.lasthandoff: 06/02/2017

---
# <a name="working-with-assemblies-and-the-global-assembly-cache"></a>Utilizzo di assembly e della Global Assembly Cache
Se si vuole condividere un assembly tra diverse applicazioni, è possibile installarlo nella Global Assembly Cache. Tale cache di codice a livello di computer si trova su ogni computer in cui è installato Common Language Runtime. La Global Assembly Cache memorizza gli assembly specificamente designati per essere condivisi da più applicazioni sul computer. L'assembly deve avere un nome sicuro per essere installato nella Global Assembly Cache.  
  
> [!NOTE]
>  Gli assembly nella Global Assembly Cache devono avere lo stesso nome di assembly e lo stesso nome di file, ad esclusione dell'estensione del nome del file. Ad esempio, un assembly con il nome assembly myAssembly deve avere un nome di file myAssembly.exe o myAssembly.dll.  
  
 Per condividere gli assembly, installarli nella Global Assembly Cache solo quando è necessario. Come regola generale, mantenere le dipendenze degli assembly private e individuare gli assembly nella directory dell'applicazione, a meno che la condivisione di un assembly non venga richiesta in modo esplicito. Non è necessario installare gli assembly nella Global Assembly Cache per renderli accessibili al codice non gestito o all'interoperabilità COM.  
  
 Esistono diverse ragioni per cui installare un assembly nella Global Assembly Cache:  
  
-   Percorso condiviso.  
  
     Gli assembly che devono essere usati dalle applicazioni possono essere inseriti nella Global Assembly Cache. Ad esempio, se tutte le applicazioni devono usare un assembly nella Global Assembly Cache, è possibile aggiungere un'istruzione di criteri di versione al file Machine.config che reindirizza i riferimenti all'assembly.  
  
-   Sicurezza dei file.  
  
     Gli amministratori spesso proteggono la directory systemroot usando un elenco di controllo di accesso (ACL) per controllare l'accesso in scrittura ed esecuzione. Poiché la Global Assembly Cache viene installata nella directory systemroot, eredita l'ACL di tale directory. È consigliabile che solo gli utenti con privilegi di amministratore siano autorizzati a eliminare file dalla Global Assembly Cache.  
  
-   Controllo delle versioni side-by-side.  
  
     Nella Global Assembly Cache possono essere gestite più copie di assembly con lo stesso nome ma con informazioni di versione diverse.  
  
-   Altri percorsi di ricerca.  
  
     Common language runtime cerca nella Global Assembly Cache un assembly che corrisponda alla richiesta di assembly prima di effettuare l'esecuzione del probe o usare le informazioni della base di codici in un file di configurazione.  
  
 Si noti che esistono scenari in cui si sceglie in modo esplicito di non installare un assembly nella Global Assembly Cache. Se si inserisce uno degli assembly che costituiscono un'applicazione nella Global Assembly Cache, non sarà più possibile replicare o installare l'applicazione usando il comando XCOPY per copiare la directory dell'applicazione. In questo caso è necessario anche spostare l'assembly nella Global Assembly Cache.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: Installare un assembly nella Global Assembly Cache](../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 Vengono descritte le modalità di installazione di un assembly nella Global Assembly Cache.  
  
 [Procedura: Visualizzare il contenuto della Global Assembly Cache](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md)  
 Illustra come usare [lo strumento Global Assembly Cache (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) per visualizzare i contenuti della Global Assembly Cache.  
  
 [Procedura: Rimuovere un assembly dalla Global Assembly Cache](../../../docs/framework/app-domains/how-to-remove-an-assembly-from-the-gac.md)  
 Illustra come usare [lo strumento Global Assembly Cache (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) per rimuovere un assembly dalla Global Assembly Cache.  
  
 [Uso dei componenti serviti con la Global Assembly Cache](../../../docs/framework/app-domains/use-serviced-components-with-the-gac.md)  
 È consigliabile inserire nella Global Assembly Cache i componenti serviti (componenti COM+ di codice gestito).  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Creazione degli assembly](../../../docs/framework/app-domains/create-assemblies.md)  
 Offre una panoramica della creazione di assembly.  
  
 [Global Assembly Cache](../../../docs/framework/app-domains/gac.md)  
 Descrive la Global Assembly Cache.  
  
 [Procedura: Visualizzare il contenuto dell'assembly](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 Illustra come usare [Ildasm.exe (Disassembler IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) per visualizzare le informazioni di Microsoft Intermediate Language (MSIL) in un assembly.  
  
 [Come il runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 Descrive in che modo Common Language Runtime individua e carica gli assembly che costituiscono l'applicazione.  
  
 [Programmazione con gli assembly](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 Descrive gli assembly, i blocchi predefiniti delle applicazioni gestite.
