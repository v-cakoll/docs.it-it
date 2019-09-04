---
title: Funzioni (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
ms.openlocfilehash: ec94a0f16fb3b836297f6675cc938a711816555b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250913"
---
# <a name="functions-entity-sql"></a>Funzioni (Entity SQL)
Entity SQL supporta funzioni definite dall'utente, funzioni canoniche e funzioni specifiche del provider. Le funzioni definite dall'utente vengono specificate nel modello concettuale o inline nella query. Per ulteriori informazioni, vedere [funzioni definite dall'utente](user-defined-functions-entity-sql.md).  
  
 Le funzioni canoniche sono predefinite in Entity Framework e devono essere supportate dai provider di dati. Se un utente chiama una funzione che non è supportata da un provider, i comandi Entity SQL hanno esito negativo. Le funzioni canoniche vengono pertanto generalmente preferite alle funzioni specifiche dell'archivio, che sono incluse in uno spazio dei nomi specifico del provider. Per altre informazioni, vedere [funzioni canoniche](canonical-functions.md).  
  
 Il provider gestito del client Microsoft SQL fornisce un set di funzioni specifiche del provider. Per ulteriori informazioni, vedere [SqlClient per le funzioni Entity Framework](../sqlclient-for-ef-functions.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Funzioni definite dall'utente](user-defined-functions-entity-sql.md)  
  
 [Risoluzione dell'overload della funzione](function-overload-resolution-entity-sql.md)  
  
 [Funzioni di aggregazione](../aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di Entity SQL](entity-sql-overview.md)
