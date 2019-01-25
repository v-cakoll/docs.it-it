---
title: Linee guida per la migrazione di un'applicazione compilata con le versioni di WIF dalla 3.5 alla 4.5
ms.date: 03/30/2017
ms.assetid: 7a32fe6e-5f68-4693-9371-19411fa8063c
author: BrucePerlerMS
ms.openlocfilehash: d843f2d01072db8b848f4d6f26dba32b4e48f302
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696188"
---
# <a name="guidelines-for-migrating-an-application-built-using-wif-35-to-wif-45"></a>Linee guida per la migrazione di un'applicazione compilata con le versioni di WIF dalla 3.5 alla 4.5
## <a name="applies-to"></a>Si applica a  
  
-   Microsoft® Windows® Identity Foundation 3.5 e 4.5.  
  
## <a name="overview"></a>Panoramica  
 Windows Identity Foundation in origine è stato reso disponibile nello stesso periodo di .NET 3.5 SP1. Questa versione di Windows Identity Foundation è nota come Windows Identity Foundation 3.5. Questa versione è stata resa disponibile come runtime ed SDK separati e questo significa che in ogni computer in cui viene eseguita un'applicazione abilitata per Windows Identity Foundation deve essere installato il runtime di Windows Identity Foundation e che gli sviluppatori devono installare l'SDK per ottenere i modelli e gli strumenti di Visual Studio che permettono di sviluppare applicazioni abilitate per Windows Identity Foundation. A partire da .NET 4.5, Windows Identity Foundation è stato completamente integrato in .NET Framework. Un runtime separato non è più necessario e gli strumenti di Windows Identity Foundation possono essere installati in Visual Studio 2012 usando il gestore delle estensioni di Visual Studio. Questa versione di Windows Identity Foundation è nota come Windows Identity Foundation 4.5.  
  
 Per l'integrazione di Windows Identity Foundation in .NET è stato necessario apportare diverse modifiche alla superficie API di Windows Identity Foundation. Windows Identity Foundation 4.5 include nuovi spazi dei nomi, alcune modifiche relative agli elementi di configurazione e nuovi strumenti per Visual Studio. Questo argomento contiene linee guida che semplificano la migrazione di applicazioni create con Windows Identity Foundation 3.5 a Windows Identity Foundation 4.5. In alcuni scenari potrebbe essere necessario eseguire applicazioni legacy create con Windows Identity Foundation 3.5 in computer che eseguono Windows 8 o Windows Server 2012. Questo argomento contiene anche le linee guida su come abilitare Windows Identity Foundation 3.5 per questi sistemi operativi.  
  
## <a name="changes-required-for-wif-45"></a>Modifiche necessarie per Windows Identity Foundation 4.5  
 Questa sezione descrive le modifiche necessarie per eseguire la migrazione di un'applicazione Windows Identity Foundation 3.5 a Windows Identity Foundation 4.5.  
  
### <a name="assembly-and-namespace-changes"></a>Modifiche apportate agli assembly e agli spazi dei nomi  
 In Windows Identity Foundation 3.5 tutte le classi sono contenute nell'assembly `Microsoft.IdentityModel` (microsoft.identitymicrosoft.identitymodel.dll). In Windows Identity Foundation 4.5 le classi sono state suddivise tra questi assembly: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll) e `System.ServiceModel` (System.ServiceModel.dll).  
  
 Le classi di Windows Identity Foundation 3.5 sono tutte contenute in uno degli spazi dei nomi `Microsoft.IdentityModel`, ad esempio `Microsoft.IdentityModel`, `Microsoft.IdentityModel.Tokens`, `Microsoft.IdentityModel.Web`e così via. In Windows Identity Foundation 4.5 le classi sono ora distribuite tra gli spazi dei nomi [System.IdentityModel](https://go.microsoft.com/fwlink/?LinkId=272004), lo spazio dei nomi <xref:System.Security.Claims?displayProperty=nameWithType> e lo spazio dei nomi <xref:System.ServiceModel.Security?displayProperty=nameWithType>. Oltre a questa riorganizzazione, alcune classi di Windows Identity Foundation 3.5 sono state eliminate in Windows Identity Foundation 4.5.  
  
 La tabella seguente mostra alcuni degli spazi dei nomi più importanti di Windows Identity Foundation 4.5 e il tipo di classi in essi contenute. Per informazioni più dettagliate sul mapping degli spazi dei nomi tra Windows Identity Foundation 3.5 e Windows Identity Foundation 4.5 e sulle classi e sugli spazi dei nomi eliminati in Windows Identity Foundation 4.5, vedere [Mapping dello spazio dei nomi tra WIF 3.5 e WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md).  
  
|Spazio dei nomi di Windows Identity Foundation 4.5|Descrizione|  
|-----------------------|-----------------|  
|<xref:System.IdentityModel?displayProperty=nameWithType>|Contiene le classi che rappresentano trasformazioni dei cookie, servizi token di sicurezza e lettori di dizionario XML specializzati. Contiene le classi di questi spazi dei nomi di Windows Identity Foundation 3.5: `Microsoft.IdentityModel`, `Microsoft.IdentityModel.SecurityTokenService` e `Microsoft.IdentityModel.Threading`.|  
|<xref:System.Security.Claims?displayProperty=nameWithType>|Contiene le classi che rappresentano attestazioni, identità basate sulle attestazioni, entità basate sulle attestazioni e altri elementi modello di identità basati sulle attestazioni. Contiene le classi dello spazio dei nomi `Microsoft.IdentityModel.Claims`.|  
|<xref:System.IdentityModel.Tokens?displayProperty=nameWithType>|Contiene le classi che rappresentano token di sicurezza, gestori di token di sicurezza e altri elementi token di sicurezza. Contiene le classi di questi spazi dei nomi di Windows Identity Foundation 3.5: `Microsoft.IdentityModel.Tokens`, `Microsoft.IdentityModel.Tokens.Saml11` e `Microsoft.IdentityModel.Tokens.Saml2`.|  
|<xref:System.IdentityModel.Services?displayProperty=nameWithType>|Contiene le classi usate in scenari passivi (WS-Federation). Contiene le classi dello spazio dei nomi `Microsoft.IdentityModel.Web`.|  
|<xref:System.ServiceModel.Security?displayProperty=nameWithType>|Le classi che rappresentano contratti, canali, host servizio e altri elementi WCF usati in scenari attivi (WS-Trust) sono ora inclusi in questo spazio dei nomi. In Windows Identity Foundation 3.5 queste classi sono incluse nello spazio dei nomi `Microsoft.IdentityModel.Protocols.WSTrust`.|  
  
> [!IMPORTANT]
>  Questi spazi dei nomi `System.IdentityModel` contengono classi che implementano il modello di identità basato sulle attestazioni di WCF: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType> e <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>. Il modello di identità basato sulle attestazioni di WCF è stato sostituito da WIF. Non usare le classi in questi tre spazi dei nomi per la compilazione di soluzioni basate su WIF.  
  
### <a name="changes-due-to-net-integration"></a>Modifiche necessarie per l'integrazione in .NET  
 Windows Identity Foundation è ora integrato in .NET Framework. La maggior parte delle classi di identità ed entità .NET deriva ora da <xref:System.Security.Claims.ClaimsIdentity?displayProperty=nameWithType> e <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=nameWithType>. In Windows Identity Foundation 4.5 sono state apportate le modifiche seguenti:  
  
-   Le classi di Windows Identity Foundation che rappresentano attestazioni, identità ed entità sono ora incluse nello spazio dei nomi <xref:System.Security.Claims?displayProperty=nameWithType>.  
  
    > [!IMPORTANT]
    >  Lo spazio dei nomi <xref:System.IdentityModel.Claims?displayProperty=nameWithType> contiene classi che rappresentano elementi nel modello di identità basato sulle attestazioni di WCF. Molte di queste classi hanno gli stessi nomi delle classi di Windows Identity Foundation, ad esempio `Claims`. Non usare queste classi per la compilazione di soluzioni basate su Windows Identity Foundation.  
  
-   Le classi di identità ed entità .NET derivano ora direttamente da <xref:System.Security.Claims.ClaimsIdentity?displayProperty=nameWithType> e <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=nameWithType>, che rappresentano identità ed entità basate sulle attestazioni. Per questo motivo, le interfacce `IClaimsIdentity` e `IClaimsPrincipal` di Windows Identity Foundation 3.5 non sono più necessarie né disponibili in Windows Identity Foundation 4.5.  
  
-   Poiché le classi di identità ed entità .NET come <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType> e <xref:System.Security.Principal.WindowsPrincipal?displayProperty=nameWithType> derivano ora da <xref:System.Security.Claims.ClaimsIdentity> e <xref:System.Security.Claims.ClaimsPrincipal>, includono funzionalità per le attestazioni integrate. Per questo motivo, le classi di identità ed entità specifiche delle attestazioni come `WindowsClaimsIdentity` e `WindowsClaimsPrincipal` disponibili in Windows Identity Foundation 3.5 non sono più necessarie e non sono incluse in Windows Identity Foundation 4.5.  
  
### <a name="other-changes-to-wif-functionality"></a>Altre modifiche apportate alle funzionalità di Windows Identity Foundation  
 Oltre alle modifiche relative agli spazi dei nomi e quelle necessarie per l'integrazione con .NET, in Windows Identity Foundation 4.5 sono state introdotte le modifiche alle funzionalità indicate di seguito.  
  
-   La classe `Microsoft.IdentityModel.ExceptionMapper`, che fornisce una funzionalità per il mapping delle eccezioni a errori SOAP specifici, è stata rimossa.  
  
-   La superficie delle eccezioni è stata notevolmente ridotta.  
  
-   Molte delle classi che definiscono costanti specifiche del protocollo o di WS-* sono state rimosse, ad esempio la classe `Microsoft.IdentityModel.WSAddressing10Constants`, che definisce costanti correlate a WS-Addressing 1.0.  
  
-   Le attestazioni per Windows Token Service (c2wts) e le classi associate nello spazio dei nomi `Microsoft.IdentityModel.WindowsTokenService` sono state rimosse.  
  
### <a name="wif-configuration-changes"></a>Modifiche apportate alla configurazione di Windows Identity Foundation  
 Molte delle modifiche apportate al file di configurazione sono dovute agli aggiornamenti degli spazi dei nomi in Windows Identity Foundation 4.5. Ad esempio, si consideri la voce seguente inclusa in Windows Identity Foundation 3.5 nella sezione `<httpModules>` per l'aggiunta del gestore di autenticazione WS-Federation a un'applicazione:  
  
```xml  
<add name="WSFederationAuthenticationModule" type="Microsoft.IdentityModel.Web.WSFederationAuthenticationModule, Microsoft.IdentityModel, Version=3.5.0.0, Culture=neutral, PublicKeyToken=abcd … 5678" />  
```  
  
 Questa voce è stata aggiornata in Windows Identity Foundation 4.5 per includere i nuovi spazi dei nomi e la nuova versione dell'assembly:  
  
```xml  
<add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcd … 5678"/>  
```  
  
 L'elenco seguente include le principali modifiche apportate al file di configurazione in Windows Identity Foundation 4.5.  
  
-   La sezione `<microsoft.identityModel>` è ora la sezione [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md).  
  
-   L'elemento `<service>` è ora l'elemento [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md).  
  
-   È stata aggiunta la nuova sezione [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) per specificare le impostazioni che controllano il comportamento negli scenari passivi (WS-Federation).  
  
-   L'elemento [\<federationConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) e i relativi elementi figlio sono stati spostati dall'elemento `<service>` di Windows Identity Foundation 3.5 al nuovo elemento `<system.identityModel.services>`.  
  
-   Diversi elementi che possono essere specificati a livello di servizio direttamente nell'elemento `<service>` in Windows Identity Foundation 3.5 possono ora essere specificati solo nell'elemento [\<securityTokenHandlerConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md). Questi elementi possono comunque essere specificati nell'elemento [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) in Windows Identity Foundation 4.5 per compatibilità con le versioni precedenti.  
  
 Per un elenco completo degli elementi di configurazione di Windows Identity Foundation 4.5, vedere [Schema di configurazione di Windows Identity Foundation](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/index.md).  
  
### <a name="visual-studio-tooling-changes"></a>Modifiche apportate agli strumenti di Visual Studio  
 Windows Identity Foundation 3.5 SDK offre un'utilità di federazione autonoma, FedUtil.exe (FedUtil), che può essere usata per l'outsourcing della gestione delle identità in applicazioni abilitate per Windows Identity Foundation a un servizio token di sicurezza. Questo strumento aggiunge impostazioni di Windows Identity Foundation al file di configurazione dell'applicazione per permettere all'applicazione di ottenere token di sicurezza da uno o più servizi token di sicurezza ed è disponibile in Visual Studio tramite il pulsante **Aggiungi riferimento al servizio token di sicurezza**. L'utilità FedUtil non è inclusa in Windows Identity Foundation 4.5. Windows Identity Foundation 4.5 supporta invece una nuova estensione di Visual Studio chiamata Identity and Access Tool per Visual Studio 2012, che può essere usata per modificare il file di configurazione dell'applicazione con le impostazioni di Windows Identity Foundation necessarie per l'outsourcing della gestione delle identità a un servizio token di sicurezza. Identity and Access Tool implementa anche un servizio token di sicurezza chiamato servizio token di sicurezza locale, che può essere usato per testare le applicazioni abilitate per Windows Identity Foundation. In molti casi, questa funzionalità elimina la necessità di compilare servizi token di sicurezza personalizzati, spesso necessari in Windows Identity Foundation 3.5 per testare le soluzioni in fase di sviluppo. Per questo motivo, i modelli di servizio token di sicurezza non sono più supportati in Visual Studio 2012, ma le classi che supportano lo sviluppo di servizi token di sicurezza sono ancora disponibili in Windows Identity Foundation 4.5.  
  
 È possibile installare Identity and Access Tool dal estensioni e gestione degli aggiornamenti in Visual Studio oppure è possibile scaricarlo dalla pagina seguente nella galleria di codice: [Identity and Access Tool per Visual Studio 2012 su Code Gallery](https://go.microsoft.com/fwlink/?LinkID=245849). L'elenco seguente offre un riepilogo delle modifiche apportate agli strumenti di Visual Studio:  
  
-   È stata rimossa la funzionalità Aggiungi riferimento al servizio token di sicurezza. La funzionalità è stata sostituita da Identity and Access Tool.  
  
-   I modelli di servizio token di sicurezza di Visual Studio sono stati rimossi. È possibile usare il servizio token di sicurezza locale, disponibile tramite Identity and Access Tool, per testare le soluzioni di gestione delle identità sviluppate con Windows Identity Foundation. La configurazione del servizio token di sicurezza locale può essere modificata per personalizzare le attestazioni rese disponibili.  
  
-   L'utilità di federazione autonoma (FedUtil) non è disponibile in Windows Identity Foundation 4.5. È possibile usare Identity and Access Tool per modificare il file di configurazione per l'outsourcing della gestione delle identità a un servizio token di sicurezza.  
  
 Per altre informazioni su Identity and Access Tool, vedere [Identity and Access Tool per Visual Studio 2012](../../../docs/framework/security/identity-and-access-tool-for-vs.md)  
  
<a name="BKMK_ToolingChanges"></a>   
### <a name="passive-ws-federation-scenarios"></a>Scenari passivi (WS-Federation):  
  
-   Le classi che supportano gli scenari passivi sono state spostate nello spazio dei nomi <xref:System.IdentityModel.Services?displayProperty=nameWithType>. In Windows Identity Foundation 3.5 queste classi sono incluse nello spazio dei nomi `Microsoft.IdentityModel.Web`.  
  
-   Le classi incluse nello spazio dei nomi `Microsoft.IdentityModel.Web.Configuration` sono state spostate in <xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>. Queste classi rappresentano oggetti specifici della configurazione in scenari passivi.  
  
-   `FederatedPasssiveSignInControl` non è più supportato. Tutte le classi incluse nello spazio dei nomi `Microsoft.IdentityModel.Web.Controls` sono state rimosse da Windows Identity Foundation 4.5.  
  
-   La funzionalità di disconnessione del modulo di autenticazione WS-Federation (<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>) è diversa rispetto a Windows Identity Foundation 3.5. Per altre informazioni sul funzionamento della disconnessione in Windows Identity Foundation 4.5, vedere l'argomento relativo alla classe <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>.  
  
### <a name="active-wcfws-trust-scenarios"></a>Scenari attivi (WCF/WS-Trust):  
  
-   Lo spazio dei nomi `Microsoft.IdentityModel.Protocols.WSTrust` è stato suddiviso prevalentemente tra due spazi dei nomi in Windows Identity Foundation 4.5. Le classi che rappresentano elementi specifici del protocollo WS-Trust si trovano ora in <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType>. Sono incluse le classi come <xref:System.IdentityModel.Protocols.WSTrust.RequestSecurityToken>. Le classi che rappresentano contratti di servizio, canali, host servizio e altri elementi coinvolti nell'uso di WS-Trust in applicazioni WCF sono stati spostati in <xref:System.ServiceModel.Security?displayProperty=nameWithType>, ad esempio l'interfaccia <xref:System.ServiceModel.Security.IWSTrust13AsyncContract>.  
  
-   La configurazione di un'applicazione WCF per l'uso di Windows Identity Foundation è stata notevolmente semplificata. Nelle versioni precedenti `Microsoft.IdentityModel.Configuration.ConfigureServiceHostBehaviorExtensionElement` deve essere aggiunto come estensione di comportamento e questa funzionalità viene quindi usata per integrare Windows Identity Foundation nel comportamento del servizio specificando un elemento `<federatedServiceHostConfiguration>`. Windows Identity Foundation 4.5 è stato integrato ancora di più con WCF. È ora possibile abilitare Windows Identity Foundation in un servizio WCF specificando l'attributo `useIdentityConfiguration` nell'elemento `<system.serviceModel>`/`<behaviors>`/`<serviceBehaviors>`/`<serviceCredentials>`, come nel codice XML seguente:  
  
    ```xml  
    <serviceCredentials useIdentityConfiguration="true">  
        <!--Certificate added by Identity And Access VS Package.  Subject='CN=localhost', Issuer='CN=localhost'. Make sure you have this certificate installed. The Identity and Access tool does not install this certificate.-->  
        <serviceCertificate findValue="CN=localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName" />  
    </serviceCredentials>  
    ```  
  
-   In Windows Identity Foundation 4.5 il certificato di servizio usato da un servizio attivo (WCF) deve essere specificato nell'host servizio. Nella configurazione è possibile usare l'elemento `<system.serviceModel>`/`<behaviors>`/`<serviceBehaviors>`/`<serviceCredentials>`/`<serviceCertificate>`, come mostrato nell'esempio precedente. In Windows Identity Foundation 3.5 il certificato di servizio può essere specificato tramite l'elemento figlio `<serviceCertificate>` dell'elemento `<service>` di Windows Identity Foundation. Questa funzionalità non è disponibile in Windows Identity Foundation 4.5. Specificare invece l'elemento `<serviceCertificate>` all'interno dell'elemento `<serviceCredentials>`.  
  
-   Le classi usate per integrare Windows Identity Foundation 3.5 in WCF non sono più disponibili. Sono incluse queste classi dello spazio dei nomi `Microsoft.IdentityModel.Tokens`: `FederatedSecurityTokenManager`, `FederatedServiceCredentials` e `IdentityModelServiceAuthorizationManager`, nonché la classe `Microsoft.IdentityModel.Configuration.ConfigureServiceHostBehaviorExtensionElement`.  
  
## <a name="enabling-wif-35-in-windows-8"></a>Abilitazione di Windows Identity Foundation 3.5 in Windows 8  
 Poiché Windows Identity Foundation 4.5 fa parte di .NET 4.5, è automaticamente abilitato nei computer che eseguono Windows 8 e Windows Server 2012 e le applicazioni compilate con Windows Identity Foundation 4.5 vengono eseguite automaticamente in Windows 8 o Windows Server 2012. Tuttavia, potrebbe essere necessario eseguire applicazioni compilate con Windows Identity Foundation 3.5 in un computer con Windows 8 o Windows Server 2012. In questo caso, è necessario abilitare Windows Identity Foundation 3.5 nel computer di destinazione. A questo scopo, in un computer che esegue Windows 8 è possibile usare lo strumento Gestione e manutenzione immagini distribuzione. In un computer che esegue Windows Server 2012 è possibile usare lo strumento Gestione e manutenzione immagini distribuzione oppure il cmdlet `Add-WindowsFeature` di Windows PowerShell. In entrambi i casi, è possibile richiamare i comandi appropriati dalla riga di comando o dall'ambiente di Windows PowerShell.  
  
 I comandi seguenti mostrano come usare lo strumento Gestione e manutenzione immagini di distribuzione dalla riga di comando o dall'ambiente di Windows PowerShell. Per impostazione predefinita, il modulo PowerShell per Gestione e manutenzione immagini di distribuzione è incluso in Windows 8 e Windows Server 2012 e non deve essere importato. Per altre informazioni sull'uso di Gestione e manutenzione immagini di distribuzione con Windows PowerShell, vedere [Usare Gestione e manutenzione immagini distribuzione in Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=254419).  
  
 Per abilitare Windows Identity Foundation 3.5 con Gestione e manutenzione immagini distribuzione:  
  
```  
dism /online /enable-feature:windows-identity-foundation  
```  
  
 Per disabilitare Windows Identity Foundation 3.5 con Gestione e manutenzione immagini distribuzione:  
  
```  
dism /online /disable-feature:windows-identity-foundation  
```  
  
 Per controllare quali funzionalità sono abilitate o disabilitate con Gestione e manutenzione immagini distribuzione:  
  
```  
dism /online /get-features  
```  
  
 In alternativa, nei computer che eseguono Windows Server 2012 è possibile abilitare Windows Identity Foundation 3.5 usando il cmdlet `Add-WindowsFeature` di Windows PowerShell. Per usare la riga di comando a questo scopo, è possibile immettere il comando seguente:  
  
```  
powershell "add-windowsfeature windows-identity-foundation"  
```  
  
 Dall'ambiente di Windows PowerShell, è possibile immettere direttamente il comando:  
  
```  
add-windowsfeature windows-identity-foundation  
```  
  
> [!NOTE]
>  Poiché molte delle classi in Windows Identity Foundation 3.5 e Windows Identity Foundation 4.5 condividono gli stessi nomi, quando si usano Windows Identity Foundation 3.5 e Windows Identity Foundation 4.5 insieme, assicurarsi di usare nomi di classe completi o alias dello spazio dei nomi per distinguere tra le classi di Windows Identity Foundation 3.5 e quelle di Windows Identity Foundation 4.5.  
  
## <a name="see-also"></a>Vedere anche
- [Schema di configurazione di WIF](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/index.md)
- [Mapping dello spazio dei nomi tra WIF 3.5 e WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)
- [Novità di Windows Identity Foundation 4.5](../../../docs/framework/security/whats-new-in-wif.md)
- [Identity and Access Tool per Visual Studio 2012](../../../docs/framework/security/identity-and-access-tool-for-vs.md)
