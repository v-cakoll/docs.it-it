---
title: Posizione dell'assembly
ms.date: 08/20/2019
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
ms.openlocfilehash: d44fb44db35b60f99583c20432c5998573298044
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107221"
---
# <a name="assembly-location"></a>Posizione dell'assembly
La posizione dell'assembly determina se Common Language Runtime può individuarlo quando rileva un riferimento all'assembly e può determinare se l'assembly è condivisibile con altri assembly. È possibile distribuire un assembly nelle seguenti posizioni:  
  
- Directory o sottodirectory dell'applicazione.  
  
     Questa è la posizione più comune per la distribuzione di un assembly. Le sottodirectory della directory radice di un'applicazione possono essere basate sulla lingua o sulle impostazioni cultura. Se un assembly dispone di informazioni nell'attributo delle impostazioni cultura, deve trovarsi in una sottodirectory della directory dell'applicazione con il nome delle impostazioni cultura specificato nell'attributo.  
  
- Global Assembly Cache.  
  
     Cache di codice a livello dell'intero computer che viene installata nella stessa posizione di Common Language Runtime. Nella maggior parte dei casi se si prevede di condividere un assembly con più applicazioni è cosigliabile distribuirlo nella Global Assembly Cache.  
  
- In un server HTTP.  
  
     Un assembly distribuito in un server HTTP deve avere un nome sicuro. È possibile specificare l'assembly nella sezione codebase del file di configurazione dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di assembly](create.md)
- [Assembly Cache globale](../../framework/app-domains/gac.md)
- [Come il runtime individua gli assembly](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [Programma con assembly](program.md)
