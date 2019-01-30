---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: bb4cb5178885b90ef25ee827c2f11593ead6e73d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55276679"
---
# <a name="trustedissuers"></a><span data-ttu-id="31a6c-101">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="31a6c-101">\<trustedIssuers></span></span>
<span data-ttu-id="31a6c-102">Consente di configurare l'elenco dei certificati dell'autorità emittente attendibile usato per il registro dei nomi basato sulla configurazione dell'autorità di certificazione (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span><span class="sxs-lookup"><span data-stu-id="31a6c-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="31a6c-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="31a6c-103">\<system.identityModel></span></span>  
<span data-ttu-id="31a6c-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="31a6c-104">\<identityConfiguration></span></span>  
<span data-ttu-id="31a6c-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="31a6c-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="31a6c-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="31a6c-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="31a6c-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="31a6c-107">\<issuerNameRegistry></span></span>  
<span data-ttu-id="31a6c-108">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="31a6c-108">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31a6c-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31a6c-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31a6c-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="31a6c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="31a6c-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="31a6c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31a6c-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="31a6c-112">Attributes</span></span>  
 <span data-ttu-id="31a6c-113">nessuno</span><span class="sxs-lookup"><span data-stu-id="31a6c-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="31a6c-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="31a6c-114">Child Elements</span></span>  
  
|<span data-ttu-id="31a6c-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="31a6c-115">Element</span></span>|<span data-ttu-id="31a6c-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31a6c-116">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="31a6c-117">Aggiunge un certificato per la raccolta di autorità emittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="31a6c-117">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="31a6c-118">Il certificato è specificato con il `thumbprint` attributo.</span><span class="sxs-lookup"><span data-stu-id="31a6c-118">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="31a6c-119">Questo attributo è obbligatorio e deve contenere il form codificato ASN.1 dell'identificazione digitale del certificato.</span><span class="sxs-lookup"><span data-stu-id="31a6c-119">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="31a6c-120">Il `name` attributo è facoltativo e può essere utilizzato per specificare un nome descrittivo per il certificato.</span><span class="sxs-lookup"><span data-stu-id="31a6c-120">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="31a6c-121">Cancella tutti i certificati dalla raccolta di autorità emittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="31a6c-121">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="31a6c-122">Rimuove un certificato dalla raccolta di autorità emittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="31a6c-122">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="31a6c-123">Il certificato è specificato con il `thumbprint` attributo.</span><span class="sxs-lookup"><span data-stu-id="31a6c-123">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="31a6c-124">Questo attributo è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="31a6c-124">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="31a6c-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="31a6c-125">Parent Elements</span></span>  
  
|<span data-ttu-id="31a6c-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="31a6c-126">Element</span></span>|<span data-ttu-id="31a6c-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31a6c-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31a6c-128">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="31a6c-128">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="31a6c-129">Configura il registro dei nomi dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="31a6c-129">Configures the issuer name registry.</span></span> <span data-ttu-id="31a6c-130">**Importante:**  Il `type` attributo del `<issuerNameRegistry>` deve fare riferimento a elemento le <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe per il `<trustedIssuers>` elemento sia valido.</span><span class="sxs-lookup"><span data-stu-id="31a6c-130">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31a6c-131">Note</span><span class="sxs-lookup"><span data-stu-id="31a6c-131">Remarks</span></span>  
 <span data-ttu-id="31a6c-132">Windows Identity Foundation (WIF) fornisce un'implementazione singola del <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe per impostazione predefinita, il <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe.</span><span class="sxs-lookup"><span data-stu-id="31a6c-132">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="31a6c-133">Il Registro di sistema configurazione nome dell'autorità emittente mantiene un elenco di autorità emittenti attendibili che viene caricato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="31a6c-133">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="31a6c-134">L'elenco associa ogni nome dell'autorità emittente con il certificato X.509 che è necessario per verificare la firma dei token prodotti dall'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="31a6c-134">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="31a6c-135">L'elenco dei certificati di autorità emittenti attendibili viene specificato sotto il `<trustedIssuers>` elemento.</span><span class="sxs-lookup"><span data-stu-id="31a6c-135">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="31a6c-136">Ogni elemento nell'elenco associa un nome dell'autorità di certificazione tasti di scelta rapida con il certificato X.509 che è necessario per verificare la firma dei token prodotti dall'autorità emittente in questione.</span><span class="sxs-lookup"><span data-stu-id="31a6c-136">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="31a6c-137">Attendibili i certificati vengono specificati usando il ASN.1 formato dell'identificazione digitale del certificato con codifica e vengono aggiunti insieme tramite `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="31a6c-137">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="31a6c-138">È possibile cancellare o rimuovere autorità emittenti (certificati) dall'elenco utilizzando il `<clear>` e `<remove>` elementi.</span><span class="sxs-lookup"><span data-stu-id="31a6c-138">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="31a6c-139">Il `type` attributo del `<issuerNameRegistry>` deve fare riferimento a elemento le <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe per il `<trustedIssuers>` elemento sia valido.</span><span class="sxs-lookup"><span data-stu-id="31a6c-139">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31a6c-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="31a6c-140">Example</span></span>  
 <span data-ttu-id="31a6c-141">Il codice XML seguente viene illustrato come specificare l'autorità di certificazione di base di configurazione del registro dei nomi.</span><span class="sxs-lookup"><span data-stu-id="31a6c-141">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="31a6c-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31a6c-142">See also</span></span>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
