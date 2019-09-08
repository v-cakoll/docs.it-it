---
title: Transazioni distribuite Oracle
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: 6f910f1dbbe448352c0edd5d1b80df659ac453d4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795151"
---
# <a name="oracle-distributed-transactions"></a>Transazioni distribuite Oracle
Se rileva una transazione attiva, l'oggetto <xref:System.Data.OracleClient.OracleConnection> esegue l'inserimento automatico in una transazione distribuita esistente. L'inserimento automatico in una transazione viene eseguito anche quando la connessione viene aperta o recuperata dal pool di connessioni. È possibile disabilitare l'inserimento automatico in transazioni esistenti specificando  
  
```  
Enlist=false  
```  
  
 come parametro della stringa di connessione per un tipo <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="see-also"></a>Vedere anche

- [Oracle e ADO.NET](oracle-and-adonet.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
