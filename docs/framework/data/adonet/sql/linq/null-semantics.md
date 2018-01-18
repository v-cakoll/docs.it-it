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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8d32f73c8c2095c23ec164ad40fd1ab27ef1153a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
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
