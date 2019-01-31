---
title: Il riferimento all'assembly Friend <reference> non è valido
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: ff2cdbebe13f6224209ef8da62600c99348c911b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286819"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a>Riferimento all'assembly Friend \<riferimento > non è valido
Riferimento all'assembly Friend \<riferimento > non è valido. Gli assembly firmati con nome sicuro devono specificare una chiave pubblica nelle relative dichiarazioni InternalsVisibleTo.  
  
 Il nome dell'assembly passato per il <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> costruttore di attributo identifica un assembly con nome sicuro, ma non include un `PublicKey` attributo.  
  
 **ID errore:** BC31535  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Determinare la chiave pubblica dell'assembly friend sicuro. Includere la chiave pubblica come parte del nome dell'assembly passato al <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> costruttore di attributo tramite la `PublicKey` attributo.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Reflection.AssemblyName>
- [Assembly Friend](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)


