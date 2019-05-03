---
title: Espressioni di query (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
ms.openlocfilehash: 5f89028b9c501dd840f1dc9445418e4757967db8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61614622"
---
# <a name="query-expressions-entity-sql"></a>Espressioni di query (Entity SQL)
Un'espressione di query combina numerosi operatori di query diversi in un'unica sintassi. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] fornisce diversi tipi di espressioni, inclusi i seguenti: [valori letterali](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md), [parametri](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md), [variabili](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md), operatori, [funzioni](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)operatori sui set e così via. Per altre informazioni, vedere [riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md).  
  
## <a name="clauses"></a>Clausole  
 Un'espressione di query è composta da una serie di clausole che consentono di applicare operazioni successive a una raccolta di oggetti. Si basano sulle stesse clausole trovate nello standard di un'istruzione SQL select: [Selezionare](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md), [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [in cui](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md), [RAGGRUPPA](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md), e [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md).  
  
## <a name="scope"></a>Ambito  
 I nomi definiti nella clausola FROM vengono introdotti nell'ambito FROM in base all'ordine con cui appaiono, da sinistra verso destra. Nell'elenco JOIN le espressioni possono fare riferimento ai nomi definiti precedentemente nell'elenco. Proprietà pubbliche degli elementi identificate nella clausola FROM non vengono aggiunti all'ambito FROM: È necessario sempre fare riferimento tramite il nome completo dell'alias. In genere, tutte le parti dell'espressione SELECT vengono considerate all'interno dell'ambito FROM.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
