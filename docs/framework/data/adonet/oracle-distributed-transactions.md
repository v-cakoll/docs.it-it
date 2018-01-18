---
title: Transazioni distribuite Oracle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c901ccf9132dc766d78efb24428b6469458a70fa
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="oracle-distributed-transactions"></a>Transazioni distribuite Oracle
Se rileva una transazione attiva, l'oggetto <xref:System.Data.OracleClient.OracleConnection> esegue l'inserimento automatico in una transazione distribuita esistente. L'inserimento automatico in una transazione viene eseguito anche quando la connessione viene aperta o recuperata dal pool di connessioni. È possibile disabilitare l'inserimento automatico in transazioni esistenti specificando  
  
```  
Enlist=false  
```  
  
 come parametro della stringa di connessione per un tipo <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="see-also"></a>Vedere anche  
 [Oracle e ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
