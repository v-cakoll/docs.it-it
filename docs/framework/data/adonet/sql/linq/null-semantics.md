---
title: Semantica Null
ms.date: 03/30/2017
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
ms.openlocfilehash: eb1e96ba44c5d64e8366a654c2d06d89c9b46c9a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172757"
---
# <a name="null-semantics"></a>Semantica Null
Nella tabella seguente vengono forniti collegamenti alle varie parti della [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentazione in cui `null` (`Nothing` in Visual Basic) vengono descritti i problemi.  
  
|Argomento|Descrizione|  
|-----------|-----------------|  
|[Tipi SQL-CLR non corrispondenti](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|La sezione "Semantica Null" di questo argomento include una discussione relativa al tipo booleano SQL a tre stati rispetto a due stati common language runtime (CLR) <xref:System.Boolean>, il valore letterale `Nothing` (Visual Basic) e `null` (C#) e altri simili problemi.|  
|[Conversione dell'operatore query standard](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|Nella sezione sulla semantica null di questo argomento viene descritta la semantica di confronto null in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].|  
|[Metodi System.String](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|Nella sezione sulle differenze rispetto a .NET di questo argomento viene descritto come un risultato 0 restituito da <xref:System.String.LastIndexOf%2A> possa significare che la stringa è null o che la posizione trovata è 0.|  
|[Calcolare la somma dei valori in una sequenza numerica](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|Viene descritto come la <xref:System.Linq.Enumerable.Sum%2A> operatore restituisce `null` (`Nothing` in Visual Basic) anziché 0 per una sequenza che contiene solo valori null o una sequenza vuota.|  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati e funzioni](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
