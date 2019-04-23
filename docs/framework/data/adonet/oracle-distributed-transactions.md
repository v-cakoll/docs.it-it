---
title: Transazioni distribuite Oracle
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: 4af1c98818f1929850c5ae78892c64993a93d4d2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116217"
---
# <a name="oracle-distributed-transactions"></a>Transazioni distribuite Oracle
Se rileva una transazione attiva, l'oggetto <xref:System.Data.OracleClient.OracleConnection> esegue l'inserimento automatico in una transazione distribuita esistente. L'inserimento automatico in una transazione viene eseguito anche quando la connessione viene aperta o recuperata dal pool di connessioni. È possibile disabilitare l'inserimento automatico in transazioni esistenti specificando  
  
```  
Enlist=false  
```  
  
 come parametro della stringa di connessione per un tipo <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="see-also"></a>Vedere anche

- [Oracle e ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
