---
title: <oidEntry> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: eed2a4d06906d2928be62aed20a75484c3eea946
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699738"
---
# <a name="oidentry-element"></a><span data-ttu-id="c8c8d-102">Elemento > \<oidEntry</span><span class="sxs-lookup"><span data-stu-id="c8c8d-102">\<oidEntry> Element</span></span>
<span data-ttu-id="c8c8d-103">Esegue il mapping di un identificatore di oggetto (OID) ASN.1 a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="c8c8d-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  
  
[<span data-ttu-id="c8c8d-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="c8c8d-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="c8c8d-105">&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c8c8d-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="c8c8d-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="c8c8d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="c8c8d-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<oidMap >** ](oidmap-element.md)</span><span class="sxs-lookup"><span data-stu-id="c8c8d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>  
<span data-ttu-id="c8c8d-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 **\<oidEntry >**</span><span class="sxs-lookup"><span data-stu-id="c8c8d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidEntry>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8c8d-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8c8d-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8c8d-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c8c8d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c8c8d-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c8c8d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8c8d-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="c8c8d-112">Attributes</span></span>  
  
|<span data-ttu-id="c8c8d-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="c8c8d-113">Attribute</span></span>|<span data-ttu-id="c8c8d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8c8d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c8c8d-115">**OID**</span><span class="sxs-lookup"><span data-stu-id="c8c8d-115">**OID**</span></span>|<span data-ttu-id="c8c8d-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c8c8d-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="c8c8d-117">Specifica l'OID ASN. 1 corrispondente all'algoritmo implementato dalla classe.</span><span class="sxs-lookup"><span data-stu-id="c8c8d-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="c8c8d-118">**name**</span><span class="sxs-lookup"><span data-stu-id="c8c8d-118">**name**</span></span>|<span data-ttu-id="c8c8d-119">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c8c8d-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="c8c8d-120">Specifica il valore per l'attributo **Name** nel tag di [> \<nameEntry](nameentry-element.md) .</span><span class="sxs-lookup"><span data-stu-id="c8c8d-120">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8c8d-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c8c8d-121">Child Elements</span></span>  
 <span data-ttu-id="c8c8d-122">No.</span><span class="sxs-lookup"><span data-stu-id="c8c8d-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8c8d-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c8c8d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c8c8d-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c8c8d-124">Element</span></span>|<span data-ttu-id="c8c8d-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8c8d-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c8c8d-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c8c8d-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="c8c8d-127">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="c8c8d-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="c8c8d-128">Contiene l' `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="c8c8d-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="c8c8d-129">Contiene i mapping degli identificatori di oggetto (OID) ASN. 1 alle classi.</span><span class="sxs-lookup"><span data-stu-id="c8c8d-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8c8d-130">Note</span><span class="sxs-lookup"><span data-stu-id="c8c8d-130">Remarks</span></span>  
 <span data-ttu-id="c8c8d-131">Gli identificatori di oggetto ASN. 1 identificano gli algoritmi in alcuni formati crittografici.</span><span class="sxs-lookup"><span data-stu-id="c8c8d-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="c8c8d-132">Eseguire il mapping degli identificatori di oggetto ai nomi descrittivi per gli algoritmi che si desidera identificare.</span><span class="sxs-lookup"><span data-stu-id="c8c8d-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8c8d-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="c8c8d-133">Example</span></span>  
 <span data-ttu-id="c8c8d-134">Nell'esempio seguente viene illustrato come utilizzare il **\<oidEntry >** elemento per eseguire il mapping di un identificatore di oggetto per l'algoritmo hash RIPEMD-160 a un'implementazione dell'algoritmo di hash.</span><span class="sxs-lookup"><span data-stu-id="c8c8d-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8c8d-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8c8d-135">See also</span></span>

- [<span data-ttu-id="c8c8d-136">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="c8c8d-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c8c8d-137">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="c8c8d-137">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c8c8d-138">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="c8c8d-138">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="c8c8d-139">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="c8c8d-139">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="c8c8d-140">Mapping di identificatori di oggetti ad algoritmi di crittografia</span><span class="sxs-lookup"><span data-stu-id="c8c8d-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
