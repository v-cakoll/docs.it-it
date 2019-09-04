---
title: Chiamata di funzioni in query di LINQ to Entities
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: 267bb393d9e75c66eb18139e8897da34bd86e159
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251257"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a>Chiamata di funzioni in query di LINQ to Entities
Negli argomenti di questa sezione viene illustrato come chiamare le funzioni nelle LINQ to Entities.  
  
 Le classi <xref:System.Data.Objects.EntityFunctions> e <xref:System.Data.Objects.SqlClient.SqlFunctions> forniscono l'accesso alle funzioni canoniche e di database come parte di Entity Framework. Per altre informazioni, vedere [Procedura: Chiamare funzioni](how-to-call-canonical-functions.md) canoniche [e procedura: Chiamare le funzioni](how-to-call-database-functions.md)di database.  
  
 Il processo per la chiamata di una funzione personalizzata richiede tre passaggi di base:  
  
1. Definire una funzione nel modello concettuale o dichiarare una funzione nel modello di archiviazione.  
  
2. Aggiungere un metodo all'applicazione ed eseguirne il mapping alla funzione nel modello con un oggetto <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.  
  
3. Chiamare la funzione in una query LINQ to Entities.  
  
 Per altre informazioni, vedere gli argomenti in questa sezione.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Chiama funzioni canoniche](how-to-call-canonical-functions.md)  
  
 [Procedura: Funzioni di database di chiamata](how-to-call-database-functions.md)  
  
 [Procedura: Chiamare funzioni di database personalizzate](how-to-call-custom-database-functions.md)  
  
 [Procedura: Chiamare funzioni definite dal modello nelle query](how-to-call-model-defined-functions-in-queries.md)  
  
 [Procedura: Chiamare funzioni definite dal modello come metodi di oggetto](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a>Vedere anche

- [Query in LINQ to Entities](queries-in-linq-to-entities.md)
- [Funzioni canoniche](canonical-functions.md)
- [Panoramica del file con estensione edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Procedura: Definire funzioni personalizzate nel modello concettuale](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))
