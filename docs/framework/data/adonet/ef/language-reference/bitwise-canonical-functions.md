---
title: Funzioni canoniche bit per bit
ms.date: 03/30/2017
ms.assetid: 993868ca-16e3-47b6-9915-c29cd63b0a21
ms.openlocfilehash: df3b81a47b8e1202884a5c38f55c7061279b245f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761194"
---
# <a name="bitwise-canonical-functions"></a>Funzioni canoniche bit per bit
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] include funzioni canoniche bit per bit.  
  
## <a name="remarks"></a>Note  
 Nella tabella seguente sono illustrate le funzioni canoniche bit per bit [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Queste funzioni restituiscono `Null` se `Null` viene specificato l'input. Il tipo restituito delle funzioni sarà uguale ai tipi di argomenti. Gli argomenti devono essere dello stesso tipo, se la funzione ne accetta più di uno. Per eseguire operazioni bit per bit tra tipi diversi, è necessario eseguire il cast in modo esplicito lo stesso tipo.  
  
|Funzione|Descrizione|  
|--------------|-----------------|  
|`BitWiseAnd (` `value1` `,`  `value2` `)`|Restituisce la congiunzione bit per bit di `value1` e `value2` come tipo di `value1` e `value2`.<br /><br /> **Argomenti**<br /><br /> Oggetto `Byte`, `Int16`, `Int32`, e `Int64`.<br /><br /> **Esempio**<br /><br /> `-- The following example returns 1.`<br /><br /> `BitWiseAnd(1,3)`|  
|`BitWiseNot (` `value` `)`|Restituisce la negazione bit per bit di `value`.<br /><br /> **Argomenti**<br /><br /> Oggetto `Byte`, `Int16`, `Int32`, e `Int64`.<br /><br /> **Esempio**<br /><br /> `-- The following example returns -4.`<br /><br /> `BitWiseNot(3)`|  
|`BitWiseOr (` `value1` `,`  `value2` `)`|Restituisce la disgiunzione bit per bit di `value1` e `value2` come tipo di `value1` e `value2`.<br /><br /> **Argomenti**<br /><br /> Oggetto `Byte`, `Int16`, `Int32` e `Int64`.<br /><br /> **Esempio**<br /><br /> `-- The following example returns 3.`<br /><br /> `BitWiseOr(1,3)`|  
|`BitWiseXor (` `value1` `,`  `value2` `)`|Restituisce la disgiunzione esclusiva bit per bit di `value1` e `value2` come tipo di `value1` e `value2`.<br /><br /> **Argomenti**<br /><br /> Oggetto `Byte`, `Int16`, `Int32` e `Int64`.<br /><br /> **Esempio**<br /><br /> `-- The following example returns 2.`<br /><br /> `BitWiseXor (1,3)`|  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
