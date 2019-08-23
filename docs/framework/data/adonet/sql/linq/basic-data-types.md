---
title: Tipi di dati di base
ms.date: 03/30/2017
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
ms.openlocfilehash: b01a49afa99fc7ecdb7a113a5056e37d901527a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964070"
---
# <a name="basic-data-types"></a>Tipi di dati di base
Poiché le query LINQ to SQL vengono convertite in Transact-SQL prima di essere eseguite in Microsoft SQL Server, in LINQ to SQL è supportata buona parte delle funzionalità predefinite di SQL Server  per i tipi di dati di base.  
  
## <a name="casting"></a>Cast  
 I cast impliciti o espliciti vengono abilitati da un tipo CLR di origine in un tipo CLR di destinazione se è disponibile una conversione valida simile all'interno di SQL Server. Per ulteriori informazioni sul cast CLR, vedere la [funzione CType](../../../../../visual-basic/language-reference/functions/ctype-function.md) (Visual Basic) e [gli operatori di cast e](../../../../../csharp/language-reference/operators/type-testing-and-cast.md)di testing dei tipi. Dopo la conversione i cast modificano il comportamento delle operazioni eseguite su un'espressione CLR, in modo che corrisponda a quello di altre espressioni CLR di cui viene eseguito naturalmente il mapping al tipo di destinazione. I cast sono inoltre convertibili nel contesto del mapping di ereditarietà. È possibile eseguire il cast degli oggetti in sottotipi dell'entità più specifici, in modo che sia possibile accedere ai dati specifici del sottotipo.  
  
## <a name="equality-operators"></a>Operatori di uguaglianza  
 LINQ to SQL all'interno di query LINQ to SQL supporta i seguenti operatori di uguaglianza sui tipi di dati di base:  
  
- Operatore di uguaglianza e disuguaglianza: Gli operatori di uguaglianza e disuguaglianza sono supportati per i <xref:System.Boolean>tipi <xref:System.DateTime>numerici <xref:System.TimeSpan> ,, e. Per ulteriori informazioni sugli operatori `=` di `<>`Visual Basic e, vedere [operatori di confronto](../../../../../visual-basic/language-reference/operators/comparison-operators.md). Per ulteriori informazioni sugli C# operatori `==` di confronto `!=`e, vedere [operatori di uguaglianza](../../../../../csharp/language-reference/operators/equality-operators.md).
  
- Operatore is: Quando `IS` si utilizza il mapping di ereditarietà, l'operatore dispone di una conversione supportata. È possibile usarlo invece di testare direttamente la colonna del discriminatore per determinare se un oggetto è di un tipo di entità specifico e viene convertito in un controllo nella colonna del discriminatore. Per ulteriori informazioni sugli operatori Visual Basic e C# is, vedere [is operator](../../../../../visual-basic/language-reference/operators/is-operator.md) e [is](../../../../../csharp/language-reference/operators/type-testing-and-cast.md#is-operator).  
  
## <a name="see-also"></a>Vedere anche

- [Mapping del tipo SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
- [Tipi di dati e funzioni](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
