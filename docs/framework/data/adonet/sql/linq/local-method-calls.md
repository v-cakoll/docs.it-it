---
title: Chiamate a metodo locali
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: c34b5012-aee9-4994-9364-1d99d12b7463
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d652072d5f2e0e0cfc74d627b573389864bca9dc
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="local-method-calls"></a>Chiamate a metodo locali
Una chiamata al metodo locale viene eseguita all'interno del modello a oggetti. Una chiamata al metodo remota viene convertita da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in SQL e trasmessa al motore di database per l'esecuzione. Chiamate al metodo locali sono necessari quando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non è possibile convertire la chiamata in SQL. In caso contrario, un <xref:System.InvalidOperationException> viene generata un'eccezione.  
  
## <a name="example-1"></a>Esempio 1  
 Nell'esempio seguente viene eseguito il mapping di una classe `Order` alla tabella Orders nel database di esempio Northwind. Alla classe è stato aggiunto un metodo di istanza locale.  
  
 Nella Query 1 il costruttore per la classe `Order` viene eseguito localmente. Nella Query 2 se [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tentasse di convertire `LocalInstanceMethod()`in SQL, il tentativo avrà esito negativo e un <xref:System.InvalidOperationException> verrebbe generata l'eccezione. Tuttavia, poiché [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fornisce il supporto per le chiamate al metodo locali, nella query 2 non genererà un'eccezione.  
  
 [!code-csharp[DlinqLocalMethodCall#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/Program.cs#1)]
 [!code-vb[DlinqLocalMethodCall#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/Module1.vb#1)]  
  
 [!code-csharp[DlinqLocalMethodCall#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/northwind.cs#2)]
 [!code-vb[DlinqLocalMethodCall#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/northwind.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 [Informazioni di base](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
