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
ms.openlocfilehash: a9b8357be5b9f49569114cbc1c2942eea03696eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180180"
---
# <a name="assembly-placement"></a>Ubicazione degli assembly
Per la maggior parte delle applicazioni .NET Framework, gli assembly che costituiscono un'applicazione si trovano nella directory dell'applicazione stessa, in una sottodirectory della directory dell'applicazione o nella Global Assembly Cache (nel caso in cui l'assembly sia condiviso). È possibile eseguire l'override del percorso usato da Common Language Runtime per cercare un assembly usando l'elemento [\<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) in un file di configurazione. Se l'assembly non ha un nome sicuro, il percorso specificato tramite l'elemento [\<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) sarà limitato alla directory dell'applicazione o a una sottodirectory. Se l'assembly ha un nome sicuro l'elemento [\<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) può specificare qualsiasi percorso nel computer o in una rete.  
  
 Regole simili vengono adottate per l'individuazione degli assembly quando si utilizza codice non gestito o applicazioni di interoperabilità COM: se l'assembly verrà condiviso da più applicazioni, è opportuno installarlo nella Global Assembly Cache. Gli assembly utilizzati con codice non gestito devono essere esportati come librerie di tipi e registrati. Gli assembly utilizzati dall'interoperabilità COM devono essere registrati nel catalogo. Tale registrazione viene talvolta compiuta automaticamente.  
  
## <a name="see-also"></a>Vedere anche

- [Come il runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Configurazione di applicazioni](../../../docs/framework/configure-apps/index.md)
- [Interoperabilità con codice non gestito](../../../docs/framework/interop/index.md)
- [Assembly in Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
