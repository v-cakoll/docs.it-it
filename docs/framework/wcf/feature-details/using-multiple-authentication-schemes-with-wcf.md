---
title: Uso di vari schemi di autenticazione con WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e570185b7df06a47e8c7fb3319328e760079415d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="using-multiple-authentication-schemes-with-wcf"></a>Uso di vari schemi di autenticazione con WCF
Con WCF è ora possibile specificare più schemi di autenticazione in un singolo endpoint. Inoltre, i servizi ospitati dal Web possono ereditare le relative impostazioni di autenticazione direttamente da IIS. Nei servizi self-hosted è possibile specificare gli schemi di autenticazione da usare. Per ulteriori informazioni sulla configurazione delle impostazioni di autenticazione in IIS, vedere [autenticazione IIS](http://go.microsoft.com/fwlink/?LinkId=232458)  
  
## <a name="iis-hosted-services"></a>Servizi ospitati da IIS  
 Per i servizi ospitati da IIS, impostare gli schemi di autenticazione che si desidera usare in IIS. Nel file Web. config del servizio, nella configurazione dell'associazione specificare il tipo clientCredential come "InheritedFromHost" come mostrato nel frammento XML seguente:  
  
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
  
 È possibile specificare che si desidera solo un subset degli schemi di autenticazione da utilizzare con il servizio utilizzando l'oggetto ServiceAuthenticationBehavior o \<serviceAuthenticationManager > elemento. Quando si configura questo tipo di codice, usare l'oggetto ServiceAuthenticationBehavior come illustrato nel seguente frammento di codice.  
  
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
  
 Quando si applica questa configurazione in un file di configurazione, utilizzare il \<serviceAuthenticationManager > come illustrato nel seguente frammento XML.  
  
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
 I servizi self-hosted vengono configurati in modo leggermente diverso dal momento che non esiste alcuna applicazione IIS da cui ereditare le impostazioni. Questo caso si usa il \<serviceAuthenticationManager > elemento o ServiceAuthenticationBehavior per specificare le impostazioni di autenticazione che verranno ereditate. Nel codice l'aspetto è simile al seguente:  
  
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
  
 Quindi è possibile specificare InheritFromHost nelle impostazioni di binding come illustrato nel seguente frammento XML.  
  
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
 [Associazioni e sicurezza](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 [Endpoint: indirizzi, associazioni e contratti](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [Configurazione di associazioni fornite dal sistema](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Funzionalità di sicurezza con associazioni personalizzate](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [Associazioni](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [Associazioni](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [Associazioni personalizzate](../../../../docs/framework/wcf/extending/custom-bindings.md)
