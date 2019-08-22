---
title: <oidMap> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
ms.openlocfilehash: e01cdd942237141b8ef35495d3b74d6b2282a865
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664249"
---
# <a name="oidmap-element"></a><span data-ttu-id="4da8d-102">\<Elemento > oidMap</span><span class="sxs-lookup"><span data-stu-id="4da8d-102">\<oidMap> Element</span></span>
<span data-ttu-id="4da8d-103">Contiene i mapping degli identificatori di oggetto (OID) ASN. 1 alle classi.</span><span class="sxs-lookup"><span data-stu-id="4da8d-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  
  
 <span data-ttu-id="4da8d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4da8d-104">\<configuration></span></span>  
<span data-ttu-id="4da8d-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="4da8d-105">\<mscorlib></span></span>  
<span data-ttu-id="4da8d-106">\<> cryptographySettings</span><span class="sxs-lookup"><span data-stu-id="4da8d-106">\<cryptographySettings></span></span>  
<span data-ttu-id="4da8d-107">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="4da8d-107">\<oidMap></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4da8d-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4da8d-108">Syntax</span></span>  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4da8d-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4da8d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4da8d-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4da8d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4da8d-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="4da8d-111">Attributes</span></span>  
 <span data-ttu-id="4da8d-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4da8d-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4da8d-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4da8d-113">Child Elements</span></span>  
  
|<span data-ttu-id="4da8d-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="4da8d-114">Element</span></span>|<span data-ttu-id="4da8d-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4da8d-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4da8d-116">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="4da8d-116">\<oidEntry></span></span>](oidentry-element.md)|<span data-ttu-id="4da8d-117">Esegue il mapping di un OID ASN. 1 a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="4da8d-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4da8d-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4da8d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4da8d-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="4da8d-119">Element</span></span>|<span data-ttu-id="4da8d-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4da8d-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4da8d-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4da8d-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="4da8d-122">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="4da8d-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="4da8d-123">Contiene l' `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="4da8d-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4da8d-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="4da8d-124">Example</span></span>  
 <span data-ttu-id="4da8d-125">Nell'esempio seguente viene illustrato come utilizzare l'  **\<elemento > oidMap** per contenere un mapping di un OID per l'algoritmo hash RIPEMD-160 a un'implementazione di tale algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="4da8d-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4da8d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4da8d-126">See also</span></span>

- [<span data-ttu-id="4da8d-127">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="4da8d-127">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4da8d-128">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="4da8d-128">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4da8d-129">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="4da8d-129">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="4da8d-130">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="4da8d-130">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="4da8d-131">Mapping di identificatori di oggetti ad algoritmi di crittografia</span><span class="sxs-lookup"><span data-stu-id="4da8d-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
