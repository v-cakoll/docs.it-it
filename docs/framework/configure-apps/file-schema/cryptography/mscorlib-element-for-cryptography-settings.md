---
title: '&lt;mscorlib&gt; (elemento) per le impostazioni di crittografia'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 6a8a589077aba413fa89518e560373df816f8943
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187845"
---
# <a name="ltmscorlibgt-element-for-cryptography-settings"></a><span data-ttu-id="8772b-102">&lt;mscorlib&gt; (elemento) per le impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="8772b-102">&lt;mscorlib&gt; Element for Cryptography Settings</span></span>
<span data-ttu-id="8772b-103">Contiene il [ \<cryptographySettings > elemento](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="8772b-103">Contains the [\<cryptographySettings> element](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span></span>  
  
 <span data-ttu-id="8772b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8772b-104">\<configuration></span></span>  
<span data-ttu-id="8772b-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="8772b-105">\<mscorlib></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8772b-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8772b-106">Syntax</span></span>  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8772b-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8772b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8772b-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8772b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8772b-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="8772b-109">Attributes</span></span>  
 <span data-ttu-id="8772b-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8772b-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8772b-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8772b-111">Child Elements</span></span>  
  
|<span data-ttu-id="8772b-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="8772b-112">Element</span></span>|<span data-ttu-id="8772b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8772b-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="8772b-114">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="8772b-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8772b-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8772b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="8772b-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="8772b-116">Element</span></span>|<span data-ttu-id="8772b-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8772b-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8772b-118">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8772b-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8772b-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="8772b-119">Example</span></span>  
 <span data-ttu-id="8772b-120">Nell'esempio seguente viene illustrato come utilizzare il  **\<mscorlib >** elemento a cui fare riferimento a una classe di crittografia e configurare il runtime.</span><span class="sxs-lookup"><span data-stu-id="8772b-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="8772b-121">È quindi possibile passare la stringa "RSA" per il <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metodo e usare il <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> metodo restituisca un `MyCryptoRSAClass` oggetto.</span><span class="sxs-lookup"><span data-stu-id="8772b-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8772b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8772b-122">See Also</span></span>  
- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>  
- <xref:System.Security.Cryptography>  
- [<span data-ttu-id="8772b-123">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="8772b-123">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="8772b-124">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="8772b-124">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
- [<span data-ttu-id="8772b-125">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="8772b-125">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
- [<span data-ttu-id="8772b-126">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="8772b-126">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
