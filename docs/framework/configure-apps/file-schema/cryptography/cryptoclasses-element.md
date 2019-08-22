---
title: <cryptoClasses> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
ms.openlocfilehash: dbe46e0b36d247005f933c82ee83687886b283d1
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659648"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="1082a-102">\<Elemento > cryptoClasses</span><span class="sxs-lookup"><span data-stu-id="1082a-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="1082a-103">Contiene un elenco delle classi di crittografia per le quali è stato eseguito il mapping a un nome descrittivo nell'elemento [\<nameEntry>](nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="1082a-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="1082a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1082a-104">\<configuration></span></span>  
<span data-ttu-id="1082a-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="1082a-105">\<mscorlib></span></span>  
<span data-ttu-id="1082a-106">\<> cryptographySettings</span><span class="sxs-lookup"><span data-stu-id="1082a-106">\<cryptographySettings></span></span>  
<span data-ttu-id="1082a-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="1082a-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="1082a-108">\<> cryptoClasses</span><span class="sxs-lookup"><span data-stu-id="1082a-108">\<cryptoClasses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1082a-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1082a-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1082a-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1082a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1082a-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1082a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1082a-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="1082a-112">Attributes</span></span>  
 <span data-ttu-id="1082a-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1082a-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1082a-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1082a-114">Child Elements</span></span>  
  
|<span data-ttu-id="1082a-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="1082a-115">Element</span></span>|<span data-ttu-id="1082a-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="1082a-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1082a-117">\<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="1082a-117">\<cryptoClass></span></span>](cryptoclass-element.md)|<span data-ttu-id="1082a-118">Contiene una classe di crittografia per la quale è stato eseguito il mapping a un nome descrittivo nell'elemento **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="1082a-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1082a-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1082a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1082a-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="1082a-120">Element</span></span>|<span data-ttu-id="1082a-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1082a-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1082a-122">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1082a-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="1082a-123">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="1082a-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="1082a-124">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="1082a-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="1082a-125">Contiene l' `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="1082a-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1082a-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="1082a-126">Example</span></span>  
 <span data-ttu-id="1082a-127">Nell'esempio seguente viene illustrato come utilizzare l'  **\<elemento > CryptoClass** per fare riferimento a una classe di crittografia e configurare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="1082a-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="1082a-128">È quindi possibile passare la stringa "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metodo e usare il <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> metodo per restituire un `MyCryptoRSAClass` oggetto.</span><span class="sxs-lookup"><span data-stu-id="1082a-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1082a-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1082a-129">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="1082a-130">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="1082a-130">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="1082a-131">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="1082a-131">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="1082a-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="1082a-132">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="1082a-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="1082a-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)
- [<span data-ttu-id="1082a-134">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="1082a-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
