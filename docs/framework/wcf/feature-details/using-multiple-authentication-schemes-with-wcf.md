---
title: Uso di vari schemi di autenticazione con WCF
ms.date: 03/30/2017
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
ms.openlocfilehash: 1874963573a6ec12939bd12b79574f1e2c889bfd
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600218"
---
# <a name="using-multiple-authentication-schemes-with-wcf"></a>Uso di vari schemi di autenticazione con WCF
Con WCF è ora possibile specificare più schemi di autenticazione in un singolo endpoint. Inoltre, i servizi ospitati dal Web possono ereditare le relative impostazioni di autenticazione direttamente da IIS. Nei servizi self-hosted è possibile specificare gli schemi di autenticazione da usare. Per ulteriori informazioni sull'impostazione delle impostazioni di autenticazione in IIS, vedere [autenticazione IIS](https://go.microsoft.com/fwlink/?LinkId=232458)  
  
## <a name="iis-hosted-services"></a>Servizi ospitati da IIS  
 Per i servizi ospitati da IIS, impostare gli schemi di autenticazione che si desidera usare in IIS. Quindi, nel file Web. config del servizio, nella configurazione dell'associazione specificare il tipo clientCredential come "InheritedFromHost", come illustrato nel frammento di codice XML seguente:  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 È possibile specificare che si desidera utilizzare solo un subset di schemi di autenticazione con il servizio utilizzando oggetto ServiceAuthenticationBehavior o l' \<serviceAuthenticationManager> elemento. Quando si configura questo tipo di codice, usare l'oggetto ServiceAuthenticationBehavior come illustrato nel seguente frammento di codice.  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 Quando si configura questa impostazione in un file di configurazione, usare l' \<serviceAuthenticationManager> elemento, come illustrato nel frammento di codice XML seguente.  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 In questo modo verrà considerato un solo subset degli schemi di autenticazione qui elencati per l'applicazione nell'endpoint del servizio, in base a quanto selezionato in IIS. Pertanto, uno sviluppatore può escludere, ad esempio, l'autenticazione di base dall'elenco omettendola dall'elenco serviceAuthenticationManager e, anche se abilitata in IIS, non verrà applicata nell'endpoint del servizio.  
  
## <a name="self-hosted-services"></a>Servizi self-hosted  
 I servizi self-hosted vengono configurati in modo leggermente diverso dal momento che non esiste alcuna applicazione IIS da cui ereditare le impostazioni. Qui si usa l' \<serviceAuthenticationManager> elemento o oggetto ServiceAuthenticationBehavior per specificare le impostazioni di autenticazione che verranno ereditate. Nel codice l'aspetto è simile al seguente:  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 Nella configurazione l'aspetto è simile al seguente:  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 Quindi è possibile specificare InheritFromHost nelle impostazioni di associazione come illustrato nel seguente frammento XML.  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 In alternativa, è possibile specificare gli schemi di autenticazione in un'associazione personalizzata, impostando gli schemi di autenticazione sull'elemento di associazione del trasporto HTTP, come illustrato nel seguente frammento di configurazione.  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Associazioni e protezione](bindings-and-security.md)
- [Endpoint: indirizzi, associazioni e contratti](endpoints-addresses-bindings-and-contracts.md)
- [Configurazione di associazioni fornite dal sistema](configuring-system-provided-bindings.md)
- [Funzionalità di sicurezza con associazioni personalizzate](security-capabilities-with-custom-bindings.md)
- [Binding](bindings.md)
- [Associazioni personalizzate](../extending/custom-bindings.md)
