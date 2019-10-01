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
ms.openlocfilehash: 4e2159cda5f35b5795804dede09ec17d07d71b23
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699740"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="0e685-102">Elemento > \<mscorlib per le impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="0e685-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="0e685-103">Contiene l' [elemento > \<cryptographySettings](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="0e685-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[<span data-ttu-id="0e685-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="0e685-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="0e685-105">&nbsp; @ no__t-1 **\<mscorlib >**</span><span class="sxs-lookup"><span data-stu-id="0e685-105">&nbsp;&nbsp;**\<mscorlib>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e685-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e685-106">Syntax</span></span>  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e685-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0e685-107">Attributes and Elements</span></span>  
 <span data-ttu-id="0e685-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0e685-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e685-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="0e685-109">Attributes</span></span>  
 <span data-ttu-id="0e685-110">No.</span><span class="sxs-lookup"><span data-stu-id="0e685-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0e685-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0e685-111">Child Elements</span></span>  
  
|<span data-ttu-id="0e685-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e685-112">Element</span></span>|<span data-ttu-id="0e685-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e685-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="0e685-114">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="0e685-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0e685-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0e685-115">Parent Elements</span></span>  
  
|<span data-ttu-id="0e685-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e685-116">Element</span></span>|<span data-ttu-id="0e685-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e685-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0e685-118">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0e685-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0e685-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="0e685-119">Example</span></span>  
 <span data-ttu-id="0e685-120">Nell'esempio seguente viene illustrato come utilizzare l'elemento **> \<mscorlib** per fare riferimento a una classe di crittografia e configurare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="0e685-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="0e685-121">È quindi possibile passare la stringa "RSA" al metodo <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> e usare il metodo <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> per restituire un oggetto `MyCryptoRSAClass`.</span><span class="sxs-lookup"><span data-stu-id="0e685-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0e685-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e685-122">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="0e685-123">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="0e685-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0e685-124">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="0e685-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0e685-125">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="0e685-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="0e685-126">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="0e685-126">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
