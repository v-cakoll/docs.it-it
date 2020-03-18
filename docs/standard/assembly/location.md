---
title: Posizione dell'assembly
ms.date: 08/20/2019
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
ms.openlocfilehash: 0b84aba749625f0f86027cd9d09a5e9a2229a3f2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73733132"
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

- [Creare assembly](create.md)
- [Global Assembly Cache](../../framework/app-domains/gac.md)
- [Come il runtime individua gli assembly](../../framework/deployment/how-the-runtime-locates-assemblies.md)
