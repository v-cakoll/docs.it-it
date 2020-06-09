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
# <a name="using-multiple-authentication-schemes-with-wcf"></a><span data-ttu-id="d60a8-102">Uso di vari schemi di autenticazione con WCF</span><span class="sxs-lookup"><span data-stu-id="d60a8-102">Using Multiple Authentication Schemes with WCF</span></span>
<span data-ttu-id="d60a8-103">Con WCF è ora possibile specificare più schemi di autenticazione in un singolo endpoint.</span><span class="sxs-lookup"><span data-stu-id="d60a8-103">WCF now allows you to specify multiple authentication schemes on a single endpoint.</span></span> <span data-ttu-id="d60a8-104">Inoltre, i servizi ospitati dal Web possono ereditare le relative impostazioni di autenticazione direttamente da IIS.</span><span class="sxs-lookup"><span data-stu-id="d60a8-104">Furthermore web hosted services can inherit their authentication settings directly from IIS.</span></span> <span data-ttu-id="d60a8-105">Nei servizi self-hosted è possibile specificare gli schemi di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="d60a8-105">Self-hosted services can specify what authentication schemes can be used.</span></span> <span data-ttu-id="d60a8-106">Per ulteriori informazioni sull'impostazione delle impostazioni di autenticazione in IIS, vedere [autenticazione IIS](https://go.microsoft.com/fwlink/?LinkId=232458)</span><span class="sxs-lookup"><span data-stu-id="d60a8-106">For more information about setting authentication settings in IIS, see [IIS Authentication](https://go.microsoft.com/fwlink/?LinkId=232458)</span></span>  
  
## <a name="iis-hosted-services"></a><span data-ttu-id="d60a8-107">Servizi ospitati da IIS</span><span class="sxs-lookup"><span data-stu-id="d60a8-107">IIS-Hosted Services</span></span>  
 <span data-ttu-id="d60a8-108">Per i servizi ospitati da IIS, impostare gli schemi di autenticazione che si desidera usare in IIS.</span><span class="sxs-lookup"><span data-stu-id="d60a8-108">For IIS-hosted services, set the authentication schemes you wish to use in IIS.</span></span> <span data-ttu-id="d60a8-109">Quindi, nel file Web. config del servizio, nella configurazione dell'associazione specificare il tipo clientCredential come "InheritedFromHost", come illustrato nel frammento di codice XML seguente:</span><span class="sxs-lookup"><span data-stu-id="d60a8-109">Then in your service’s web.config file, in your binding configuration specify clientCredential type as "InheritedFromHost" as shown in the following XML snippet:</span></span>  
  
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
  
 <span data-ttu-id="d60a8-110">È possibile specificare che si desidera utilizzare solo un subset di schemi di autenticazione con il servizio utilizzando oggetto ServiceAuthenticationBehavior o l' \<serviceAuthenticationManager> elemento.</span><span class="sxs-lookup"><span data-stu-id="d60a8-110">You can specify that you only want a subset of authentication schemes to be used with your service using the ServiceAuthenticationBehavior or the \<serviceAuthenticationManager> element.</span></span> <span data-ttu-id="d60a8-111">Quando si configura questo tipo di codice, usare l'oggetto ServiceAuthenticationBehavior come illustrato nel seguente frammento di codice.</span><span class="sxs-lookup"><span data-stu-id="d60a8-111">When configuring this in code use the ServiceAuthenticationBehavior as shown in the following code snippet.</span></span>  
  
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
  
 <span data-ttu-id="d60a8-112">Quando si configura questa impostazione in un file di configurazione, usare l' \<serviceAuthenticationManager> elemento, come illustrato nel frammento di codice XML seguente.</span><span class="sxs-lookup"><span data-stu-id="d60a8-112">When configuring this in a config file, use the \<serviceAuthenticationManager> element as shown in the following XML snippet.</span></span>  
  
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
  
 <span data-ttu-id="d60a8-113">In questo modo verrà considerato un solo subset degli schemi di autenticazione qui elencati per l'applicazione nell'endpoint del servizio, in base a quanto selezionato in IIS.</span><span class="sxs-lookup"><span data-stu-id="d60a8-113">This will ensure that only a subset of the authentication schemes listed here will be considered for applying on the service endpoint, depending on what is selected in the IIS.</span></span> <span data-ttu-id="d60a8-114">Pertanto, uno sviluppatore può escludere, ad esempio, l'autenticazione di base dall'elenco omettendola dall'elenco serviceAuthenticationManager e, anche se abilitata in IIS, non verrà applicata nell'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="d60a8-114">This means that a developer can exclude say Basic auth from the list by omitting it from the serviceAuthenticationManager listing and even if it is enabled in IIS, it will not be applied on the service endpoint</span></span>  
  
## <a name="self-hosted-services"></a><span data-ttu-id="d60a8-115">Servizi self-hosted</span><span class="sxs-lookup"><span data-stu-id="d60a8-115">Self-Hosted Services</span></span>  
 <span data-ttu-id="d60a8-116">I servizi self-hosted vengono configurati in modo leggermente diverso dal momento che non esiste alcuna applicazione IIS da cui ereditare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d60a8-116">Self-hosted services are configured a bit differently since there is no IIS to inherit settings from.</span></span> <span data-ttu-id="d60a8-117">Qui si usa l' \<serviceAuthenticationManager> elemento o oggetto ServiceAuthenticationBehavior per specificare le impostazioni di autenticazione che verranno ereditate.</span><span class="sxs-lookup"><span data-stu-id="d60a8-117">Here you use the \<serviceAuthenticationManager> element or ServiceAuthenticationBehavior to specify the authentication settings that will be inherited.</span></span> <span data-ttu-id="d60a8-118">Nel codice l'aspetto è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d60a8-118">In code it looks like this:</span></span>  
  
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
  
 <span data-ttu-id="d60a8-119">Nella configurazione l'aspetto è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d60a8-119">In config, it looks like this:</span></span>  
  
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
  
 <span data-ttu-id="d60a8-120">Quindi è possibile specificare InheritFromHost nelle impostazioni di associazione come illustrato nel seguente frammento XML.</span><span class="sxs-lookup"><span data-stu-id="d60a8-120">And then you can specify InheritFromHost in your binding settings as shown in the following XML snippet.</span></span>  
  
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
  
 <span data-ttu-id="d60a8-121">In alternativa, è possibile specificare gli schemi di autenticazione in un'associazione personalizzata, impostando gli schemi di autenticazione sull'elemento di associazione del trasporto HTTP, come illustrato nel seguente frammento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d60a8-121">Alternatively, you can specify the authentication schemes in a custom binding, by setting the authentication schemes on the HTTP transport binding element, as shown in the following config snippet.</span></span>  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d60a8-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d60a8-122">See also</span></span>

- [<span data-ttu-id="d60a8-123">Associazioni e protezione</span><span class="sxs-lookup"><span data-stu-id="d60a8-123">Bindings and Security</span></span>](bindings-and-security.md)
- [<span data-ttu-id="d60a8-124">Endpoint: indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="d60a8-124">Endpoints: Addresses, Bindings, and Contracts</span></span>](endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="d60a8-125">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="d60a8-125">Configuring System-Provided Bindings</span></span>](configuring-system-provided-bindings.md)
- [<span data-ttu-id="d60a8-126">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="d60a8-126">Security Capabilities with Custom Bindings</span></span>](security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="d60a8-127">Binding</span><span class="sxs-lookup"><span data-stu-id="d60a8-127">Bindings</span></span>](bindings.md)
- [<span data-ttu-id="d60a8-128">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="d60a8-128">Custom Bindings</span></span>](../extending/custom-bindings.md)
