---
title: '&lt;trustedIssuers&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 33ef3ca88462595d81d269a92a643b43c9aea025
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lttrustedissuersgt"></a><span data-ttu-id="76830-102">&lt;trustedIssuers&gt;</span><span class="sxs-lookup"><span data-stu-id="76830-102">&lt;trustedIssuers&gt;</span></span>
<span data-ttu-id="76830-103">Consente di configurare l'elenco di certificati di autorità emittenti attendibili utilizzati dal Registro di sistema di nome dell'autorità di certificazione basata sulla configurazione (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span><span class="sxs-lookup"><span data-stu-id="76830-103">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="76830-104">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="76830-104">\<system.identityModel></span></span>  
<span data-ttu-id="76830-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="76830-105">\<identityConfiguration></span></span>  
<span data-ttu-id="76830-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="76830-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="76830-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="76830-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="76830-108">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="76830-108">\<issuerNameRegistry></span></span>  
<span data-ttu-id="76830-109">\<trustedIssuers ></span><span class="sxs-lookup"><span data-stu-id="76830-109">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76830-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="76830-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76830-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="76830-111">Attributes and Elements</span></span>  
 <span data-ttu-id="76830-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="76830-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76830-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="76830-113">Attributes</span></span>  
 <span data-ttu-id="76830-114">Nessuna</span><span class="sxs-lookup"><span data-stu-id="76830-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="76830-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="76830-115">Child Elements</span></span>  
  
|<span data-ttu-id="76830-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="76830-116">Element</span></span>|<span data-ttu-id="76830-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76830-117">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="76830-118">Aggiunge un certificato per la raccolta di autorità emittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="76830-118">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="76830-119">Il certificato è specificato con il `thumbprint` attributo.</span><span class="sxs-lookup"><span data-stu-id="76830-119">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="76830-120">Questo attributo è obbligatorio e deve contenere il modulo ASN. 1 codificata dell'identificazione digitale del certificato.</span><span class="sxs-lookup"><span data-stu-id="76830-120">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="76830-121">Il `name` attributo è facoltativo e può essere utilizzato per specificare un nome descrittivo per il certificato.</span><span class="sxs-lookup"><span data-stu-id="76830-121">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="76830-122">Cancella tutti i certificati dalla raccolta di autorità emittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="76830-122">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="76830-123">Rimuove un certificato dalla raccolta di autorità emittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="76830-123">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="76830-124">Il certificato è specificato con il `thumbprint` attributo.</span><span class="sxs-lookup"><span data-stu-id="76830-124">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="76830-125">Questo attributo è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="76830-125">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="76830-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="76830-126">Parent Elements</span></span>  
  
|<span data-ttu-id="76830-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="76830-127">Element</span></span>|<span data-ttu-id="76830-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76830-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76830-129">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="76830-129">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="76830-130">Consente di configurare il Registro di sistema di nome dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="76830-130">Configures the issuer name registry.</span></span> <span data-ttu-id="76830-131">**Importante:** il `type` attributo del `<issuerNameRegistry>` deve fare riferimento a elemento di <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe per il `<trustedIssuers>` elemento sia valido.</span><span class="sxs-lookup"><span data-stu-id="76830-131">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76830-132">Note</span><span class="sxs-lookup"><span data-stu-id="76830-132">Remarks</span></span>  
 <span data-ttu-id="76830-133">Windows Identity Foundation (WIF) fornisce un'implementazione singola del <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe predefinita, la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe.</span><span class="sxs-lookup"><span data-stu-id="76830-133">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="76830-134">Il Registro di sistema di configurazione dell'autorità di certificazione nome gestisce un elenco di autorità emittenti attendibili che viene caricato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="76830-134">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="76830-135">Nell'elenco, ciascun nome dell'autorità emittente associato il certificato x. 509 che è necessaria per verificare la firma dei prodotti dall'emittente del token.</span><span class="sxs-lookup"><span data-stu-id="76830-135">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="76830-136">L'elenco di certificati di autorità emittenti attendibili viene specificato sotto il `<trustedIssuers>` elemento.</span><span class="sxs-lookup"><span data-stu-id="76830-136">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="76830-137">Ogni elemento nell'elenco associa un nome di tasto di scelta dell'autorità emittente con il certificato x. 509 che è necessario verificare la firma di token generato da tale autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="76830-137">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="76830-138">Certificati trusted vengono specificati utilizzando l'ASN. 1 formato dell'identificazione digitale del certificato con codifica e vengono aggiunti insieme utilizzando `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="76830-138">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="76830-139">È possibile cancellare o rimuovere gli emittenti (certificati) dall'elenco utilizzando il `<clear>` e `<remove>` elementi.</span><span class="sxs-lookup"><span data-stu-id="76830-139">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="76830-140">Il `type` attributo del `<issuerNameRegistry>` deve fare riferimento a elemento di <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe per il `<trustedIssuers>` elemento sia valido.</span><span class="sxs-lookup"><span data-stu-id="76830-140">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76830-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="76830-141">Example</span></span>  
 <span data-ttu-id="76830-142">Il codice XML seguente viene illustrato come specificare l'autorità emittente di base di configurazione del Registro di sistema di nome.</span><span class="sxs-lookup"><span data-stu-id="76830-142">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="76830-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76830-143">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
