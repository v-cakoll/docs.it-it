---
title: Riferimento all'assembly Friend &lt;riferimento&gt; non è valido
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: cdedcc18aa82f6efd8c52cdca5d915d7d78e269f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611930"
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a>Riferimento all'assembly Friend &lt;riferimento&gt; non è valido
Riferimento all'assembly Friend \<riferimento > non è valido. Gli assembly firmati con nome sicuro devono specificare una chiave pubblica nelle relative dichiarazioni InternalsVisibleTo.  
  
 Il nome dell'assembly passato per il <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> costruttore di attributo identifica un assembly con nome sicuro, ma non include un `PublicKey` attributo.  
  
 **ID errore:** BC31535  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Determinare la chiave pubblica dell'assembly friend sicuro. Includere la chiave pubblica come parte del nome dell'assembly passato al <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> costruttore di attributo tramite la `PublicKey` attributo.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Reflection.AssemblyName>
- [Assembly Friend](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)


