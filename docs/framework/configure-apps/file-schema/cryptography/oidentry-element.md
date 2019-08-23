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
ms.openlocfilehash: cbdf6150010ca2dace3f0610d9caa90c2bf52746
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921050"
---
# <a name="oidentry-element"></a><span data-ttu-id="c1834-102">\<Elemento > oidEntry</span><span class="sxs-lookup"><span data-stu-id="c1834-102">\<oidEntry> Element</span></span>
<span data-ttu-id="c1834-103">Esegue il mapping di un identificatore di oggetto (OID) ASN.1 a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="c1834-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  
  
 <span data-ttu-id="c1834-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c1834-104">\<configuration></span></span>  
<span data-ttu-id="c1834-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="c1834-105">\<mscorlib></span></span>  
<span data-ttu-id="c1834-106">\<> cryptographySettings</span><span class="sxs-lookup"><span data-stu-id="c1834-106">\<cryptographySettings></span></span>  
<span data-ttu-id="c1834-107">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="c1834-107">\<oidMap></span></span>  
<span data-ttu-id="c1834-108">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="c1834-108">\<oidEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1834-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c1834-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1834-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c1834-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c1834-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c1834-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1834-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="c1834-112">Attributes</span></span>  
  
|<span data-ttu-id="c1834-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="c1834-113">Attribute</span></span>|<span data-ttu-id="c1834-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1834-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c1834-115">**OID**</span><span class="sxs-lookup"><span data-stu-id="c1834-115">**OID**</span></span>|<span data-ttu-id="c1834-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c1834-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="c1834-117">Specifica l'OID ASN. 1 corrispondente all'algoritmo implementato dalla classe.</span><span class="sxs-lookup"><span data-stu-id="c1834-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="c1834-118">**name**</span><span class="sxs-lookup"><span data-stu-id="c1834-118">**name**</span></span>|<span data-ttu-id="c1834-119">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c1834-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="c1834-120">Specifica il valore per l'attributo **Name** nel tag del [ \<> nameEntry](nameentry-element.md) .</span><span class="sxs-lookup"><span data-stu-id="c1834-120">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1834-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c1834-121">Child Elements</span></span>  
 <span data-ttu-id="c1834-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c1834-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1834-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c1834-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c1834-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1834-124">Element</span></span>|<span data-ttu-id="c1834-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1834-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c1834-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c1834-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="c1834-127">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="c1834-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="c1834-128">Contiene l' `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="c1834-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="c1834-129">Contiene i mapping degli identificatori di oggetto (OID) ASN. 1 alle classi.</span><span class="sxs-lookup"><span data-stu-id="c1834-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1834-130">Note</span><span class="sxs-lookup"><span data-stu-id="c1834-130">Remarks</span></span>  
 <span data-ttu-id="c1834-131">Gli identificatori di oggetto ASN. 1 identificano gli algoritmi in alcuni formati crittografici.</span><span class="sxs-lookup"><span data-stu-id="c1834-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="c1834-132">Eseguire il mapping degli identificatori di oggetto ai nomi descrittivi per gli algoritmi che si desidera identificare.</span><span class="sxs-lookup"><span data-stu-id="c1834-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1834-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="c1834-133">Example</span></span>  
 <span data-ttu-id="c1834-134">Nell'esempio seguente viene illustrato come utilizzare il **\<oidEntry >** elemento per eseguire il mapping di un identificatore di oggetto per l'algoritmo hash RIPEMD-160 a un'implementazione dell'algoritmo di hash.</span><span class="sxs-lookup"><span data-stu-id="c1834-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c1834-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1834-135">See also</span></span>

- [<span data-ttu-id="c1834-136">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="c1834-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c1834-137">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="c1834-137">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c1834-138">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="c1834-138">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="c1834-139">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="c1834-139">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="c1834-140">Mapping di identificatori di oggetti ad algoritmi di crittografia</span><span class="sxs-lookup"><span data-stu-id="c1834-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
