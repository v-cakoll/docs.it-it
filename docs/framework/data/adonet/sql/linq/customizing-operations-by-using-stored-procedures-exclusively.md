---
title: Personalizzazione di operazioni utilizzando esclusivamente stored procedure
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 61230ffc5cd055ee64de9d519cdfb4d76c856ca3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038051"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a>Personalizzazione di operazioni utilizzando esclusivamente stored procedure
L'accesso ai dati usando solo stored procedure costituisce uno scenario comune.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 È possibile modificare l'esempio fornito [personalizzazione di operazioni usando Stored procedure](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) sostituendo anche la prima query (causando l'esecuzione di SQL dinamico) con una chiamata al metodo che esegue il wrapping di una stored procedure.  
  
 Si supponga che il metodo sia `CustomersByCity`, come nell'esempio seguente.  
  
### <a name="code"></a>Codice  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 Il codice seguente viene eseguito senza SQL dinamico.  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Vedere anche

- [Responsabilità dello sviluppatore nell'override del comportamento predefinito](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
