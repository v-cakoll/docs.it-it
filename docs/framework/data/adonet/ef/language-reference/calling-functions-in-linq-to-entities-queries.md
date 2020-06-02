---
title: Chiamata di funzioni in query di LINQ to Entities
description: Usare questi articoli per vedere come le classi EntityFunctions e SqlFunctions forniscono l'accesso alle funzioni canoniche e di database come parte del Entity Framework.
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: faa6406713592f10e5e7371cd73f29bec4b03b7b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286857"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a>Chiamata di funzioni in query di LINQ to Entities
Negli argomenti di questa sezione viene illustrato come chiamare le funzioni nelle LINQ to Entities.  
  
 Le classi <xref:System.Data.Objects.EntityFunctions> e <xref:System.Data.Objects.SqlClient.SqlFunctions> forniscono l'accesso alle funzioni canoniche e di database come parte di Entity Framework. Per altre informazioni, vedere [procedura: chiamare funzioni canoniche](how-to-call-canonical-functions.md) e [procedura: chiamare funzioni di database](how-to-call-database-functions.md).  
  
 Il processo per la chiamata di una funzione personalizzata richiede tre passaggi di base:  
  
1. Definire una funzione nel modello concettuale o dichiarare una funzione nel modello di archiviazione.  
  
2. Aggiungere un metodo all'applicazione ed eseguirne il mapping alla funzione nel modello con un oggetto <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.  
  
3. Chiamare la funzione in una query LINQ to Entities.  
  
 Per altre informazioni, vedere gli argomenti in questa sezione.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: chiamare funzioni canoniche](how-to-call-canonical-functions.md)  
  
 [Procedura: chiamare funzioni di database](how-to-call-database-functions.md)  
  
 [Procedura: chiamare funzioni di database personalizzate](how-to-call-custom-database-functions.md)  
  
 [Procedura: Chiamare funzioni definite dal modello in query](how-to-call-model-defined-functions-in-queries.md)  
  
 [Procedura: Chiamare funzioni definite dal modello come metodi di oggetto](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a>Vedere anche

- [Query in LINQ to Entities](queries-in-linq-to-entities.md)
- [Funzioni canoniche](canonical-functions.md)
- [Panoramica sui file con estensione edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Procedura: definire funzioni personalizzate nel modello concettuale](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))
