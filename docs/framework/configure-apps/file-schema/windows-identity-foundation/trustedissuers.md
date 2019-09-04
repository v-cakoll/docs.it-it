---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 50fc7194823fb0c5c426fb54ffd50b17c3714ed9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251751"
---
# <a name="trustedissuers"></a><span data-ttu-id="39c7d-101">\<> trustedIssuers</span><span class="sxs-lookup"><span data-stu-id="39c7d-101">\<trustedIssuers></span></span>
<span data-ttu-id="39c7d-102">Configura l'elenco dei certificati dell'autorità emittente attendibile usati dal registro di sistema del nome dell'autorità emittente<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>basata sulla configurazione ().</span><span class="sxs-lookup"><span data-stu-id="39c7d-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
<span data-ttu-id="39c7d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="39c7d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="39c7d-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="39c7d-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="39c7d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="39c7d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="39c7d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="39c7d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="39c7d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="39c7d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="39c7d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuerNameRegistry**](issuernameregistry.md)</span><span class="sxs-lookup"><span data-stu-id="39c7d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerNameRegistry>**](issuernameregistry.md)</span></span>\
<span data-ttu-id="39c7d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> trustedIssuers**</span><span class="sxs-lookup"><span data-stu-id="39c7d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trustedIssuers>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39c7d-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39c7d-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39c7d-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="39c7d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="39c7d-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="39c7d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39c7d-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="39c7d-113">Attributes</span></span>  
 <span data-ttu-id="39c7d-114">Nessuna</span><span class="sxs-lookup"><span data-stu-id="39c7d-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="39c7d-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="39c7d-115">Child Elements</span></span>  
  
|<span data-ttu-id="39c7d-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="39c7d-116">Element</span></span>|<span data-ttu-id="39c7d-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="39c7d-117">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="39c7d-118">Aggiunge un certificato alla raccolta di autorità emittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="39c7d-118">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="39c7d-119">Il certificato viene specificato con l' `thumbprint` attributo.</span><span class="sxs-lookup"><span data-stu-id="39c7d-119">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="39c7d-120">Questo attributo è obbligatorio e deve contenere il formato con codifica ASN. 1 dell'identificazione personale del certificato.</span><span class="sxs-lookup"><span data-stu-id="39c7d-120">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="39c7d-121">L' `name` attributo è facoltativo e può essere usato per specificare un nome descrittivo per il certificato.</span><span class="sxs-lookup"><span data-stu-id="39c7d-121">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="39c7d-122">Cancella tutti i certificati dalla raccolta di autorità emittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="39c7d-122">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="39c7d-123">Rimuove un certificato dalla raccolta di autorità emittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="39c7d-123">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="39c7d-124">Il certificato viene specificato con l' `thumbprint` attributo.</span><span class="sxs-lookup"><span data-stu-id="39c7d-124">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="39c7d-125">Questo attributo è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="39c7d-125">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39c7d-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="39c7d-126">Parent Elements</span></span>  
  
|<span data-ttu-id="39c7d-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="39c7d-127">Element</span></span>|<span data-ttu-id="39c7d-128">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="39c7d-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39c7d-129">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="39c7d-129">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="39c7d-130">Configura il registro dei nomi delle autorità emittenti.</span><span class="sxs-lookup"><span data-stu-id="39c7d-130">Configures the issuer name registry.</span></span> <span data-ttu-id="39c7d-131">**Importante:**  L' `type` attributo <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> `<trustedIssuers>` dell'elemento deve fare riferimento alla classe affinché l'elemento sia valido. `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="39c7d-131">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39c7d-132">Note</span><span class="sxs-lookup"><span data-stu-id="39c7d-132">Remarks</span></span>  
 <span data-ttu-id="39c7d-133">Windows Identity Foundation (WIF) fornisce una singola implementazione della <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe predefinita, la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe.</span><span class="sxs-lookup"><span data-stu-id="39c7d-133">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="39c7d-134">Il registro dei nomi delle autorità emittenti di configurazione mantiene un elenco di autorità emittenti attendibili caricate dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="39c7d-134">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="39c7d-135">L'elenco associa ogni nome dell'autorità emittente al certificato X. 509 necessario per verificare la firma dei token prodotti dall'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="39c7d-135">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="39c7d-136">L'elenco dei certificati dell'autorità emittente attendibile viene specificato `<trustedIssuers>` nell'elemento.</span><span class="sxs-lookup"><span data-stu-id="39c7d-136">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="39c7d-137">Ogni elemento nell'elenco associa il nome di un emittente mnemonico al certificato X. 509 necessario per verificare la firma dei token prodotti dall'emittente.</span><span class="sxs-lookup"><span data-stu-id="39c7d-137">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="39c7d-138">I certificati attendibili vengono specificati utilizzando il formato con codifica ASN. 1 dell'identificazione personale del certificato e vengono aggiunti alla raccolta `<add>` tramite l'elemento.</span><span class="sxs-lookup"><span data-stu-id="39c7d-138">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="39c7d-139">È possibile cancellare o rimuovere autorità emittenti (certificati) dall'elenco usando gli `<clear>` elementi e. `<remove>`</span><span class="sxs-lookup"><span data-stu-id="39c7d-139">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="39c7d-140">L' `type` attributo <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> `<trustedIssuers>` dell'elemento deve fare riferimento alla classe affinché l'elemento sia valido. `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="39c7d-140">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39c7d-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="39c7d-141">Example</span></span>  
 <span data-ttu-id="39c7d-142">Nel codice XML seguente viene illustrato come specificare il registro dei nomi delle autorità emittenti basato sulla configurazione.</span><span class="sxs-lookup"><span data-stu-id="39c7d-142">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="39c7d-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39c7d-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
