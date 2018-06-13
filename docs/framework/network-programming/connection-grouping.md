---
title: Raggruppamento delle connessioni
ms.date: 03/30/2017
helpviewer_keywords:
- Internet, connections
- connections [.NET Framework], grouping
- WebRequest class, connection grouping
- network resources, connections
- connection pooling
ms.assetid: 2ec502e8-4ba0-4c22-9410-f28eaf4eee63
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bbf34f1e653e95ea30a3e9945fc74c99cfdc3a45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395047"
---
# <a name="connection-grouping"></a>Raggruppamento delle connessioni
Con il raggruppamento delle connessioni le richieste specifiche eseguite all'interno di una singola applicazione vengono associate a un pool di connessioni definito. Questa operazione può essere necessaria in caso di connessione, tramite un'applicazione di livello intermedio, a un server back-end per conto di un utente mediante un protocollo di autenticazione che supporti la delega, ad esempio Kerberos, oppure in caso di uso di un'applicazione di livello intermedio in cui vengono fornite le credenziali dell'utente, come nell'esempio seguente. Si supponga ad esempio che un utente, Gianni, visiti un sito Web interno che visualizza informazioni sul suo stipendio. Dopo l'autenticazione, le credenziali di Gianni vengono usate dal server dell'applicazione di livello intermedio per connettersi al server back-end e recuperare le informazioni sullo stipendio. Il sito viene quindi visitato da Elena, che richiede informazioni sul proprio stipendio. Poiché tramite l'applicazione di livello intermedio è già stata stabilita una connessione con le credenziali di Gianni, la risposta fornita dal server back-end contiene le informazioni relative a Gianni. Se tuttavia ogni richiesta inviata al server back-end viene assegnata a un gruppo di connessioni basato sul nome utente, ogni utente apparterrà a un pool di connessioni distinto e non potrà condividere accidentalmente le informazioni di autenticazione con altri utenti.  
  
 Per assegnare una richiesta a un gruppo di connessioni specifico, è necessario assegnare un nome alla proprietà <xref:System.Net.WebRequest.ConnectionGroupName%2A> della classe <xref:System.Net.WebRequest> prima di effettuare la richiesta.  
  
## <a name="see-also"></a>Vedere anche  
 [Gestione di connessioni](../../../docs/framework/network-programming/managing-connections.md)  
 [Procedura: Assegnare informazioni utente a connessioni di gruppo](../../../docs/framework/network-programming/how-to-assign-user-information-to-group-connections.md)
