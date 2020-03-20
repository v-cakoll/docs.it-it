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
ms.openlocfilehash: 007366764a7b8e1208e22ef5895e6a9093b090e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048650"
---
# <a name="connection-grouping"></a><span data-ttu-id="07937-102">Raggruppamento delle connessioni</span><span class="sxs-lookup"><span data-stu-id="07937-102">Connection Grouping</span></span>
<span data-ttu-id="07937-103">Con il raggruppamento delle connessioni le richieste specifiche eseguite all'interno di una singola applicazione vengono associate a un pool di connessioni definito.</span><span class="sxs-lookup"><span data-stu-id="07937-103">Connection grouping associates specific requests within a single application to a defined connection pool.</span></span> <span data-ttu-id="07937-104">Questa operazione può essere necessaria in caso di connessione, tramite un'applicazione di livello intermedio, a un server back-end per conto di un utente mediante un protocollo di autenticazione che supporti la delega, ad esempio Kerberos, oppure in caso di uso di un'applicazione di livello intermedio in cui vengono fornite le credenziali dell'utente, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="07937-104">This can be required by a middle-tier application that connects to a back-end server on behalf of a user and uses an authentication protocol that supports delegation, such as Kerberos, or by a middle-tier application that supplies its own credentials, as in the example below.</span></span> <span data-ttu-id="07937-105">Si supponga ad esempio che un utente, Gianni, visiti un sito Web interno che visualizza informazioni sul suo stipendio.</span><span class="sxs-lookup"><span data-stu-id="07937-105">For example, suppose a user, Joe, visits an internal Web site that displays his payroll information.</span></span> <span data-ttu-id="07937-106">Dopo l'autenticazione, le credenziali di Gianni vengono usate dal server dell'applicazione di livello intermedio per connettersi al server back-end e recuperare le informazioni sullo stipendio.</span><span class="sxs-lookup"><span data-stu-id="07937-106">After authenticating Joe, the middle-tier application server uses Joe's credentials to connect to the back-end server to retrieve his payroll information.</span></span> <span data-ttu-id="07937-107">Il sito viene quindi visitato da Elena, che richiede informazioni sul proprio stipendio.</span><span class="sxs-lookup"><span data-stu-id="07937-107">Next, Susan visits the site and requests her payroll information.</span></span> <span data-ttu-id="07937-108">Poiché tramite l'applicazione di livello intermedio è già stata stabilita una connessione con le credenziali di Gianni, la risposta fornita dal server back-end contiene le informazioni relative a Gianni.</span><span class="sxs-lookup"><span data-stu-id="07937-108">Because the middle-tier application has already made a connection using Joe's credentials, the back-end server responds with Joe's information.</span></span> <span data-ttu-id="07937-109">Se tuttavia ogni richiesta inviata al server back-end viene assegnata a un gruppo di connessioni basato sul nome utente, ogni utente apparterrà a un pool di connessioni distinto e non potrà condividere accidentalmente le informazioni di autenticazione con altri utenti.</span><span class="sxs-lookup"><span data-stu-id="07937-109">However, if the application assigns each request sent to the back-end server to a connection group formed from the user name, then each user belongs to a separate connection pool and cannot accidentally share authentication information with another user.</span></span>  
  
 <span data-ttu-id="07937-110">Per assegnare una richiesta a un gruppo di connessioni specifico, è necessario assegnare un nome alla proprietà <xref:System.Net.WebRequest.ConnectionGroupName%2A> della classe <xref:System.Net.WebRequest> prima di effettuare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="07937-110">To assign a request to a specific connection group, you must assign a name to the <xref:System.Net.WebRequest.ConnectionGroupName%2A> property of your <xref:System.Net.WebRequest> before making the request.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07937-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07937-111">See also</span></span>

- [<span data-ttu-id="07937-112">Gestione delle connessioni</span><span class="sxs-lookup"><span data-stu-id="07937-112">Managing Connections</span></span>](managing-connections.md)
- [<span data-ttu-id="07937-113">Procedura: Assegnare informazioni utente a connessioni di gruppo</span><span class="sxs-lookup"><span data-stu-id="07937-113">How to: Assign User Information to Group Connections</span></span>](how-to-assign-user-information-to-group-connections.md)
