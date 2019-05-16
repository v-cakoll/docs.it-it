---
title: Modello di programmazione attestazioni WIF
ms.date: 03/30/2017
ms.assetid: 149cb875-9b1c-4695-b88a-fbf1725a02f9
author: BrucePerlerMS
ms.openlocfilehash: 19dbf5ed8852ea8d3ad9be078cb575c6e4dc06ed
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631896"
---
# <a name="wif-claims-programming-model"></a>Modello di programmazione attestazioni WIF
Gli sviluppatori ASP.NET e Windows Communication Foundation (WCF) usano in genere le interfacce IIdentity e IPrincipal per lavorare con le informazioni sull'identità dell'utente. In .NET 4.5 è stato integrato Windows Identity Foundation (WIF), in modo che le attestazioni siano ora sempre presenti per qualsiasi entità di sicurezza, come illustrato nel diagramma seguente:

 ![Diagramma che mostra il modello di programmazione attestazioni WIF.](./media/wif-claims-programming-model/wif-claims-programming-model.png)

 In .NET 4.5 System.Security.Claims contiene le nuove classi ClaimsPrincipal e ClaimsIdentity (vedere il diagramma precedente). Tutte le entità di sicurezza in .NET derivano ora da ClaimsPrincipal. Tutte le classi di identità predefinite, come FormsIdentity per ASP.NET e WindowsIdentity, derivano ora da ClaimsIdentity. Analogamente, tutte le classi di entità di sicurezza predefinite, come GenericPrincipal e WindowsPrincipal, derivano da ClaimsPrincipal.

 Un'attestazione è rappresentata dalla classe <xref:System.Security.Claims.Claim>. Questa classe ha le proprietà importanti seguenti:

- <xref:System.Security.Claims.Claim.Type%2A> rappresenta il tipo di attestazione ed è in genere un URI. Ad esempio, l'attestazione di indirizzo di posta elettronica è rappresentato come `http://schemas.microsoft.com/ws/2008/06/identity/claims/email`.

- <xref:System.Security.Claims.Claim.Value%2A> contiene il valore dell'attestazione e viene rappresentato come stringa. Ad esempio, l'indirizzo di posta elettronica può essere rappresentato come "someone@contoso.com".

- <xref:System.Security.Claims.Claim.ValueType%2A> rappresenta il tipo di valore dell'attestazione ed è in genere un URI. Ad esempio, il tipo di stringa è rappresentato come `http://www.w3.org/2001/XMLSchema#string`. Il tipo valore deve essere un oggetto QName in base allo standard XML Schema. Il valore deve essere nel formato `namespace#format` per consentire a WIF di restituire un valore QName valido. Se lo spazio dei nomi non è uno spazio dei nomi ben definito, il codice XML generato probabilmente non può essere convalidato dallo schema, perché non ci sarà un file XSD pubblicato per tale spazio dei nomi. Il tipo valore predefinito è `http://www.w3.org/2001/XMLSchema#string`. Per informazioni sui tipi di valore ben noto che è possibile usare in modo sicuro, vedere la [W3C XML Schema](https://www.w3.org/2001/XMLSchema) pagina.

- <xref:System.Security.Claims.Claim.Issuer%2A> è l'identificatore del servizio token di sicurezza che ha rilasciato l'attestazione. Può essere rappresentato come URL del servizio token di sicurezza o come nome che rappresenta il servizio token di sicurezza, ad esempio `https://sts1.contoso.com/sts`.

- <xref:System.Security.Claims.Claim.OriginalIssuer%2A> è l'identificatore del servizio token di sicurezza che ha originariamente rilasciato l'attestazione, indipendentemente dal numero servizi token di sicurezza nella catena. Viene rappresentato semplicemente come <xref:System.Security.Claims.Claim.Issuer%2A>.

- <xref:System.Security.Claims.Claim.Subject%2A> è l'oggetto la cui identità viene esaminata. Esso contiene una <xref:System.Security.Claims.ClaimsIdentity>.

- <xref:System.Security.Claims.Claim.Properties%2A> è un dizionario che consente allo sviluppatore di fornire dati specifici dell'applicazione da trasferire insieme alle altre proprietà e può essere usato per la convalida personalizzata.

## <a name="identity-delegation"></a>Delega di identità
Una proprietà importante di <xref:System.Security.Claims.ClaimsIdentity> è <xref:System.Security.Claims.ClaimsIdentity.Actor%2A>. Questa proprietà consente la delega delle credenziali in un sistema multilivello in cui un livello intermedio funge da client per effettuare le richieste a un servizio back-end.

### <a name="accessing-claims-through-threadcurrentprincipal"></a>Accesso alle attestazioni tramite Thread.CurrentPrincipal
Per accedere al set di attestazioni dell'utente corrente in un'applicazione relying party, usare `Thread.CurrentPrincipal`.

L'esempio di codice seguente mostra l'uso di questo metodo per ottenere un oggetto System.Security.Claims.ClaimsIdentity:

```csharp
ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;
```

Per altre informazioni, vedere <xref:System.Security.Claims>.

### <a name="role-claim-type"></a>Tipo di attestazione del ruolo
Parte della configurazione dell'applicazione relying party consiste nel determinare il tipo di attestazione del ruolo. Questo tipo di attestazione viene usato da System.Security.Claims.ClaimsPrincipal.IsInRole(System.String). Il tipo di attestazione predefinito è `http://schemas.microsoft.com/ws/2008/06/identity/claims/role`.

### <a name="claims-extracted-by-windows-identity-foundation-from-different-token-types"></a>Attestazioni estratte da Windows Identity Foundation da tipi di token diversi
Per impostazione predefinita, WIF supporta diverse combinazioni di meccanismi di autenticazione. La tabella seguente elenca le attestazioni che WIF estrae da tipi di token diversi.

|Tipo di token|Attestazione generata|Mapping con il token di accesso di Windows|
|-|-|-|
|SAML 1.1|1.  Tutte le attestazioni da System.IdentityModel.SecurityTokenService.GetOutputClaimsIdentity(System.Security.Claims.ClaimsPrincipal,System.IdentityModel.Protocols.WSTrust.RequestSecurityToken,System.IdentityModel.Scope).<br />2.  Attestazione `http://schemas.microsoft.com/ws/2008/06/identity/claims/confirmationkey` che contiene la serializzazione XML della chiave di conferma, se il token contiene un token di prova.<br />3.  Attestazione `http://schemas.microsoft.com/ws/2008/06/identity/claims/samlissuername` dall'elemento Issuer.<br />4.  Attestazioni AuthenticationMethod AuthenticationInstant, se il token contiene un'istruzione di autenticazione.|Oltre alle attestazioni elencate in "SAML 1.1", ad eccezione delle attestazioni di tipo `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name`, verranno aggiunte le attestazioni correlate all'autenticazione di Windows e l'identità verrà rappresentata da WindowsClaimsIdentity.|
|SAML 2.0|Uguale a "SAML 1.1".|Uguale a "SAML 1.1 con mapping all'account Windows".|
|X509|1.  Attestazioni con nome distinto X500, emailName, dnsName, SimpleName, UpnName, UrlName, thumbprint, RsaKey (che è possibile estrarre usando il metodo RSACryptoServiceProvider.ExportParameters della proprietà X509Certificate2.PublicKey.Key), DsaKey (che è possibile estrarre usando il metodo DSACryptoServiceProvider.ExportParameters della proprietà X509Certificate2.PublicKey.Key), proprietà SerialNumber del certificato X509.<br />2.  Attestazione AuthenticationMethod con valore `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/x509`. Attestazione AuthenticationInstant con il valore del momento in cui il certificato è stato convalidato, nel formato DateTime XmlSchema.|1.  Usa il nome di dominio completo dell'account di Windows come valore dell'attestazione `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name`. .<br />2.  Attestazioni del certificato X509 non mappate a Windows e attestazioni dell'account Windows ottenute dal mapping del certificato a Windows.|
|UPN|1.  Le attestazioni sono simili alle attestazioni nella sezione di autenticazione di Windows.<br />2.  Attestazione AuthenticationMethod con valore `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/password`. Attestazione AuthenticationInstant con il valore del momento in cui la password è stata convalidata, nel formato DateTime XmlSchema.||
|Windows (Kerberos o NTLM)|1.  Attestazioni generate dal token di accesso, ad esempio: PrimarySID, DenyOnlyPrimarySID, PrimaryGroupSID, DenyOnlyPrimaryGroupSID, GroupSID, DenyOnlySID e Name<br />2.  AuthenticationMethod con valore `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/windows`. AuthenticationInstant con il valore del momento in cui il token di accesso di Windows è stato creato, nel formato DateTime XMLSchema.||
|Coppia di chiavi RSA|1.  Attestazione `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/rsa` con il valore di RSAKeyValue.<br />2.  Attestazione AuthenticationMethod con valore `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/signature`. Attestazione AuthenticationInstant con il valore del momento in cui la chiave RSA è stata convalidata (ovvero la firma è stata verificata), nel formato DateTime XMLSchema.||

|Tipo di autenticazione|URI emesso nell'attestazione "AuthenticationMethod"|
|-|-|
|Password|`urn:oasis:names:tc:SAML:1.0:am:password`|
|Kerberos|`urn:ietf:rfc:1510`|
|SecureRemotePassword|`urn:ietf:rfc:2945`|
|TLSClient|`urn:ietf:rfc:2246`|
|X509|`urn:oasis:names:tc:SAML:1.0:am:X509-PKI`|
|PGP|`urn:oasis:names:tc:SAML:1.0:am:PGP`|
|Spki|`urn:oasis:names:tc:SAML:1.0:am:SPKI`|
|XmlDSig|`urn:ietf:rfc:3075`|
|Non specificato|`urn:oasis:names:tc:SAML:1.0:am:unspecified`|
