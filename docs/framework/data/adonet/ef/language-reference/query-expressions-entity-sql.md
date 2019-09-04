---
title: Espressioni di query (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
ms.openlocfilehash: 4428286890f41573a02daf31a4593d0c8f9ad34b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249281"
---
# <a name="query-expressions-entity-sql"></a>Espressioni di query (Entity SQL)
Un'espressione di query combina numerosi operatori di query diversi in un'unica sintassi. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]in sono disponibili vari tipi di espressioni, tra cui i seguenti: [valori letterali](literals-entity-sql.md), [parametri](parameters-entity-sql.md), [variabili](variables-entity-sql.md), operatori, [funzioni](functions-entity-sql.md), operatori di set e così via. Per ulteriori informazioni, vedere [Entity SQL Reference](entity-sql-reference.md).  
  
## <a name="clauses"></a>Clausole  
 Un'espressione di query è composta da una serie di clausole che consentono di applicare operazioni successive a una raccolta di oggetti. Si basano sulle stesse clausole disponibili nell'istruzione SQL SELECT standard: [Select](select-entity-sql.md), [from](from-entity-sql.md), [where](where-entity-sql.md), [Group by](group-by-entity-sql.md), [having](having-entity-sql.md)e [Order by](order-by-entity-sql.md).  
  
## <a name="scope"></a>Ambito  
 I nomi definiti nella clausola FROM vengono introdotti nell'ambito FROM in base all'ordine con cui appaiono, da sinistra verso destra. Nell'elenco JOIN le espressioni possono fare riferimento ai nomi definiti precedentemente nell'elenco. Le proprietà pubbliche degli elementi identificati nella clausola FROM non vengono aggiunte all'ambito FROM: È necessario farvi sempre riferimento tramite il nome completo dell'alias. In genere, tutte le parti dell'espressione SELECT vengono considerate all'interno dell'ambito FROM.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
