---
title: Personalizzazione di operazioni utilizzando esclusivamente stored procedure
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: a242ecdc774d67721aee640e75847317c1b815d6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247540"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a>Personalizzazione di operazioni utilizzando esclusivamente stored procedure
L'accesso ai dati usando solo stored procedure costituisce uno scenario comune.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>DESCRIZIONE  
 È possibile modificare l'esempio fornito in [personalizzazione di operazioni utilizzando stored procedure](customizing-operations-by-using-stored-procedures.md) sostituendo anche la prima query, che causa l'esecuzione dinamica di SQL, con una chiamata al metodo che esegue il wrapping di un stored procedure.  
  
 Si supponga che il metodo sia `CustomersByCity`, come nell'esempio seguente.  
  
### <a name="code"></a>Codice  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 Il codice seguente viene eseguito senza SQL dinamico.  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Vedere anche

- [Responsabilità dello sviluppatore nell'override del comportamento predefinito](responsibilities-of-the-developer-in-overriding-default-behavior.md)
