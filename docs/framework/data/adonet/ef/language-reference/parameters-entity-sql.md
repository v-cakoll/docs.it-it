---
title: Parametri (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 47a1514933904daa623adc151d50525f011e07a7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187674"
---
# <a name="parameters-entity-sql"></a>Parametri (Entity SQL)
I parametri sono variabili definite esternamente a [!INCLUDE[esql](../../../../../../includes/esql-md.md)], generalmente tramite un'API di associazione usata da un linguaggio host. Ogni parametro è associato a un nome e un tipo. I nomi dei parametri sono definiti nelle espressioni di query con il simbolo chiocciola (@) come prefisso. Questo consente di distinguerli dai nomi di proprietà o dagli altri nomi definiti nella query.  
  
 L'API di associazione del linguaggio host fornisce le API per l'associazione dei parametri.  
  
## <a name="example"></a>Esempio  
  
```  
select c   
      from LOB.Customers as c   
      where c.Name = @name  
```  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Cenni preliminari su Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
