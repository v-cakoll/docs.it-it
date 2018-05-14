---
title: Ubicazione degli assembly
ms.date: 03/30/2017
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6a10a896494304b9c3c17bc320464a8273e430d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="assembly-placement"></a>Ubicazione degli assembly
Per la maggior parte delle applicazioni .NET Framework, gli assembly che costituiscono un'applicazione si trovano nella directory dell'applicazione stessa, in una sottodirectory della directory dell'applicazione o nella Global Assembly Cache (nel caso in cui l'assembly sia condiviso). È possibile eseguire l'override del percorso usato da Common Language Runtime per cercare un assembly usando l'elemento [\<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) in un file di configurazione. Se l'assembly non ha un nome sicuro, il percorso specificato tramite l'elemento [\<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) sarà limitato alla directory dell'applicazione o a una sottodirectory. Se l'assembly ha un nome sicuro l'elemento [\<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) può specificare qualsiasi percorso nel computer o in una rete.  
  
 Regole simili vengono adottate per l'individuazione degli assembly quando si utilizza codice non gestito o applicazioni di interoperabilità COM: se l'assembly verrà condiviso da più applicazioni, è opportuno installarlo nella Global Assembly Cache. Gli assembly utilizzati con codice non gestito devono essere esportati come librerie di tipi e registrati. Gli assembly utilizzati dall'interoperabilità COM devono essere registrati nel catalogo. Tale registrazione viene talvolta compiuta automaticamente.  
  
## <a name="see-also"></a>Vedere anche  
 [Come il runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Configurazione di applicazioni](../../../docs/framework/configure-apps/index.md)  
 [Interoperabilità COM avanzata](http://msdn.microsoft.com/library/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [Assembly in Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
