---
title: Livelli di accessibilità - Riferimenti per C#
ms.date: 12/06/2017
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
ms.openlocfilehash: 26fbc2a6d86aead537465c304146630f8bcd3ad4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713821"
---
# <a name="accessibility-levels-c-reference"></a>Livelli di accessibilità (Riferimenti per C#)

Usare i modificatori di accesso `public`, `protected`, `internal` o `private` per specificare uno dei livelli seguenti di accessibilità dichiarata per i membri.  
  
|Accessibilità dichiarata|Significato|  
|----------------------------|-------------|  
|[`public`](public.md)|L'accesso non è limitato.|  
|[`protected`](protected.md)|L'accesso è limitato alla classe o ai tipi derivati dalla classe che li contiene.|  
|[`internal`](internal.md)|L'accesso è limitato all'assembly corrente.|  
|[`protected internal`](protected-internal.md)|L'accesso è limitato all'assembly corrente o ai tipi derivati dalla classe che li contiene.|  
|[`private`](private.md)|L'accesso è limitato al tipo contenitore.|  
|[`private protected`](private-protected.md)|L'accesso è limitato alla classe o ai tipi derivati dalla classe che li contiene all'interno dell'assembly corrente. Disponibile da C# 7.2. |  
  
 Per un membro o un tipo è consentito solo un modificatore di accesso, tranne quando si usano le combinazioni `protected internal` o `private protected`.  
  
 I modificatori di accesso non sono consentiti negli spazi dei nomi. Gli spazi dei nomi non hanno restrizioni di accesso.  
  
 A seconda del contesto in cui si verifica una dichiarazione di membro, sono consentite solo determinate accessibilità dichiarate. Se non è specificato nessun modificatore di accesso in una dichiarazione di membro, viene usata un'accessibilità predefinita.  
  
 I tipi di primo livello, che non sono annidati in altri tipi, possono avere solo l'accessibilità `internal` o `public`. L'accessibilità predefinita per questi tipi è `internal`.  
  
 I tipi annidati, che sono membri di altri tipi, possono avere accessibilità dichiarate come indicato nella tabella seguente.  
  
|Membri di|Accessibilità predefinita del membro|Accessibilità dichiarate e consentite del membro|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|nessuna|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|nessuna|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 L'accessibilità di un tipo annidato dipende dal relativo [dominio di accessibilità](./accessibility-domain.md), che è determinato dall'accessibilità dichiarata del membro e dal dominio di accessibilità del tipo contenitore. Tuttavia il dominio di accessibilità di un tipo annidato non può essere superiore a quello del tipo che lo contiene.  
  
## <a name="c-language-specification"></a>Specifica del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](./index.md)
- [Modificatori di accesso](./access-modifiers.md)
- [Dominio di accessibilità](./accessibility-domain.md)
- [Restrizioni relative all'uso dei livelli di accessibilità](./restrictions-on-using-accessibility-levels.md)
- [Modificatori di accesso](../../programming-guide/classes-and-structs/access-modifiers.md)
- [public](./public.md)
- [private](./private.md)
- [protected](./protected.md)
- [internal](./internal.md)
