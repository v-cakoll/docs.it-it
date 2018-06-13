---
title: Chiamata di funzioni in query di LINQ to Entities
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: 690f1a2cdcd8726d40a6627c1ceb05c9ae7e7fdd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760141"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a>Chiamata di funzioni in query di LINQ to Entities
Negli argomenti di questa sezione viene illustrato come chiamare le funzioni nelle LINQ to Entities.  
  
 Le classi <xref:System.Data.Objects.EntityFunctions> e <xref:System.Data.Objects.SqlClient.SqlFunctions> forniscono l'accesso alle funzioni canoniche e di database come parte di Entity Framework. Per ulteriori informazioni, vedere [procedura: chiamare funzioni canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) e [procedura: chiamare funzioni di Database](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).  
  
 Il processo per la chiamata di una funzione personalizzata richiede tre passaggi di base:  
  
1.  Definire una funzione nel modello concettuale o dichiarare una funzione nel modello di archiviazione.  
  
2.  Aggiungere un metodo all'applicazione ed eseguirne il mapping alla funzione nel modello con un oggetto <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.  
  
3.  Chiamare la funzione in una query LINQ to Entities.  
  
 Per altre informazioni, vedere gli argomenti in questa sezione.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Chiamare funzioni canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md)  
  
 [Procedura: Chiamare funzioni di database](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)  
  
 [Procedura: Chiamare funzioni di database personalizzate](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-custom-database-functions.md)  
  
 [Procedura: Chiamare funzioni definite dal modello in query](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md)  
  
 [Procedura: Chiamare funzioni definite dal modello come metodi di oggetto](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Query in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [Funzioni canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)  
 [Cenni preliminari sui file con estensione edmx](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [Procedura: definire le funzioni personalizzate nel modello concettuale](http://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f)
