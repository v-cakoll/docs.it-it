---
title: '&lt;trustedIssuers&gt;'
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: c390cecc265b27dfa8d9d0a892f5930c982f7054
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2018
ms.locfileid: "48261007"
---
# <a name="lttrustedissuersgt"></a><span data-ttu-id="c56d0-102">&lt;trustedIssuers&gt;</span><span class="sxs-lookup"><span data-stu-id="c56d0-102">&lt;trustedIssuers&gt;</span></span>
<span data-ttu-id="c56d0-103">Consente di configurare l'elenco dei certificati dell'autorità emittente attendibile usato per il registro dei nomi basato sulla configurazione dell'autorità di certificazione (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span><span class="sxs-lookup"><span data-stu-id="c56d0-103">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="c56d0-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="c56d0-104">\<system.identityModel></span></span>  
<span data-ttu-id="c56d0-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c56d0-105">\<identityConfiguration></span></span>  
<span data-ttu-id="c56d0-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="c56d0-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="c56d0-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="c56d0-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="c56d0-108">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="c56d0-108">\<issuerNameRegistry></span></span>  
<span data-ttu-id="c56d0-109">\<trustedIssuers ></span><span class="sxs-lookup"><span data-stu-id="c56d0-109">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c56d0-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c56d0-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c56d0-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c56d0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c56d0-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c56d0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c56d0-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="c56d0-113">Attributes</span></span>  
 <span data-ttu-id="c56d0-114">nessuno</span><span class="sxs-lookup"><span data-stu-id="c56d0-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c56d0-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c56d0-115">Child Elements</span></span>  
  
|<span data-ttu-id="c56d0-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="c56d0-116">Element</span></span>|<span data-ttu-id="c56d0-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c56d0-117">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="c56d0-118">Aggiunge un certificato per la raccolta di autorità emittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="c56d0-118">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="c56d0-119">Il certificato è specificato con il `thumbprint` attributo.</span><span class="sxs-lookup"><span data-stu-id="c56d0-119">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="c56d0-120">Questo attributo è obbligatorio e deve contenere il form codificato ASN.1 dell'identificazione digitale del certificato.</span><span class="sxs-lookup"><span data-stu-id="c56d0-120">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="c56d0-121">Il `name` attributo è facoltativo e può essere utilizzato per specificare un nome descrittivo per il certificato.</span><span class="sxs-lookup"><span data-stu-id="c56d0-121">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="c56d0-122">Cancella tutti i certificati dalla raccolta di autorità emittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="c56d0-122">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="c56d0-123">Rimuove un certificato dalla raccolta di autorità emittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="c56d0-123">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="c56d0-124">Il certificato è specificato con il `thumbprint` attributo.</span><span class="sxs-lookup"><span data-stu-id="c56d0-124">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="c56d0-125">Questo attributo è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c56d0-125">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c56d0-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c56d0-126">Parent Elements</span></span>  
  
|<span data-ttu-id="c56d0-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="c56d0-127">Element</span></span>|<span data-ttu-id="c56d0-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c56d0-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c56d0-129">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="c56d0-129">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="c56d0-130">Configura il registro dei nomi dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="c56d0-130">Configures the issuer name registry.</span></span> <span data-ttu-id="c56d0-131">**Importante:** il `type` attributo del `<issuerNameRegistry>` deve fare riferimento a elemento di <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe per il `<trustedIssuers>` elemento sia valido.</span><span class="sxs-lookup"><span data-stu-id="c56d0-131">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c56d0-132">Note</span><span class="sxs-lookup"><span data-stu-id="c56d0-132">Remarks</span></span>  
 <span data-ttu-id="c56d0-133">Windows Identity Foundation (WIF) fornisce un'implementazione singola del <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe per impostazione predefinita, il <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe.</span><span class="sxs-lookup"><span data-stu-id="c56d0-133">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="c56d0-134">Il Registro di sistema configurazione nome dell'autorità emittente mantiene un elenco di autorità emittenti attendibili che viene caricato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="c56d0-134">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="c56d0-135">L'elenco associa ogni nome dell'autorità emittente con il certificato X.509 che è necessario per verificare la firma dei token prodotti dall'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="c56d0-135">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="c56d0-136">L'elenco dei certificati di autorità emittenti attendibili viene specificato sotto il `<trustedIssuers>` elemento.</span><span class="sxs-lookup"><span data-stu-id="c56d0-136">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="c56d0-137">Ogni elemento nell'elenco associa un nome dell'autorità di certificazione tasti di scelta rapida con il certificato X.509 che è necessario per verificare la firma dei token prodotti dall'autorità emittente in questione.</span><span class="sxs-lookup"><span data-stu-id="c56d0-137">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="c56d0-138">Attendibili i certificati vengono specificati usando il ASN.1 formato dell'identificazione digitale del certificato con codifica e vengono aggiunti insieme tramite `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="c56d0-138">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="c56d0-139">È possibile cancellare o rimuovere autorità emittenti (certificati) dall'elenco utilizzando il `<clear>` e `<remove>` elementi.</span><span class="sxs-lookup"><span data-stu-id="c56d0-139">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="c56d0-140">Il `type` attributo del `<issuerNameRegistry>` deve fare riferimento a elemento le <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe per il `<trustedIssuers>` elemento sia valido.</span><span class="sxs-lookup"><span data-stu-id="c56d0-140">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c56d0-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="c56d0-141">Example</span></span>  
 <span data-ttu-id="c56d0-142">Il codice XML seguente viene illustrato come specificare l'autorità di certificazione di base di configurazione del registro dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c56d0-142">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c56d0-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c56d0-143">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
