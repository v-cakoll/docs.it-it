---
title: Espressioni di query (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8b30deea78efe275ccaf6beabafb16a84357ba26
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="query-expressions-entity-sql"></a>Espressioni di query (Entity SQL)
Un'espressione di query combina numerosi operatori di query diversi in un'unica sintassi. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]Fornisce i vari tipi di espressioni, inclusi i seguenti: [valori letterali](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md), [parametri](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md), [variabili](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md), operatori, [funzioni](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)operatori sui set e così via. Per ulteriori informazioni, vedere [riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md).  
  
## <a name="clauses"></a>Clausole  
 Un'espressione di query è composta da una serie di clausole che consentono di applicare operazioni successive a una raccolta di oggetti. Sono basate su stesse clausole presenti nello standard di un'istruzione SQL select: [selezionare](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md), [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [in](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md), [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), [Con](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md), e [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md).  
  
## <a name="scope"></a>Ambito  
 I nomi definiti nella clausola FROM vengono introdotti nell'ambito FROM in base all'ordine con cui appaiono, da sinistra verso destra. Nell'elenco JOIN le espressioni possono fare riferimento ai nomi definiti precedentemente nell'elenco. Le proprietà pubbliche degli elementi identificate nella clausola FROM non vengono aggiunte all'ambito FROM, ma è sempre necessario fare riferimento a queste proprietà tramite il nome completo dell'alias. In genere, tutte le parti dell'espressione SELECT vengono considerate all'interno dell'ambito FROM.  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
