---
title: Posizione dell'assembly
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e069c1636004896bfb193fd70a352195ba045865
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="assembly-location"></a>Posizione dell'assembly
La posizione dell'assembly determina se Common Language Runtime può individuarlo quando rileva un riferimento all'assembly e può determinare se l'assembly è condivisibile con altri assembly. È possibile distribuire un assembly nelle seguenti posizioni:  
  
-   Directory o sottodirectory dell'applicazione.  
  
     Questa è la posizione più comune per la distribuzione di un assembly. Le sottodirectory della directory radice di un'applicazione possono essere basate sulla lingua o sulle impostazioni cultura. Se un assembly dispone di informazioni nell'attributo delle impostazioni cultura, deve trovarsi in una sottodirectory della directory dell'applicazione con il nome delle impostazioni cultura specificato nell'attributo.  
  
-   Global Assembly Cache.  
  
     Cache di codice a livello dell'intero computer che viene installata nella stessa posizione di Common Language Runtime. Nella maggior parte dei casi se si prevede di condividere un assembly con più applicazioni è cosigliabile distribuirlo nella Global Assembly Cache.  
  
-   In un server HTTP.  
  
     Un assembly distribuito in un server HTTP deve avere un nome sicuro. È possibile specificare l'assembly nella sezione codebase del file di configurazione dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione degli assembly](../../../docs/framework/app-domains/create-assemblies.md)  
 [Global Assembly Cache](../../../docs/framework/app-domains/gac.md)  
 [Come il runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Programmazione con gli assembly](../../../docs/framework/app-domains/programming-with-assemblies.md)
