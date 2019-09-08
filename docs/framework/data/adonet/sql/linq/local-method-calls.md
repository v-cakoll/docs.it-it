---
title: Chiamate a metodo locali
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34b5012-aee9-4994-9364-1d99d12b7463
ms.openlocfilehash: ec288d5ac2f6466860362be82c619c89204e8f31
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781425"
---
# <a name="local-method-calls"></a>Chiamate a metodo locali
Una chiamata al metodo locale viene eseguita all'interno del modello a oggetti. Una chiamata al metodo remota viene convertita da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in SQL e trasmessa al motore di database per l'esecuzione. Le chiamate al metodo locale sono [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] necessarie quando non è in grado di tradurre la chiamata in SQL. In caso contrario, verrà generata un'eccezione <xref:System.InvalidOperationException>.  
  
## <a name="example-1"></a>Esempio 1  
 Nell'esempio seguente viene eseguito il mapping di una classe `Order` alla tabella Orders nel database di esempio Northwind. Alla classe è stato aggiunto un metodo di istanza locale.  
  
 Nella Query 1 il costruttore per la classe `Order` viene eseguito localmente. Nella query 2, se [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tentasse di `LocalInstanceMethod()`convertire in SQL, il tentativo avrà esito <xref:System.InvalidOperationException> negativo e verrà generata un'eccezione. Tuttavia, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] poiché fornisce il supporto per le chiamate al metodo locali, query2 non genererà un'eccezione.  
  
 [!code-csharp[DlinqLocalMethodCall#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/Program.cs#1)]
 [!code-vb[DlinqLocalMethodCall#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/Module1.vb#1)]  
  
 [!code-csharp[DlinqLocalMethodCall#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/northwind.cs#2)]
 [!code-vb[DlinqLocalMethodCall#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/northwind.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni di base](background-information.md)
