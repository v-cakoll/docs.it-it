---
title: Autorizzazione basata su attestazioni con WIF
ms.date: 03/30/2017
ms.assetid: e24000a3-8fd8-4c0e-bdf0-39882cc0f6d8
author: BrucePerlerMS
ms.openlocfilehash: e269a168c5aa594684a41a98338d961447acd536
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59312176"
---
# <a name="claims-based-authorization-using-wif"></a>Autorizzazione basata su attestazioni con WIF
Tramite l'autorizzazione di un'applicazione relying party vengono determinate le risorse di un'identità autenticata a cui è consentito l'accesso e le operazioni eseguibili in queste risorse. Un'autorizzazione non corretta o debole comporta la diffusione di informazioni e l'alterazione dei dati. In questo argomento vengono descritti gli approcci disponibili per implementare l'autorizzazione per i servizi e le applicazioni Web ASP.NET in grado di riconoscere attestazioni mediante WIF (Windows Identity Foundation) e un servizio token di sicurezza (STS), ad esempio il Servizio di controllo di accesso (ACS) di Microsoft Azure.  
  
## <a name="overview"></a>Panoramica  
 Fin dalla prima versione, in .NET Framework viene fornito un meccanismo flessibile per implementare l'autorizzazione. Questo meccanismo è basato su due interfacce semplici, ovvero **IPrincipal** e **IIdentity**. Le implementazioni concrete di **IIdentity** rappresentano un utente autenticato. Ad esempio, l'implementazione di **WindowsIdentity** rappresenta un utente autenticato da Active Directory e quella di **GenericIdentity** rappresenta un utente la cui identità viene verificata tramite un processo di autenticazione personalizzato. Le implementazioni concrete di **IPrincipal** consentono di verificare le autorizzazioni usando ruoli in base all'archivio ruoli. **WindowsPrincipal**, ad esempio, verifica l'appartenenza di **WindowsIdentity** ai gruppi di Active Directory. Questo controllo viene eseguito chiamando il metodo **IsInRole** sull'interfaccia **IPrincipal** e viene definito controllo dell'accesso basato sui ruoli (RBAC). Per altre informazioni, vedere [Controllo degli accessi in base al ruolo](../../../docs/framework/security/claims-based-authorization-using-wif.md#BKMK_1).  Le attestazioni possono essere utilizzate per trasferire le informazioni sui ruoli per supportare i comuni meccanismi dell'autorizzazione basata sui ruoli.  
  
 Inoltre, possono essere utilizzate per abilitare decisioni di autorizzazione più complesse oltre ai ruoli. Le attestazioni possono essere basate su qualsiasi informazione relativa all'utente, ovvero età, codice postale, numero di scarpe e così via. Un meccanismo di controllo degli accessi basato su attestazioni arbitrarie è definito autorizzazione basata sulle attestazioni. Per altre informazioni, vedere [Autorizzazione basata sulle attestazioni](../../../docs/framework/security/claims-based-authorization-using-wif.md#BKMK_2).  
  
<a name="BKMK_1"></a>   
## <a name="role-based-access-control"></a>Controllo dell'accesso basato sui ruoli  
 Il controllo dell'accesso basato sui ruoli è un approccio di autorizzazione in cui le autorizzazioni utente vengono gestite e applicate da un'applicazione basata sui ruoli utente. Se un utente dispone di un ruolo necessario per l'esecuzione di un'azione, l'accesso viene consentito; in caso contrario, viene negato.  
  
### <a name="iprincipalisinrole-method"></a>Metodo IPrincipal.IsInRole  
 Per implementare il controllo degli accessi in base al ruolo nelle applicazioni in grado di riconoscere attestazioni, usare il metodo **IsInRole()** nell'interfaccia **IPrincipal**, proprio come nelle applicazioni che non sono in grado di riconoscere attestazioni. Il metodo **IsInRole()** può essere usato in diversi modi:  
  
-   Eseguendo una chiamata esplicita su **IPrincipal.IsInRole("Administrator")**. In questo approccio, il risultato è un valore booleano. Utilizzarlo nelle istruzioni condizionali. Può essere utilizzato in modo arbitrario in qualsiasi punto nel codice.  
  
-   Usando la richiesta di sicurezza **PrincipalPermission.Demand()**. In questo approccio, il risultato è un'eccezione in caso di richiesta non soddisfatta. Deve rientrare nella strategia di gestione delle eccezioni. La generazione di eccezioni è molto più costosa dal punto di vista delle prestazioni rispetto alla restituzione di un valore booleano. Può essere utilizzata in qualsiasi punto nel codice.  
  
-   Usando gli attributi dichiarativi **[PrincipalPermission(SecurityAction.Demand, Role = "Administrator")]**. Questo approccio viene chiamato dichiarativo, in quanto viene utilizzato per decorare i metodi. Non può essere utilizzato in blocchi di codice nelle implementazioni del metodo. Il risultato è un'eccezione in caso di richiesta non soddisfatta. È necessario assicurarsi che rientri nella strategia di gestione delle eccezioni.  
  
-   Usando l'autorizzazione basata su URL tramite la sezione **\<authorization>** in **web.config**. Questo approccio è utile quando si gestisce l'autorizzazione in un livello URL. Si tratta del livello più grezzo tra quelli indicati in precedenza. Il vantaggio di questo approccio è che le modifiche vengono apportate nel file di configurazione, pertanto il codice non deve essere compilato per sfruttare la modifica.  
  
### <a name="expressing-roles-as-claims"></a>Espressione dei ruoli come attestazioni  
 Quando viene chiamato il metodo **IsInRole()**, viene eseguito un controllo per determinare se l'utente corrente dispone del ruolo in questione. Nelle applicazioni in grado di riconoscere attestazioni il ruolo è espresso da un tipo di attestazione del ruolo che deve essere disponibile nel token. Il tipo di attestazione del ruolo viene espresso tramite l'URI seguente:  
  
 `http://schemas.microsoft.com/ws/2008/06/identity/claims/role`
  
 Vi sono diversi modi per arricchire un token con un tipo di attestazione del ruolo:  
  
-   **Durante il rilascio del token**. Quando un utente viene autenticato, l'attestazione del ruolo può essere emessa dal servizio token di sicurezza del provider di identità o da un provider di federazioni, ad esempio il Servizio di controllo di accesso di Microsoft Azure.  
  
-   **Trasformando le attestazioni arbitrarie in tipi di attestazioni del ruolo tramite ClaimsAuthenticationManager**. ClaimsAuthenticationManager è un componente fornito come parte di WIF. Consente l'intercettazione delle richieste quando tramite esse viene avviata un'applicazione, esaminando i token e trasformandoli con l'aggiunta, la modifica o la rimozione di attestazioni. Per altre informazioni su come usare ClaimsAuthenticationManager per trasformare le attestazioni, vedere [How To: In base al ruolo di implementare il controllo di accesso (RBAC) in un'applicazione ASP.NET compatibili con le attestazioni mediante WIF e ACS](https://go.microsoft.com/fwlink/?LinkID=247445).  
  
-   **Eseguendo il mapping di attestazioni arbitrarie a un tipo di ruolo tramite la sezione di configurazione samlSecurityTokenRequirement**. Si tratta di un approccio dichiarativo in cui la trasformazione delle attestazioni viene eseguita usando solo la configurazione, senza intervenire sul codice.  
  
<a name="BKMK_2"></a>   
## <a name="claims-based-authorization"></a>Autorizzazione basata sulle attestazioni  
 L'autorizzazione basata sulle attestazioni è un approccio in cui la decisione di autorizzazione di concedere o negare l'accesso è basata sulla logica arbitraria che utilizza i dati disponibili nelle attestazioni per prendere la decisione. Si tenga presente che nel caso del controllo dell'accesso basato sui ruoli, l'unica attestazione utilizzata è quella di tipo del ruolo. Per controllare se l'utente appartiene o meno a un ruolo specifico, è stata utilizzata un'attestazione di tipo del ruolo. Per illustrare il processo per prendere decisioni di autorizzazione utilizzando l'approccio basato sulle attestazioni, si tengano in considerazione i passaggi seguenti:  
  
1. Dall'applicazione viene ricevuta una richiesta in cui l'utente deve essere autenticato.  
  
2. Tramite WIF l'utente viene reindirizzato al provider di identità. Dopo essere stata autenticata, la richiesta di applicazione viene eseguita con un token di sicurezza associato che rappresenta l'utente che contiene le attestazioni su di esse. Queste attestazioni vengono associate da WIF all'entità principale che rappresenta l'utente.  
  
3. Tramite l'applicazione le attestazioni vengono passate al meccanismo della logica delle decisioni. Può essere il codice in memoria, una chiamata a un servizio Web, una query a un database, un motore regole avanzato o l'utilizzo di ClaimsAuthorizationManager.  
  
4. Con il meccanismo delle decisioni viene calcolato il risultato in base alle attestazioni.  
  
5. L'accesso viene consentito se il risultato è true e viene negato se è false. Ad esempio, la regola potrebbe essere che l'utente ha 21 anni, o anche di più, e vive nello stato di Washington.  
  
 L'oggetto <xref:System.Security.Claims.ClaimsAuthorizationManager> è utile per esternalizzare la logica delle decisioni per l'autorizzazione basata su attestazioni nelle applicazioni. ClaimsAuthorizationManager è un componente di WIF fornito come parte di .NET 4.5. Con ClaimsAuthorizationManager è possibile intercettare le richieste in ingresso e implementare qualsiasi logica di scelta per prendere decisioni di autorizzazioni basate sulle attestazioni in ingresso. Questo aspetto diventa importante quando è necessario modificare la logica dell'autorizzazione. In tal caso, l'utilizzo di ClaimsAuthorizationManager non influirà sull'integrità dell'applicazione, quindi riducendo la probabilità di un errore di applicazione come risultato della modifica. Per altre informazioni su come usare ClaimsAuthorizationManager per implementare il controllo di accesso basato sulle attestazioni, vedere [How To: Implementare autorizzazione delle attestazioni in un'applicazione ASP.NET compatibili con le attestazioni mediante WIF e ACS](https://go.microsoft.com/fwlink/?LinkID=247446).
