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
ms.openlocfilehash: cf74b38c15cf8dc68218c39246c8999c4ec44493
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="using-multiple-authentication-schemes-with-wcf"></a><span data-ttu-id="19b88-102">Uso di vari schemi di autenticazione con WCF</span><span class="sxs-lookup"><span data-stu-id="19b88-102">Using Multiple Authentication Schemes with WCF</span></span>
<span data-ttu-id="19b88-103">Con WCF è ora possibile specificare più schemi di autenticazione in un singolo endpoint.</span><span class="sxs-lookup"><span data-stu-id="19b88-103">WCF now allows you to specify multiple authentication schemes on a single endpoint.</span></span> <span data-ttu-id="19b88-104">Inoltre, i servizi ospitati dal Web possono ereditare le relative impostazioni di autenticazione direttamente da IIS.</span><span class="sxs-lookup"><span data-stu-id="19b88-104">Furthermore web hosted services can inherit their authentication settings directly from IIS.</span></span> <span data-ttu-id="19b88-105">Nei servizi self-hosted è possibile specificare gli schemi di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="19b88-105">Self-hosted services can specify what authentication schemes can be used.</span></span> <span data-ttu-id="19b88-106">Per ulteriori informazioni sulla configurazione delle impostazioni di autenticazione in IIS, vedere [autenticazione IIS](http://go.microsoft.com/fwlink/?LinkId=232458)</span><span class="sxs-lookup"><span data-stu-id="19b88-106">For more information about setting authentication settings in IIS, see [IIS Authentication](http://go.microsoft.com/fwlink/?LinkId=232458)</span></span>  
  
## <a name="iis-hosted-services"></a><span data-ttu-id="19b88-107">Servizi ospitati da IIS</span><span class="sxs-lookup"><span data-stu-id="19b88-107">IIS-Hosted Services</span></span>  
 <span data-ttu-id="19b88-108">Per i servizi ospitati da IIS, impostare gli schemi di autenticazione che si desidera usare in IIS.</span><span class="sxs-lookup"><span data-stu-id="19b88-108">For IIS-hosted services, set the authentication schemes you wish to use in IIS.</span></span> <span data-ttu-id="19b88-109">Nel file Web. config del servizio, nella configurazione dell'associazione specificare il tipo clientCredential come "InheritedFromHost" come mostrato nel frammento XML seguente:</span><span class="sxs-lookup"><span data-stu-id="19b88-109">Then in your service’s web.config file, in your binding configuration specify clientCredential type as "InheritedFromHost" as shown in the following XML snippet:</span></span>  
  
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
  
 <span data-ttu-id="19b88-110">È possibile specificare che si desidera solo un subset degli schemi di autenticazione da utilizzare con il servizio utilizzando l'oggetto ServiceAuthenticationBehavior o \<serviceAuthenticationManager > elemento.</span><span class="sxs-lookup"><span data-stu-id="19b88-110">You can specify that you only want a subset of authentication schemes to be used with your service using the ServiceAuthenticationBehavior or the \<serviceAuthenticationManager> element.</span></span> <span data-ttu-id="19b88-111">Quando si configura questo tipo di codice, usare l'oggetto ServiceAuthenticationBehavior come illustrato nel seguente frammento di codice.</span><span class="sxs-lookup"><span data-stu-id="19b88-111">When configuring this in code use the ServiceAuthenticationBehavior as shown in the following code snippet.</span></span>  
  
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
  
 <span data-ttu-id="19b88-112">Quando si applica questa configurazione in un file di configurazione, utilizzare il \<serviceAuthenticationManager > come illustrato nel seguente frammento XML.</span><span class="sxs-lookup"><span data-stu-id="19b88-112">When configuring this in a config file, use the \<serviceAuthenticationManager> element as shown in the following XML snippet.</span></span>  
  
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
  
 <span data-ttu-id="19b88-113">In questo modo verrà considerato un solo subset degli schemi di autenticazione qui elencati per l'applicazione nell'endpoint del servizio, in base a quanto selezionato in IIS.</span><span class="sxs-lookup"><span data-stu-id="19b88-113">This will ensure that only a subset of the authentication schemes listed here will be considered for applying on the service endpoint, depending on what is selected in the IIS.</span></span> <span data-ttu-id="19b88-114">Pertanto, uno sviluppatore può escludere, ad esempio, l'autenticazione di base dall'elenco omettendola dall'elenco serviceAuthenticationManager e, anche se abilitata in IIS, non verrà applicata nell'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="19b88-114">This means that a developer can exclude say Basic auth from the list by omitting it from the serviceAuthenticationManager listing and even if it is enabled in IIS, it will not be applied on the service endpoint</span></span>  
  
## <a name="self-hosted-services"></a><span data-ttu-id="19b88-115">Servizi self-hosted</span><span class="sxs-lookup"><span data-stu-id="19b88-115">Self-Hosted Services</span></span>  
 <span data-ttu-id="19b88-116">I servizi self-hosted vengono configurati in modo leggermente diverso dal momento che non esiste alcuna applicazione IIS da cui ereditare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="19b88-116">Self-hosted services are configured a bit differently since there is no IIS to inherit settings from.</span></span> <span data-ttu-id="19b88-117">Questo caso si usa il \<serviceAuthenticationManager > elemento o ServiceAuthenticationBehavior per specificare le impostazioni di autenticazione che verranno ereditate.</span><span class="sxs-lookup"><span data-stu-id="19b88-117">Here you use the \<serviceAuthenticationManager> element or ServiceAuthenticationBehavior to specify the authentication settings that will be inherited.</span></span> <span data-ttu-id="19b88-118">Nel codice l'aspetto è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="19b88-118">In code it looks like this:</span></span>  
  
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
  
 <span data-ttu-id="19b88-119">Nella configurazione l'aspetto è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="19b88-119">In config, it looks like this:</span></span>  
  
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
  
 <span data-ttu-id="19b88-120">Quindi è possibile specificare InheritFromHost nelle impostazioni di binding come illustrato nel seguente frammento XML.</span><span class="sxs-lookup"><span data-stu-id="19b88-120">And then you can specify InheritFromHost in your binding settings as shown in the following XML snippet.</span></span>  
  
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
  
 <span data-ttu-id="19b88-121">In alternativa, è possibile specificare gli schemi di autenticazione in un'associazione personalizzata, impostando gli schemi di autenticazione sull'elemento di associazione del trasporto HTTP, come illustrato nel seguente frammento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="19b88-121">Alternatively, you can specify the authentication schemes in a custom binding, by setting the authentication schemes on the HTTP transport binding element, as shown in the following config snippet.</span></span>  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="19b88-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19b88-122">See Also</span></span>  
 [<span data-ttu-id="19b88-123">Associazioni e protezione</span><span class="sxs-lookup"><span data-stu-id="19b88-123">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 [<span data-ttu-id="19b88-124">Endpoint: Indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="19b88-124">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [<span data-ttu-id="19b88-125">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="19b88-125">Configuring System-Provided Bindings</span></span>](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="19b88-126">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="19b88-126">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="19b88-127">Associazioni</span><span class="sxs-lookup"><span data-stu-id="19b88-127">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [<span data-ttu-id="19b88-128">Associazioni</span><span class="sxs-lookup"><span data-stu-id="19b88-128">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [<span data-ttu-id="19b88-129">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="19b88-129">Custom Bindings</span></span>](../../../../docs/framework/wcf/extending/custom-bindings.md)
