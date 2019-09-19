---
title: Gestore del token Web JSON
ms.date: 03/30/2017
ms.assetid: 9968f12e-e05d-4e6a-9b65-6896c0e31ab1
ms.openlocfilehash: 3dc76f3de714fd91d397cc240d02a1a8605fe18b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71045328"
---
# <a name="json-web-token-handler"></a>Gestore del token Web JSON
Con l'estensione del gestore dei token Web JSON per Windows Identity Foundation vengono creati e convalidati i token Web JSON (JWT) nelle applicazioni. Il gestore dei token JWT può essere configurato in modo da essere eseguito nella pipeline di WIF come altri gestori di token di sicurezza incorporati, ma può anche essere utilizzato indipendentemente per eseguire la convalida dei token nelle applicazioni leggere. Questo gestore è particolarmente utile quando si utilizza uno schema di token portante OAuth 2.0, ad esempio l'autenticazione di Active Directory di Microsoft Azure.  
  
 Il gestore dei token JWT è disponibile come pacchetto NuGet. Per altre informazioni, vedere [Downloading the JSON Web Token Handler Package](downloading-the-json-web-token-handler-package.md) (Download del pacchetto del gestore del token Web JSON)  
  
## <a name="scenarios"></a>Scenari  
 Con il gestore dei token JWT vengono abilitati gli scenari principali seguenti:  
  
- **Convalidare un token JWT in un'applicazione server**: In questo scenario, una società denominata Litware dispone di un'applicazione server che utilizza WIF per gestire le richieste di accesso Web. Litware desidera abilitare le proprie applicazioni per l'utilizzo di token JWT per l'autenticazione. L'applicazione viene aggiornata con il gestore dei token JWT, quindi la configurazione dell'applicazione viene aggiornata per aggiungere il gestore dei token JWT nella pipeline di WIF. Una volta effettuati gli aggiornamenti e una nuova richiesta entra nella pipeline di WIF, il token JWT viene convalidato utilizzando il nuovo gestore e viene effettuata l'autenticazione con esito positivo.  
  
- **Convalidare un token JWT in un servizio Web REST**: In questo scenario, una società denominata Litware ha un servizio Web REST protetto da Windows Azure Active Directory. Le richieste al servizio Web devono essere autenticate da Active Directory di Microsoft Azure, tramite cui viene emesso un token JWT al completamento dell'autenticazione. Litware dispone di un'applicazione client che necessità dell'accesso al servizio Web. Tramite il client viene effettuata una richiesta al servizio Web e viene presentato il relativo token JWT da Active Directory di Microsoft Azure, che viene quindi convalidato dal servizio Web utilizzando il gestore dei token JWT. Al termine della convalida del token da parte del gestore dei token JWT, la risorsa desiderata viene restituita al client dal servizio Web.  
  
## <a name="features"></a>Funzionalità  
 Il gestore dei token JWT offre le funzionalità seguenti:  
  
- **Convalidare un token JWT**: I token JWT possono essere convalidati facilmente dalla logica di convalida del gestore del token, come parte della pipeline WIF dell'applicazione o chiamati indipendentemente da WIF  
  
- **Creare un token JWT**: Il gestore dei token JWT può essere usato per creare token JWT per l'autorizzazione nei servizi downstream
