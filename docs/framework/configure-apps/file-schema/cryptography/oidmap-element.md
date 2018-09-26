---
title: '&lt;oidMap&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 4ec2ba884f0f60182dd59bb6a4491e223f43ce1a
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47196616"
---
# <a name="ltoidmapgt-element"></a><span data-ttu-id="dde71-102">&lt;oidMap&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="dde71-102">&lt;oidMap&gt; Element</span></span>
<span data-ttu-id="dde71-103">Contiene mapping di identificatore (OID) ASN.1 oggetto alle classi.</span><span class="sxs-lookup"><span data-stu-id="dde71-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  
  
 <span data-ttu-id="dde71-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="dde71-104">\<configuration></span></span>  
<span data-ttu-id="dde71-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="dde71-105">\<mscorlib></span></span>  
<span data-ttu-id="dde71-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="dde71-106">\<cryptographySettings></span></span>  
<span data-ttu-id="dde71-107">\<oidMap ></span><span class="sxs-lookup"><span data-stu-id="dde71-107">\<oidMap></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dde71-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dde71-108">Syntax</span></span>  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dde71-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dde71-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dde71-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dde71-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dde71-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="dde71-111">Attributes</span></span>  
 <span data-ttu-id="dde71-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dde71-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dde71-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dde71-113">Child Elements</span></span>  
  
|<span data-ttu-id="dde71-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="dde71-114">Element</span></span>|<span data-ttu-id="dde71-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dde71-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dde71-116">\<oidEntry ></span><span class="sxs-lookup"><span data-stu-id="dde71-116">\<oidEntry></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|<span data-ttu-id="dde71-117">Esegue il mapping di OID ASN.1 a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="dde71-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dde71-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dde71-118">Parent Elements</span></span>  
  
|<span data-ttu-id="dde71-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="dde71-119">Element</span></span>|<span data-ttu-id="dde71-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dde71-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="dde71-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dde71-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="dde71-122">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="dde71-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="dde71-123">Contiene il `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="dde71-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dde71-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="dde71-124">Example</span></span>  
 <span data-ttu-id="dde71-125">Nell'esempio seguente viene illustrato come utilizzare il  **\<oidMap >** elemento per contenere il mapping di un OID per l'algoritmo hash RIPEMD-160 a un'implementazione dell'algoritmo di hash.</span><span class="sxs-lookup"><span data-stu-id="dde71-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"  name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dde71-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dde71-126">See Also</span></span>  
 [<span data-ttu-id="dde71-127">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="dde71-127">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="dde71-128">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="dde71-128">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="dde71-129">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="dde71-129">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="dde71-130">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="dde71-130">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [<span data-ttu-id="dde71-131">Mapping di identificatori di oggetti ad algoritmi di crittografia</span><span class="sxs-lookup"><span data-stu-id="dde71-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
