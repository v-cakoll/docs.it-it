---
title: Ubicazione degli assembly
ms.date: 03/30/2017
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
ms.openlocfilehash: 5eb7b5c35bb40d5a58390ccbd4619cbed4e06c52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119963"
---
# <a name="assembly-placement"></a>Ubicazione degli assembly
Per la maggior parte delle applicazioni .NET Framework, gli assembly che costituiscono un'applicazione si trovano nella directory dell'applicazione stessa, in una sottodirectory della directory dell'applicazione o nella Global Assembly Cache (nel caso in cui l'assembly sia condiviso). È possibile eseguire l'override della posizione in cui il Common Language Runtime cerca un assembly usando l' [ \<elemento codebase>](../configure-apps/file-schema/runtime/codebase-element.md) in un file di configurazione. Se l'assembly non ha un nome sicuro, il percorso specificato tramite l' [ \<elemento codebase>](../configure-apps/file-schema/runtime/codebase-element.md) è limitato alla directory dell'applicazione o a una sottodirectory. Se l'assembly ha un nome sicuro, l' [ \<elemento codebase>](../configure-apps/file-schema/runtime/codebase-element.md) può specificare qualsiasi percorso nel computer o in una rete.  
  
 Regole simili vengono adottate per l'individuazione degli assembly quando si utilizza codice non gestito o applicazioni di interoperabilità COM: se l'assembly verrà condiviso da più applicazioni, è opportuno installarlo nella Global Assembly Cache. Gli assembly utilizzati con codice non gestito devono essere esportati come librerie di tipi e registrati. Gli assembly utilizzati dall'interoperabilità COM devono essere registrati nel catalogo. Tale registrazione viene talvolta compiuta automaticamente.  
  
## <a name="see-also"></a>Vedere anche

- [Modalità di individuazione degli assembly da parte del runtime](../deployment/how-the-runtime-locates-assemblies.md)
- [Configurazione di applicazioni](../configure-apps/index.md)
- [Interoperabilità con codice non gestito](../interop/index.md)
- [Assembly in .NET](index.md)
