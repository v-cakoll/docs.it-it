---
title: Elemento <mscorlib> per le impostazioni di crittografia
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
ms.openlocfilehash: d1d805f7154c18dba2dcd4eb7228cc200d8da811
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155181"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="8c9af-102">\<Elemento> mscorlib per le impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="8c9af-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="8c9af-103">Contiene [ \<l'elemento> cryptographySettings](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="8c9af-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[<span data-ttu-id="8c9af-104">**\<>di configurazione**</span><span class="sxs-lookup"><span data-stu-id="8c9af-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="8c9af-105">&nbsp;&nbsp;**\<>mscorlib**</span><span class="sxs-lookup"><span data-stu-id="8c9af-105">&nbsp;&nbsp;**\<mscorlib>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c9af-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c9af-106">Syntax</span></span>  
  
```xml  
      <mscorlib>
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c9af-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8c9af-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8c9af-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8c9af-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c9af-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="8c9af-109">Attributes</span></span>  
 <span data-ttu-id="8c9af-110">No.</span><span class="sxs-lookup"><span data-stu-id="8c9af-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8c9af-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8c9af-111">Child Elements</span></span>  
  
|<span data-ttu-id="8c9af-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c9af-112">Element</span></span>|<span data-ttu-id="8c9af-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c9af-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="8c9af-114">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="8c9af-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c9af-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8c9af-115">Parent Elements</span></span>  
  
|<span data-ttu-id="8c9af-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c9af-116">Element</span></span>|<span data-ttu-id="8c9af-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c9af-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8c9af-118">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8c9af-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8c9af-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="8c9af-119">Example</span></span>  
 <span data-ttu-id="8c9af-120">Nell'esempio seguente viene illustrato come utilizzare l'elemento \*\* \<mscorlib>\*\* per fare riferimento a una classe di crittografia e per configurare il runtime.</span><span class="sxs-lookup"><span data-stu-id="8c9af-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="8c9af-121">È quindi possibile passare la stringa <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> "RSA" <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> al metodo `MyCryptoRSAClass` e utilizzare il metodo per restituire un oggetto.</span><span class="sxs-lookup"><span data-stu-id="8c9af-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8c9af-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c9af-122">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="8c9af-123">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="8c9af-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="8c9af-124">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="8c9af-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8c9af-125">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="8c9af-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="8c9af-126">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="8c9af-126">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
