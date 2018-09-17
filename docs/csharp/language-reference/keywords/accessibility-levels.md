---
title: Livelli di accessibilità (Riferimenti per C#)
ms.date: 12/06/2017
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
ms.openlocfilehash: 4679fd2564454e7f1ade5cb4813729b65f433012
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45617058"
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
|`enum`|`public`|nessuno|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|nessuno|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 L'accessibilità di un tipo annidato dipende dal relativo [dominio di accessibilità](../../../csharp/language-reference/keywords/accessibility-domain.md), che è determinato dall'accessibilità dichiarata del membro e dal dominio di accessibilità del tipo contenitore. Tuttavia il dominio di accessibilità di un tipo annidato non può essere superiore a quello del tipo che lo contiene.  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
- [Modificatori di accesso](../../../csharp/language-reference/keywords/access-modifiers.md)  
- [Dominio di accessibilità](../../../csharp/language-reference/keywords/accessibility-domain.md)  
- [Restrizioni relative all'uso dei livelli di accessibilità](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
- [Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
- [public](../../../csharp/language-reference/keywords/public.md)  
- [private](../../../csharp/language-reference/keywords/private.md)  
- [protected](../../../csharp/language-reference/keywords/protected.md)  
- [internal](../../../csharp/language-reference/keywords/internal.md)
