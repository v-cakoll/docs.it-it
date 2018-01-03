---
title: "Supporto dell'ereditarietà"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c898d8448b39fc5da63e5eda2046d0747837509b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="inheritance-support"></a>Supporto dell'ereditarietà
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]supporta *mapping di singole tabelle*. In altre parole, una gerarchia di ereditarietà completa viene archiviata in un'unica tabella di database, che contiene l'unione bidimensionale di tutte le possibili colonne di dati per l'intera gerarchia. Un'unione è il risultato della combinazione di due tabelle in una sola contenente le righe presenti in ciascuna delle tabelle originali. In ogni riga è indicato un valore null in corrispondenza delle colonne non applicabili al tipo dell'istanza rappresentata dalla riga stessa.  
  
 La strategia di mapping di singole tabelle è la più semplice rappresentazione di ereditarietà e offre caratteristiche di prestazioni ottimali per numerose categorie di query.  
  
 Per implementare questo tipo di mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], è necessario specificare gli attributi e le relative proprietà sulla classe radice della gerarchia di ereditarietà. Per ulteriori informazioni, vedere [come: mappa di gerarchie di ereditarietà](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).  
  
 Gli sviluppatori che usano [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] possono inoltre adoperare [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per eseguire il mapping delle gerarchie di ereditarietà.  
  
## <a name="see-also"></a>Vedere anche  
 [Informazioni di base](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
