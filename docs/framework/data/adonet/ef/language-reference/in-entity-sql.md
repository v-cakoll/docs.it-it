---
title: IN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: e46db63600b6baa03697615a2f5eb9240f55d15e
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833690"
---
# <a name="in-entity-sql"></a>IN (Entity SQL)
Determina se un valore corrisponde a qualsiasi valore in una raccolta.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a>Argomenti  
 `value`  
 Qualsiasi espressione valida che restituisce il valore di cui trovare la corrispondenza.  
  
 [ NOT ]  
 Specifica la negazione del risultato `Boolean` di IN.  
  
 `expression`  
 Qualsiasi espressione valida che restituisce la raccolta da testare per trovare una corrispondenza. Tutte le espressioni devono essere dello stesso tipo o di un tipo di base o derivato comune di `value`.  
  
## <a name="return-value"></a>Valore restituito  
 `true` se il valore viene trovato nella raccolta; null se il valore è null o se la raccolta è null; in caso contrario `false`. L'utilizzo di NOT IN consente di negare i risultati di IN.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore IN per determinare se un valore corrisponde a qualsiasi valore in una raccolta. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Seguire la procedura descritta in [How per: Eseguire una query che restituisce i risultati di StructuralType @ no__t-0.  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#IN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#in)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
