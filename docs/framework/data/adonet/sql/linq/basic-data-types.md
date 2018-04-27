---
title: Tipi di dati di base
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: e88767bd478b4b59e8c395473cfd8a36aaf68f3b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="basic-data-types"></a>Tipi di dati di base
Poiché le query LINQ to SQL vengono convertite in Transact-SQL prima di essere eseguite in Microsoft SQL Server, in LINQ to SQL è supportata buona parte delle funzionalità predefinite di SQL Server  per i tipi di dati di base.  
  
## <a name="casting"></a>Cast  
 I cast impliciti o espliciti vengono abilitati da un tipo CLR di origine in un tipo CLR di destinazione se è disponibile una conversione valida simile all'interno di SQL Server. Per ulteriori informazioni sui cast CLR, vedere [funzione CType](~/docs/visual-basic/language-reference/functions/ctype-function.md) (Visual Basic) e [come](~/docs/csharp/language-reference/keywords/as.md). Dopo la conversione i cast modificano il comportamento delle operazioni eseguite su un'espressione CLR, in modo che corrisponda a quello di altre espressioni CLR di cui viene eseguito naturalmente il mapping al tipo di destinazione. I cast sono inoltre convertibili nel contesto del mapping di ereditarietà. È possibile eseguire il cast degli oggetti in sottotipi dell'entità più specifici, in modo che sia possibile accedere ai dati specifici del sottotipo.  
  
## <a name="equality-operators"></a>Operatori di uguaglianza  
 LINQ to SQL all'interno di query LINQ to SQL supporta i seguenti operatori di uguaglianza sui tipi di dati di base:  
  
-   Operatore di uguaglianza e disuguaglianza: tali operatori sono supportati per i tipi numerici <xref:System.Boolean>, <xref:System.DateTime> e <xref:System.TimeSpan>. Per ulteriori informazioni sugli operatori di Visual Basic `=` e `<>`, vedere [gli operatori di confronto](~/docs/visual-basic/language-reference/operators/comparison-operators.md). Per ulteriori informazioni sugli operatori di confronto c# `==` e `!=`, vedere [Operator = =](~/docs/csharp/language-reference/operators/equality-comparison-operator.md) e [! = (operatore)](~/docs/csharp/language-reference/operators/not-equal-operator.md)rispettivamente  
  
-   Operatore Is: l'operatore `IS` supporta la conversione quando viene usato il mapping di ereditarietà. È possibile usarlo invece di testare direttamente la colonna del discriminatore per determinare se un oggetto è di un tipo di entità specifico e viene convertito in un controllo nella colonna del discriminatore. Per ulteriori informazioni sugli operatori di Visual Basic e C#, vedere [operatore Is](~/docs/visual-basic/language-reference/operators/is-operator.md) e [è](~/docs/csharp/language-reference/keywords/is.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Mapping del tipo SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)  
 [Tipi di dati e funzioni](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
