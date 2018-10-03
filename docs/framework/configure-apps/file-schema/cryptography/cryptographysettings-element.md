---
title: '&lt;cryptographySettings&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
author: mcleblanc
ms.author: markl
ms.openlocfilehash: dc55acd7a698ef37d45e8a412db684c13a3b8b16
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48025454"
---
# <a name="ltcryptographysettingsgt-element"></a><span data-ttu-id="23bf1-102">&lt;cryptographySettings&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="23bf1-102">&lt;cryptographySettings&gt; Element</span></span>
<span data-ttu-id="23bf1-103">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="23bf1-103">Contains cryptography settings.</span></span>  
  
 <span data-ttu-id="23bf1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="23bf1-104">\<configuration></span></span>  
<span data-ttu-id="23bf1-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="23bf1-105">\<mscorlib></span></span>  
<span data-ttu-id="23bf1-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="23bf1-106">\<cryptographySettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23bf1-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23bf1-107">Syntax</span></span>  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23bf1-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="23bf1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="23bf1-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="23bf1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23bf1-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="23bf1-110">Attributes</span></span>  
 <span data-ttu-id="23bf1-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="23bf1-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="23bf1-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="23bf1-112">Child Elements</span></span>  
  
|<span data-ttu-id="23bf1-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="23bf1-113">Element</span></span>|<span data-ttu-id="23bf1-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23bf1-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23bf1-115">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="23bf1-115">\<cryptoNameMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|<span data-ttu-id="23bf1-116">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="23bf1-116">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="23bf1-117">\<oidMap ></span><span class="sxs-lookup"><span data-stu-id="23bf1-117">\<oidMap></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|<span data-ttu-id="23bf1-118">Contiene mapping di identificatore (OID) ASN.1 oggetto alle classi.</span><span class="sxs-lookup"><span data-stu-id="23bf1-118">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="23bf1-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="23bf1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="23bf1-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="23bf1-120">Element</span></span>|<span data-ttu-id="23bf1-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23bf1-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="23bf1-122">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="23bf1-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="23bf1-123">Contiene il `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="23bf1-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="23bf1-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="23bf1-124">Example</span></span>  
 <span data-ttu-id="23bf1-125">Nell'esempio seguente viene illustrato come utilizzare il  **\<cryptographySettings >** elemento per contenere i mapping dei nomi di crittografia e i mapping di OID.</span><span class="sxs-lookup"><span data-stu-id="23bf1-125">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="23bf1-126">In questo esempio configura il runtime in modo che <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> restituisce un `MyHashClass` oggetto e il `MyCryptoClass` classe esegue il mapping all'identificatore di oggetto 1.3.36.2.1.</span><span class="sxs-lookup"><span data-stu-id="23bf1-126">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="23bf1-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23bf1-127">See Also</span></span>  
 [<span data-ttu-id="23bf1-128">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="23bf1-128">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="23bf1-129">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="23bf1-129">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="23bf1-130">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="23bf1-130">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
