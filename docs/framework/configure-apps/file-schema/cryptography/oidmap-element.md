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
ms.openlocfilehash: eec2c4745ad5a0492ccf04c8f23b901275f23c01
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698442"
---
# <a name="oidmap-element"></a><span data-ttu-id="57452-102">Elemento > \<oidMap</span><span class="sxs-lookup"><span data-stu-id="57452-102">\<oidMap> Element</span></span>
<span data-ttu-id="57452-103">Contiene i mapping degli identificatori di oggetto (OID) ASN. 1 alle classi.</span><span class="sxs-lookup"><span data-stu-id="57452-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  
  
[<span data-ttu-id="57452-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="57452-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="57452-105">&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="57452-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="57452-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="57452-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="57452-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<oidMap >**</span><span class="sxs-lookup"><span data-stu-id="57452-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57452-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57452-108">Syntax</span></span>  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57452-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="57452-109">Attributes and Elements</span></span>  
 <span data-ttu-id="57452-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="57452-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57452-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="57452-111">Attributes</span></span>  
 <span data-ttu-id="57452-112">No.</span><span class="sxs-lookup"><span data-stu-id="57452-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="57452-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="57452-113">Child Elements</span></span>  
  
|<span data-ttu-id="57452-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="57452-114">Element</span></span>|<span data-ttu-id="57452-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57452-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="57452-116">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="57452-116">\<oidEntry></span></span>](oidentry-element.md)|<span data-ttu-id="57452-117">Esegue il mapping di un OID ASN. 1 a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="57452-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="57452-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="57452-118">Parent Elements</span></span>  
  
|<span data-ttu-id="57452-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="57452-119">Element</span></span>|<span data-ttu-id="57452-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57452-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="57452-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="57452-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="57452-122">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="57452-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="57452-123">Contiene l' `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="57452-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="57452-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="57452-124">Example</span></span>  
 <span data-ttu-id="57452-125">Nell'esempio seguente viene illustrato come utilizzare l'elemento **> \<oidMap** per contenere un mapping di un OID per l'algoritmo hash RIPEMD-160 a un'implementazione dell'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="57452-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="57452-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57452-126">See also</span></span>

- [<span data-ttu-id="57452-127">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="57452-127">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="57452-128">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="57452-128">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="57452-129">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="57452-129">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="57452-130">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="57452-130">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="57452-131">Mapping di identificatori di oggetti ad algoritmi di crittografia</span><span class="sxs-lookup"><span data-stu-id="57452-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
