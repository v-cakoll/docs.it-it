---
title: '&lt;cryptoClass&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 728fff7b8626e227e692c713f4cb05049c14a9f1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742757"
---
# <a name="ltcryptoclassgt-element"></a><span data-ttu-id="50088-102">&lt;cryptoClass&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="50088-102">&lt;cryptoClass&gt; Element</span></span>
<span data-ttu-id="50088-103">Contiene una classe di crittografia per la quale è stato eseguito il mapping a un nome descrittivo nell'elemento [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="50088-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="50088-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="50088-104">\<configuration></span></span>  
<span data-ttu-id="50088-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="50088-105">\<mscorlib></span></span>  
<span data-ttu-id="50088-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="50088-106">\<cryptographySettings></span></span>  
<span data-ttu-id="50088-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="50088-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="50088-108">\<cryptoClasses ></span><span class="sxs-lookup"><span data-stu-id="50088-108">\<cryptoClasses></span></span>  
<span data-ttu-id="50088-109">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="50088-109">\<cryptoClass></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50088-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50088-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50088-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="50088-111">Attributes and Elements</span></span>  
 <span data-ttu-id="50088-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="50088-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50088-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="50088-113">Attributes</span></span>  
  
|<span data-ttu-id="50088-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="50088-114">Attribute</span></span>|<span data-ttu-id="50088-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50088-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="50088-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="50088-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="50088-117">Contiene le informazioni per la classe di crittografia.</span><span class="sxs-lookup"><span data-stu-id="50088-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="50088-118">Usare questo attributo per specificare un nome breve per la classe.</span><span class="sxs-lookup"><span data-stu-id="50088-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="50088-119">È necessario specificare una stringa che soddisfi i requisiti indicati in [specifica di nomi di tipo completi](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="50088-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50088-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="50088-120">Child Elements</span></span>  
 <span data-ttu-id="50088-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="50088-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="50088-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="50088-122">Parent Elements</span></span>  
  
|<span data-ttu-id="50088-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="50088-123">Element</span></span>|<span data-ttu-id="50088-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50088-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="50088-125">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="50088-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="50088-126">Contiene un elenco delle classi di crittografia per le quali è stato eseguito il mapping a un nome descrittivo nell'elemento [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="50088-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="50088-127">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="50088-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="50088-128">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="50088-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="50088-129">Contiene l'elemento [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="50088-129">Contains the [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="50088-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="50088-130">Example</span></span>  
 <span data-ttu-id="50088-131">Nell'esempio seguente viene illustrato come utilizzare il  **\<cryptoClass >** elemento a cui fare riferimento a una classe di crittografia e configurare il runtime.</span><span class="sxs-lookup"><span data-stu-id="50088-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="50088-132">È quindi possibile passare la stringa "RSA" per il <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metodo e utilizzare il <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> per restituire un `MyCryptoRSAClass` oggetto.</span><span class="sxs-lookup"><span data-stu-id="50088-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="50088-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50088-133">See Also</span></span>  
 [<span data-ttu-id="50088-134">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="50088-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="50088-135">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="50088-135">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="50088-136">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="50088-136">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="50088-137">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="50088-137">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
