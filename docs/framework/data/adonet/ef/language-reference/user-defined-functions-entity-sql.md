---
title: Funzioni definite dall'utente (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: 9ddafb18a10ff2313fd27eab453907054a35218a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248762"
---
# <a name="user-defined-functions-entity-sql"></a>Funzioni definite dall'utente (Entity SQL)
Nelle query Entity SQL sono supportate le chiamate a funzioni definite dall'utente. È possibile definire queste funzioni inline con la query (vedere [procedura: Chiamare una funzione](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))definita dall'utente) o come parte del modello concettuale (vedere [procedura: Definire funzioni personalizzate nel modello](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))concettuale. Le funzioni del modello concettuale sono definite come Entity SQL comando nell'elemento [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) di un elemento [Function](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) nel modello concettuale.  
  
 Entity SQL consente di definire delle funzioni nel comando di query stesso. L'operatore [Function](function-entity-sql.md) definisce le funzioni inline. È possibile definire più funzioni in un singolo comando e queste funzioni possono avere lo stesso nome purché le rispettive firme siano univoche. Per altre informazioni, vedere [Function Overload Resolution](function-overload-resolution-entity-sql.md).  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni](functions-entity-sql.md)
