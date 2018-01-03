---
title: 'Procedura: rilevare e risolvere gli invii in conflitto'
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
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 28dba94262002f863a750a83493ba98b3714fabd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a>Procedura: rilevare e risolvere gli invii in conflitto
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sono disponibili molte risorse per rilevare e risolvere i conflitti causati dalle modifiche apportate al database da più utenti. Per ulteriori informazioni, vedere [procedura: gestire i conflitti di modifiche](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente un `try` / `catch` blocco che memorizza nella cache un <xref:System.Data.Linq.ChangeConflictException> eccezione. Le informazioni sull'entità e sul membro per ogni conflitto sono visualizzate nella finestra della console.  
  
> [!NOTE]
>  Per supportare il recupero delle informazioni, è necessario includere la direttiva `using System.Reflection` (`Imports System.Reflection` in Visual Basic). Per altre informazioni, vedere <xref:System.Reflection>.  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione e invio di modifiche dei dati](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [Procedura: gestire i conflitti di modifiche](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
