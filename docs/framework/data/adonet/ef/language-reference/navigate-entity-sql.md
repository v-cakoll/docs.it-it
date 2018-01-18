---
title: NAVIGATE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e6d61e3fb03a1e0ee0cdf344bd61167ad3046a13
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="navigate-entity-sql"></a>NAVIGATE (Entity SQL)
Consente di eseguire la navigazione nella relazione stabilita tra le entità.  
  
## <a name="syntax"></a>Sintassi  
  
```  
navigate(instance-expresssion, [relationship-type], [to-end [, from-end] ])  
```  
  
## <a name="arguments"></a>Argomenti  
 `instance-expresssion`  
 Istanza di un'entità.  
  
 `relationship-type`  
 Nome del tipo della relazione, dal file CSDL (Conceptual Schema Definition Language). Il `relationship-type` è qualificato come \<dello spazio dei nomi >.\< Nome tipo relazione >.  
  
 `to`  
 Entità finale della relazione.  
  
 `from`  
 Inizio della relazione.  
  
## <a name="return-value"></a>Valore restituito  
 Se la cardinalità dell'entità finale è 1, il valore restituito è `Ref<T>`. Se la cardinalità dell'entità finale è n, il valore restituito è `Collection<Ref<T>>`.  
  
## <a name="remarks"></a>Note  
 Le relazioni sono costrutti di primaria importanza in [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] (EDM). È possibile stabilire relazioni tra due o più tipi di entità e navigare nella relazione da un'entità finale all'altra. I parametri`from` e `to` sono condizionatamente facoltativi in assenza di ambiguità nella risoluzione dei nomi all'interno della relazione.  
  
 NAVIGATE è valido nello spazio O e C.  
  
 Il formato generale di un costrutto di navigazione è il seguente:  
  
 navigate(`instance-expresssion`, `relationship-type`, [ `to-end` [, `from-end` ] ] )  
  
 Ad esempio:  
  
```  
Select o.Id, navigate(o, OrderCustomer, Customer, Order)  
From LOB.Orders as o  
```  
  
 Dove OrderCustomer è l'oggetto `relationship`, mentre Customer e Order rappresentano l'oggetto `to-end` (Customer) e l'oggetto `from-end` (Order) della relazione. Se OrderCustomer è una relazione n:1, il tipo di risultato dell'espressione di navigazione è Ref\<Customer >.  
  
 La forma più semplice di questa espressione è la seguente:  
  
```  
Select o.Id, navigate(o, OrderCustomer)  
From LOB.Orders as o  
```  
  
 Analogamente, in una query nel formato seguente, l'espressione di navigazione produrrebbe come risultato Collection < Ref\<ordine >>.  
  
```  
Select c.Id, navigate(c, OrderCustomer, Order, Customer)  
From LOB.Customers as c  
```  
  
 L'espressione dell'istanza deve essere un tipo di entità/riferimento.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore NAVIGATE per eseguire la navigazione nella relazione stabilita tra i tipi di entità Address e SalesOrderHeader. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1.  Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#NAVIGATE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#navigate)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Procedura: esplorare relazioni con operatore Navigate](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)
