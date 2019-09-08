---
title: 'Procedura: Racchiudere tra parentesi quadre gli invii di dati usando transazioni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 6a4c5ba7c4938b48fe489e43ff4a3ff806bd8916
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793812"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>Procedura: Racchiudere tra parentesi quadre gli invii di dati usando transazioni
È possibile usare <xref:System.Transactions.TransactionScope> per raggruppare gli invii al database. Per ulteriori informazioni, vedere [supporto delle transazioni](transaction-support.md).  
  
## <a name="example"></a>Esempio  
 Nel codice seguente l'invio al database viene incluso in <xref:System.Transactions.TransactionScope>.  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Download di database di esempio](downloading-sample-databases.md)
- [Creazione e invio di modifiche dei dati](making-and-submitting-data-changes.md)
- [Supporto delle transazioni](transaction-support.md)
