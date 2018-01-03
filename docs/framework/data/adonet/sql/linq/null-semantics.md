---
title: Semantica Null
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6786c7ea4441b1a753d6f0b4213f40fa64dcb4ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="null-semantics"></a>Semantica Null
La tabella seguente fornisce i collegamenti alle varie parti della documentazione di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in cui sono descritti i problemi relativi a `null` (`Nothing` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]).  
  
|Argomento|Descrizione|  
|-----------|-----------------|  
|[Tipi SQL-CLR non corrispondenti](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|La sezione sulla semantica null di questo argomento include una discussione relativa al tipo booleano SQL a tre stati rispetto al tipo Common Language Runtime (CLR) a due stati <xref:System.Boolean>, ai tipi letterali `Nothing` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) e `null` (C#) e altri problemi simili.|  
|[Conversione dell'operatore query standard](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|Nella sezione sulla semantica null di questo argomento viene descritta la semantica di confronto null in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].|  
|[Metodi System.String](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|Nella sezione sulle differenze rispetto a .NET di questo argomento viene descritto come un risultato 0 restituito da <xref:System.String.LastIndexOf%2A> possa significare che la stringa è null o che la posizione trovata è 0.|  
|[Calcolare la somma dei valori in una sequenza numerica](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|Viene descritto come l'operatore <xref:System.Linq.Enumerable.Sum%2A> restituisca `null` (`Nothing` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) anziché 0 per una sequenza vuota o che contiene solo valori null.|  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati e funzioni](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
