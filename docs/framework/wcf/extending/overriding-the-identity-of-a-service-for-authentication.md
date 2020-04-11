---
title: Override dell'identità di un servizio per l'autenticazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d613a22b-07d7-41a4-bada-1adc653b9b5d
ms.openlocfilehash: e7273c1e140e52eb37a30b6cabeb9e9a83a6fa2d
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121563"
---
# <a name="override-the-identity-of-a-service-for-authentication"></a>Eseguire l'override dell'identità di un servizio per l'autenticazioneOverride the identity of a service for authentication

In genere non è necessario impostare l'identità in un servizio, perché la selezione del tipo di credenziale di un client impone il tipo di identità esposto nei metadati del servizio. Ad esempio, il codice di configurazione seguente usa l'elemento [ \<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) e imposta l'attributo su Windows.For example, the following configuration code uses the wsHttpBinding>element and sets the `clientCredentialType` attribute to Windows.  

 Nel frammento WSDL (Web Services Description Language) viene mostrata l'identità dell'endpoint precedentemente definito. In questo esempio, il servizio viene eseguito come servizio self-hosted con un particolare account utente (username@contoso.com) e pertanto l'identità del nome dell'entità utente (UPN) contiene il nome dell'account. L'UPN è anche noto anche come nome di accesso dell'utente in un dominio Windows.  

 Per un'applicazione di esempio che illustri l'impostazione dell'identità, vedere Esempio di [identità del servizio](../samples/service-identity-sample.md). Per ulteriori informazioni sull'identità del servizio, vedere [Autenticazione e identità del servizio](../feature-details/service-identity-and-authentication.md).  
  
## <a name="kerberos-authentication-and-identity"></a>Autenticazione Kerberos e identità  
 Per impostazione predefinita, quando un servizio è [ \<](../../configure-apps/file-schema/wcf/identity.md) configurato per l'utilizzo di una credenziale di Windows, nel file WSDL viene generato un elemento identity>contenente un [ \<elemento userPrincipalName>](../../configure-apps/file-schema/wcf/userprincipalname.md) o [ \<servicePrincipalName>.](../../configure-apps/file-schema/wcf/serviceprincipalname.md) Se il servizio è `LocalSystem` `LocalService`in `NetworkService` esecuzione con l'account , o account, viene `host/` \<generato un nome dell'entità servizio (SPN) per impostazione predefinita sotto forma di *nome host*> perché tali account hanno accesso ai dati SPN del computer. Se il servizio viene eseguito con un account diverso, Windows Communication \<Foundation (WCF) genera un UPN sotto forma di *nome utente nomedominio*>@<*domainName*`>`. Questo si verifica perché l'autenticazione Kerberos richiede che venga fornito un UPN o un SPN al client per l'autenticazione del servizio.  
  
 È inoltre possibile utilizzare lo strumento [Setspn](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731241(v=ws.10)?redirectedfrom=MSDN) per registrare un nome SPN aggiuntivo con l'account di un servizio in un dominio. È quindi possibile usare il nome SPN come identità del servizio. Per ulteriori informazioni sullo strumento, vedere [Cenni preliminari](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10))su Setspn .  
  
> [!NOTE]
> Per usare il tipo di credenziale di Windows senza negoziazione, l'account utente del servizio deve avere accesso al nome SPN registrato con il dominio Active Directory. È possibile eseguire questa operazione nei modi seguenti:  
  
- Usare l'account NetworkService o LocalSystem per eseguire il servizio. Poiché tali account hanno accesso al nome SPN del computer che viene stabilito quando il computer viene aggiunto al dominio di Active Directory, WCF genera automaticamente l'elemento SPN appropriato all'interno dell'endpoint del servizio nei metadati del servizio (WSDL).  
  
- Usare un account di dominio Active Directory arbitrario per eseguire il servizio. In questo caso, stabilire un SPN per l'account di dominio, eventualmente usando l'utilità Setspn.exe. Dopo aver creato il nome SPN per l'account del servizio, configurare WCF per pubblicare tale nome SPN per i client del servizio tramite i relativi metadati (WSDL). Questa operazione viene eseguita impostando l'identità dell'endpoint esposto tramite un file di configurazione dell'applicazione o tramite codice.  
  
 Per ulteriori informazioni sui nomi SPN, il protocollo Kerberos e Active Directory, vedere [Supplemento tecnico Kerberos per Windows.](https://docs.microsoft.com/previous-versions/msp-n-p/ff649429(v=pandp.10))  
  
### <a name="when-spn-or-upn-equals-the-empty-string"></a>SPN o UPN corrispondente a una stringa vuota  
 Se si imposta il nome SPN o UPN come stringa vuota si verificano diverse cose, a seconda del livello di sicurezza e della modalità di autenticazione usati:  
  
- Se si sta usando la protezione del trasporto, viene scelta l'autenticazione NT LanMan (NTLM).  
  
- Se si sta usando la protezione dei messaggi, l'autenticazione potrebbe non riuscire, a seconda della modalità scelta:  
  
- Se si sta usando la modalità `spnego` e l'attributo `AllowNtlm` è impostato su `false`, l'autenticazione avrà esito negativo.  
  
- Se si sta usando la modalità `spnego` e l'attributo `AllowNtlm` è impostato su `true`, l'autenticazione avrà esito negativo se l'UPN è vuoto, ma avrà esito positivo se l'SPN è vuoto.  
  
- Se si sta usando la modalità Kerberos diretta, nota anche come "monofase", l'autenticazione avrà esito negativo.  
  
### <a name="using-the-identity-element-in-configuration"></a>Utilizzo \<dell'elemento identity> nella configurazioneUsing the identity> Element in Configuration  
 Se si imposta su Certificate il tipo di credenziale client nell'associazione descritta in precedenza`,` il codice WSDL generato conterrà un certificato X.509 con serializzazione Base64 per il valore dell'identità, come illustrato nel codice seguente. Si tratta dell'impostazione predefinita per tutti i tipi di credenziale client diversi da Windows.  

 È possibile modificare il valore dell'identità del servizio predefinito `identity` o modificare il tipo di identità utilizzando l'elemento> <nella configurazione o impostando l'identità nel codice. Nel codice di configurazione seguente viene impostata un'identità DNS (Domain Name System) con il valore `contoso.com`.  

### <a name="setting-identity-programmatically"></a>Impostazione dell'identità a livello di programmazione  
 Il servizio non è necessario specificare in modo esplicito un'identità, perché WCF la determina automaticamente. Tuttavia, WCF consente di specificare un'identità in un endpoint, se necessario. Nel codice seguente viene aggiunto un nuovo endpoint di servizio con un'identità DNS specifica.  
  
 [!code-csharp[C_Identity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#5)]
 [!code-vb[C_Identity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#5)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: creare un verificatore di identità client personalizzato](how-to-create-a-custom-client-identity-verifier.md)
- [Identità del servizio e autenticazione](../feature-details/service-identity-and-authentication.md)
