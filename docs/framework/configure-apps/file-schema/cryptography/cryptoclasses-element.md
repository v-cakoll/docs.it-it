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
ms.openlocfilehash: 87e64ecd79ebc54a669d33550790781c87b5917c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921125"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="7add4-102">\<Elemento > cryptoClasses</span><span class="sxs-lookup"><span data-stu-id="7add4-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="7add4-103">Contiene un elenco delle classi di crittografia per le quali è stato eseguito il mapping a un nome descrittivo nell'elemento [\<nameEntry>](nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="7add4-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="7add4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7add4-104">\<configuration></span></span>  
<span data-ttu-id="7add4-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="7add4-105">\<mscorlib></span></span>  
<span data-ttu-id="7add4-106">\<> cryptographySettings</span><span class="sxs-lookup"><span data-stu-id="7add4-106">\<cryptographySettings></span></span>  
<span data-ttu-id="7add4-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="7add4-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="7add4-108">\<> cryptoClasses</span><span class="sxs-lookup"><span data-stu-id="7add4-108">\<cryptoClasses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7add4-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7add4-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7add4-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7add4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7add4-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7add4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7add4-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="7add4-112">Attributes</span></span>  
 <span data-ttu-id="7add4-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7add4-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7add4-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7add4-114">Child Elements</span></span>  
  
|<span data-ttu-id="7add4-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="7add4-115">Element</span></span>|<span data-ttu-id="7add4-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7add4-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7add4-117">\<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="7add4-117">\<cryptoClass></span></span>](cryptoclass-element.md)|<span data-ttu-id="7add4-118">Contiene una classe di crittografia per la quale è stato eseguito il mapping a un nome descrittivo nell'elemento **\<nameEntry>** .</span><span class="sxs-lookup"><span data-stu-id="7add4-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7add4-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7add4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7add4-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="7add4-120">Element</span></span>|<span data-ttu-id="7add4-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7add4-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7add4-122">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7add4-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="7add4-123">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="7add4-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="7add4-124">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="7add4-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="7add4-125">Contiene l' `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="7add4-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7add4-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="7add4-126">Example</span></span>  
 <span data-ttu-id="7add4-127">Nell'esempio seguente viene illustrato come utilizzare l'  **\<elemento > CryptoClass** per fare riferimento a una classe di crittografia e configurare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="7add4-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="7add4-128">È quindi possibile passare la stringa "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metodo e usare il <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> metodo per restituire un `MyCryptoRSAClass` oggetto.</span><span class="sxs-lookup"><span data-stu-id="7add4-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7add4-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7add4-129">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="7add4-130">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="7add4-130">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7add4-131">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="7add4-131">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7add4-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="7add4-132">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="7add4-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="7add4-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)
- [<span data-ttu-id="7add4-134">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="7add4-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
