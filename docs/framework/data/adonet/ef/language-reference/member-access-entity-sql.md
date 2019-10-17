---
title: . (Accesso ai membri) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
ms.openlocfilehash: 8e63caba9e9efb91d5c4629b9da0b1feca905ace
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319653"
---
# <a name="-member-access-entity-sql"></a>. (Accesso ai membri) (Entity SQL)
L'operatore punto (.) è l'operatore di accesso ai membri [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. L'operatore di accesso ai membri viene usato per produrre il valore di una proprietà o di un campo di un'istanza del tipo di modello concettuale strutturale.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
expression.identifier  
```  
  
## <a name="arguments"></a>argomenti  
 `expression`  
 Istanza di un tipo di modello concettuale strutturale.  
  
 `identifier`  
 Proprietà o campo che appartiene a un'istanza dell'oggetto.  
  
## <a name="remarks"></a>Note  
 L'operatore punto (.) può essere usato per estrarre campi da un record, analogamente all'estrazione di proprietà di un tipo di entità o complesso. Se, ad esempio, un oggetto n di tipo Name è un membro del tipo Person e p è un'istanza del tipo Person, p.n è un'espressione di accesso ai membri valida che restituisce un valore di tipo Name.  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
