---
title: MULTISET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
ms.openlocfilehash: 222be86db434b5d41c7b0536d271a3750b6afbe8
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319589"
---
# <a name="multiset-entity-sql"></a>MULTISET (Entity SQL)
Crea un'istanza di un multiset da un elenco di valori. Tutti i valori nel costruttore MULTISET devono essere di un tipo `T`compatibile. Non sono consentiti costruttori multiset vuoti.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
MULTISET ( expression [{, expression }] )  
-- or  
{ expression [{, expression }] }  
```  
  
## <a name="arguments"></a>argomenti  
 `expression`  
 Qualsiasi elenco valido di valori.  
  
## <a name="return-value"></a>Valore restituito  
 Raccolta di tipo MULTISET \<T >.  
  
## <a name="remarks"></a>Note  
 In[!INCLUDE[esql](../../../../../../includes/esql-md.md)] sono disponibili tre tipi di costruttori, ovvero costruttori di riga, costruttori di oggetti e costruttori di raccolte o multiset. Per altre informazioni, vedere [costruzione di tipi](constructing-types-entity-sql.md).  
  
 Il costruttore multiset crea un'istanza di un multiset da un elenco di valori. Tutti i valori nel costruttore devono essere di un tipo compatibile.  
  
 L'espressione seguente consente ad esempio di creare un multiset di valori interi.  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
> I valori letterali di multiset annidati sono supportati solo quando un multiset di wrapping ha un singolo elemento multiset. ad esempio, `{{1, 2, 3}}`. Quando il multiset di wrapping contiene più elementi multiset, ad esempio `{{1, 2}, {3, 4}}`, non sono supportati valori letterali di multiset annidati.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore MULTISET per creare un'istanza di un multiset da un elenco di valori. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#MULTISET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#multiset)]  
  
## <a name="see-also"></a>Vedere anche

- [Costruzione di tipi](constructing-types-entity-sql.md)
- [Riferimento a Entity SQL](entity-sql-reference.md)
