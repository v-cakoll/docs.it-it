---
title: 'Procedura: racchiudere tra parentesi quadre gli invii di dati utilizzando transazioni'
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
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a5d7f1e0b0419874f694a0b3953f6b037a777016
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>Procedura: racchiudere tra parentesi quadre gli invii di dati utilizzando transazioni
È possibile usare <xref:System.Transactions.TransactionScope> per raggruppare gli invii al database. Per ulteriori informazioni, vedere [il supporto delle transazioni](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).  
  
## <a name="example"></a>Esempio  
 Nel codice seguente l'invio al database viene incluso in <xref:System.Transactions.TransactionScope>.  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche  
 [Download di database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [Creazione e invio di modifiche dei dati](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [Supporto delle transazioni](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)
