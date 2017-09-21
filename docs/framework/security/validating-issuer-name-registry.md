---
title: "Convalida del registro dei nomi delle autorità emittenti"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4644dd1-dead-48ff-abeb-7bffae69a6ac
caps.latest.revision: 4
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c6c1b72048f1f7cb421e5a19d34c2c2dea5463ce
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="validating-issuer-name-registry"></a>Convalida del registro dei nomi delle autorità emittenti
Validating Issuer Name Registry (VINR) per Windows Identity Foundation consente alle applicazioni multi-tenant di verificare che un token in ingresso sia stato emesso da un tenant e un provider di identità attendibili. Questa funzionalità è particolarmente utile per le applicazioni multi-tenant in cui viene utilizzato Active Directory di Microsoft Azure perché tutti i token emessi da quest'ultimo sono firmati utilizzando lo stesso certificato. Per poter distinguere tra le richieste provenienti da più tenant che utilizzano lo stesso certificato, e di conseguenza dispongono della stessa identificazione digitale, nell'applicazione deve persistere il nome dell'autorità di certificazione per ogni tenant per eseguire la logica di convalida. VINR fornisce questa funzionalità. Inoltre consente di aggiungere la logica di convalida personalizzata o di archiviare i dati del Registro di sistema dell'autorità di certificazione in percorsi diversi da un file di configurazione. L'estensione può essere aggiunta alla pipeline di WIF dell'applicazione o può essere utilizzata indipendentemente.  
  
 VINR è disponibile come pacchetto NuGet. Per altre informazioni, vedere [Download del pacchetto di convalida del registro dei nomi delle autorità emittenti](../../../docs/framework/security/downloading-the-validating-issuer-name-registry-package.md).  
  
## <a name="scenarios"></a>Scenari  
 Con VINR viene abilitato lo scenario principale seguente:  
  
-   **Convalida di un token in un'applicazione multi-tenant**: in questo scenario una società di nome Litware ha sviluppato un'applicazione multi-tenant che usa un provider di identità come Microsoft Azure AD. Questa applicazione viene utilizzata per due clienti: Contoso e Fabrikam. Quando un utente di Fabrikam effettua l'autenticazione per l'applicazione di Litware, il token risultante di Active Directory di Microsoft Azure viene firmato utilizzando il relativo certificato standard e la richiesta viene emessa da Fabrikam. Tramite l'applicazione deve essere verificata la validità del nome dell'autorità di certificazione e del token e devono essere differenziate le richieste di Contoso firmate con lo stesso certificato da Active Directory di Microsoft Azure. Con VINR è più facile per l'applicazione di Litware differenziare e convalidare le richieste da più tenant, ad esempio Contoso e Fabrikam.  
  
## <a name="features"></a>Funzionalità  
 VINR offre le funzionalità seguenti:  
  
-   **Convalida del nome dell'autorità emittente e del token per le applicazioni multi-tenant**: viene eseguita la convalida del token in ingresso verificando il nome dell'autorità emittente (tenant) e il fatto che il token sia stato firmato usando un certificato valido dal provider di identità.  
  
-   **Estendibilità per la logica di convalida personalizzata e gli archivi dati**: fornisce l'estendibilità per inserire la logica di convalida personalizzata e per specificare un archivio dati diverso dal file di configurazione predefinito.

