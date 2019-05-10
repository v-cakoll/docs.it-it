---
title: Convalida del registro dei nomi delle autorità emittenti
ms.date: 03/30/2017
ms.assetid: c4644dd1-dead-48ff-abeb-7bffae69a6ac
ms.openlocfilehash: fc10181a142fd8ca4ebd8250869d49a046623564
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2019
ms.locfileid: "64910775"
---
# <a name="validating-issuer-name-registry"></a>Convalida del registro dei nomi delle autorità emittenti
Validating Issuer Name Registry (VINR) per Windows Identity Foundation consente alle applicazioni multi-tenant di verificare che un token in ingresso sia stato emesso da un tenant e un provider di identità attendibili. Questa funzionalità è particolarmente utile per le applicazioni multi-tenant in cui viene utilizzato Active Directory di Microsoft Azure perché tutti i token emessi da quest'ultimo sono firmati utilizzando lo stesso certificato. Per poter distinguere tra le richieste provenienti da più tenant che utilizzano lo stesso certificato, e di conseguenza dispongono della stessa identificazione digitale, nell'applicazione deve persistere il nome dell'autorità di certificazione per ogni tenant per eseguire la logica di convalida. VINR fornisce questa funzionalità. Inoltre consente di aggiungere la logica di convalida personalizzata o di archiviare i dati del Registro di sistema dell'autorità di certificazione in percorsi diversi da un file di configurazione. L'estensione può essere aggiunta alla pipeline di WIF dell'applicazione o può essere utilizzata indipendentemente.  
  
 VINR è disponibile come pacchetto NuGet. Per altre informazioni, vedere [Download del pacchetto di convalida del registro dei nomi delle autorità emittenti](../../../docs/framework/security/downloading-the-validating-issuer-name-registry-package.md).  
  
## <a name="scenarios"></a>Scenari  
 Con VINR viene abilitato lo scenario principale seguente:  
  
- **Convalidare un Token in un'applicazione multi-Tenant**: In questo scenario una società denominata Litware ha sviluppato un'applicazione multi-tenant che usa un provider di identità, ad esempio Microsoft Azure AD. Questa applicazione è destinata ai due clienti: Contoso e Fabrikam. Quando un utente di Fabrikam effettua l'autenticazione per l'applicazione di Litware, il token risultante di Active Directory di Microsoft Azure viene firmato utilizzando il relativo certificato standard e la richiesta viene emessa da Fabrikam. Tramite l'applicazione deve essere verificata la validità del nome dell'autorità di certificazione e del token e devono essere differenziate le richieste di Contoso firmate con lo stesso certificato da Active Directory di Microsoft Azure. Con VINR è più facile per l'applicazione di Litware differenziare e convalidare le richieste da più tenant, ad esempio Contoso e Fabrikam.  
  
## <a name="features"></a>Funzionalità  
 VINR offre le funzionalità seguenti:  
  
- **Nome dell'autorità emittente e la convalida dei Token per le applicazioni multi-Tenant**: Convalida il token in ingresso verificando il nome dell'autorità di certificazione (tenant) e indica se il token è stato firmato con un certificato valido dal provider di identità.  
  
- **Estendibilità per la logica di convalida personalizzata e archivi dati**: Fornisce l'estendibilità per inserire la propria logica di convalida e specificare un archivio dati diverso dal file di configurazione predefinito.
