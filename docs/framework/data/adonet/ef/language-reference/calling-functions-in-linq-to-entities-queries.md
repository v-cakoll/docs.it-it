---
title: Chiamata di funzioni in query di LINQ to Entities
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6e50147d356ad9e389a87868205bb9b8b6b3e7b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="calling-functions-in-linq-to-entities-queries"></a>Chiamata di funzioni in query di LINQ to Entities
Negli argomenti di questa sezione viene illustrato come chiamare le funzioni nelle LINQ to Entities.  
  
 Le classi <xref:System.Data.Objects.EntityFunctions> e <xref:System.Data.Objects.SqlClient.SqlFunctions> forniscono l'accesso alle funzioni canoniche e di database come parte di Entity Framework. Per ulteriori informazioni, vedere [procedura: chiamare funzioni canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) e [procedura: chiamare funzioni di Database](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).  
  
 Il processo per la chiamata di una funzione personalizzata richiede tre passaggi di base:  
  
1.  Definire una funzione nel modello concettuale o dichiarare una funzione nel modello di archiviazione.  
  
2.  Aggiungere un metodo all'applicazione ed eseguirne il mapping alla funzione nel modello con un oggetto <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.  
  
3.  Chiamare la funzione in una query LINQ to Entities.  
  
 Per altre informazioni, vedere gli argomenti in questa sezione.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: chiamare funzioni canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md)  
  
 [Procedura: chiamare funzioni di Database](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)  
  
 [Procedura: chiamare funzioni personalizzate per il Database](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-custom-database-functions.md)  
  
 [Procedura: chiamare funzioni definite dal modello nelle query](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md)  
  
 [Procedura: chiamare funzioni definite dal modello come metodi di oggetti](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Query in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [Funzioni canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)  
 [Cenni preliminari sui file con estensione edmx](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [Procedura: definire le funzioni personalizzate nel modello concettuale](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f)
