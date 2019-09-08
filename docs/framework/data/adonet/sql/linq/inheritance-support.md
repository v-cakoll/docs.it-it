---
title: Supporto dell'ereditarietà
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: 034aa6e75ca304d98aa4d3e1f3023c1a6940b73c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781562"
---
# <a name="inheritance-support"></a>Supporto dell'ereditarietà
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]supporta il *mapping di una singola tabella*. In altre parole, una gerarchia di ereditarietà completa viene archiviata in un'unica tabella di database, che contiene l'unione bidimensionale di tutte le possibili colonne di dati per l'intera gerarchia. Un'unione è il risultato della combinazione di due tabelle in una sola contenente le righe presenti in ciascuna delle tabelle originali. In ogni riga è indicato un valore null in corrispondenza delle colonne non applicabili al tipo dell'istanza rappresentata dalla riga stessa.  
  
 La strategia di mapping di singole tabelle è la più semplice rappresentazione di ereditarietà e offre caratteristiche di prestazioni ottimali per numerose categorie di query.  
  
 Per implementare questo tipo di mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], è necessario specificare gli attributi e le relative proprietà sulla classe radice della gerarchia di ereditarietà. Per altre informazioni, vedere [Procedura: Mappare le gerarchie](how-to-map-inheritance-hierarchies.md)di ereditarietà.  
  
 Gli sviluppatori che usano Visual Studio possono anche usare la Object Relational Designer per eseguire il mapping delle gerarchie di ereditarietà.  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni di base](background-information.md)
