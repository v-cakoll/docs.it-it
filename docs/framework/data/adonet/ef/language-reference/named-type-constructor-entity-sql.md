---
title: Costruttore di tipo denominato (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: f40adce1a9e031ed0b7cd5d03d9c63db255aa610
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319567"
---
# <a name="named-type-constructor-entity-sql"></a>Costruttore di tipo denominato (Entity SQL)
Utilizzato per creare istanze di tipi nominali del modello concettuale, ad esempio i tipi di entità o i tipi complessi.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a>argomenti  
 `identifier`  
 Valore che rappresenta un identificatore semplice o delimitato. Per ulteriori informazioni, vedere [identificatori](identifiers-entity-sql.md)  
  
 `expression`  
 Attributi del tipo che si presuppone essere nello stesso ordine in cui appaiono nella dichiarazione del tipo.  
  
## <a name="return-value"></a>Valore restituito  
 Istanze di tipi di entità e di tipi complessi denominati.  
  
## <a name="remarks"></a>Note  
 Negli esempi seguenti viene illustrato come costruire i tipi nominali e complessi:  
  
 L'espressione seguente consente di creare un'istanza di un tipo `Person` :  
  
 `Person("abc", 12)`  
  
 L'espressione seguente consente di creare un'istanza di un tipo complesso:  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 L'espressione seguente consente di creare un'istanza di un tipo complesso annidato:  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 L'espressione seguente consente di creare un'istanza di un'entità con un tipo complesso annidato:  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 Nell'esempio seguente viene illustrato come inizializzare una proprietà di un tipo complesso impostandola su Null:`MyModel.ZipCode(‘98118’, null)`.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato il costruttore di tipi denominati per creare un'istanza di un tipo di modello concettuale. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#NAMED_TYPE_CONSTRUCTOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#named_type_constructor)]  
  
## <a name="see-also"></a>Vedere anche

- [Costruzione di tipi](constructing-types-entity-sql.md)
- [Riferimento a Entity SQL](entity-sql-reference.md)
