---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 50fc7194823fb0c5c426fb54ffd50b17c3714ed9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251751"
---
# \<trustedIssuers>
<span data-ttu-id="d6581-101">Configura l'elenco dei certificati dell'autorità emittente attendibile usati dal registro di sistema del nome dell'autorità emittente basata sulla configurazione ( <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> ).</span><span class="sxs-lookup"><span data-stu-id="d6581-101">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerNameRegistry>**](issuernameregistry.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trustedIssuers>**  
  
## <a name="syntax"></a><span data-ttu-id="d6581-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6581-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6581-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d6581-103">Attributes and Elements</span></span>  
 <span data-ttu-id="d6581-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d6581-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6581-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="d6581-105">Attributes</span></span>  
 <span data-ttu-id="d6581-106">nessuno</span><span class="sxs-lookup"><span data-stu-id="d6581-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d6581-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d6581-107">Child Elements</span></span>  
  
|<span data-ttu-id="d6581-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6581-108">Element</span></span>|<span data-ttu-id="d6581-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6581-109">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="d6581-110">Aggiunge un certificato alla raccolta di autorità emittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="d6581-110">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="d6581-111">Il certificato viene specificato con l' `thumbprint` attributo.</span><span class="sxs-lookup"><span data-stu-id="d6581-111">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="d6581-112">Questo attributo è obbligatorio e deve contenere il formato con codifica ASN. 1 dell'identificazione personale del certificato.</span><span class="sxs-lookup"><span data-stu-id="d6581-112">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="d6581-113">L' `name` attributo è facoltativo e può essere usato per specificare un nome descrittivo per il certificato.</span><span class="sxs-lookup"><span data-stu-id="d6581-113">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="d6581-114">Cancella tutti i certificati dalla raccolta di autorità emittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="d6581-114">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="d6581-115">Rimuove un certificato dalla raccolta di autorità emittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="d6581-115">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="d6581-116">Il certificato viene specificato con l' `thumbprint` attributo.</span><span class="sxs-lookup"><span data-stu-id="d6581-116">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="d6581-117">Questo attributo è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d6581-117">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d6581-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d6581-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d6581-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6581-119">Element</span></span>|<span data-ttu-id="d6581-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6581-120">Description</span></span>|  
|-------------|-----------------|  
|[\<issuerNameRegistry>](issuernameregistry.md)|<span data-ttu-id="d6581-121">Configura il registro dei nomi delle autorità emittenti.</span><span class="sxs-lookup"><span data-stu-id="d6581-121">Configures the issuer name registry.</span></span> <span data-ttu-id="d6581-122">**Importante:**  L' `type` attributo dell' `<issuerNameRegistry>` elemento deve fare riferimento alla <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe affinché l' `<trustedIssuers>` elemento sia valido.</span><span class="sxs-lookup"><span data-stu-id="d6581-122">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6581-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="d6581-123">Remarks</span></span>  
 <span data-ttu-id="d6581-124">Windows Identity Foundation (WIF) fornisce una singola implementazione della <xref:System.IdentityModel.Tokens.IssuerNameRegistry> classe predefinita, la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe.</span><span class="sxs-lookup"><span data-stu-id="d6581-124">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="d6581-125">Il registro dei nomi delle autorità emittenti di configurazione mantiene un elenco di autorità emittenti attendibili caricate dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="d6581-125">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="d6581-126">L'elenco associa ogni nome dell'autorità emittente al certificato X. 509 necessario per verificare la firma dei token prodotti dall'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="d6581-126">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="d6581-127">L'elenco dei certificati dell'autorità emittente attendibile viene specificato nell' `<trustedIssuers>` elemento.</span><span class="sxs-lookup"><span data-stu-id="d6581-127">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="d6581-128">Ogni elemento nell'elenco associa il nome di un emittente mnemonico al certificato X. 509 necessario per verificare la firma dei token prodotti dall'emittente.</span><span class="sxs-lookup"><span data-stu-id="d6581-128">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="d6581-129">I certificati attendibili vengono specificati utilizzando il formato con codifica ASN. 1 dell'identificazione personale del certificato e vengono aggiunti alla raccolta tramite l' `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="d6581-129">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="d6581-130">È possibile cancellare o rimuovere autorità emittenti (certificati) dall'elenco usando gli `<clear>` `<remove>` elementi e.</span><span class="sxs-lookup"><span data-stu-id="d6581-130">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="d6581-131">L' `type` attributo dell' `<issuerNameRegistry>` elemento deve fare riferimento alla <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> classe affinché l' `<trustedIssuers>` elemento sia valido.</span><span class="sxs-lookup"><span data-stu-id="d6581-131">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6581-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="d6581-132">Example</span></span>  
 <span data-ttu-id="d6581-133">Nel codice XML seguente viene illustrato come specificare il registro dei nomi delle autorità emittenti basato sulla configurazione.</span><span class="sxs-lookup"><span data-stu-id="d6581-133">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6581-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6581-134">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
