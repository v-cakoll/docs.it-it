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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155181"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="55da3-102">Elemento \<mscorlib> per le impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="55da3-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="55da3-103">Contiene l' [ \<cryptographySettings> elemento](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="55da3-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<mscorlib>**  
  
## <a name="syntax"></a><span data-ttu-id="55da3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="55da3-104">Syntax</span></span>  
  
```xml  
      <mscorlib>
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55da3-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="55da3-105">Attributes and Elements</span></span>  
 <span data-ttu-id="55da3-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="55da3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55da3-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="55da3-107">Attributes</span></span>  
 <span data-ttu-id="55da3-108">No.</span><span class="sxs-lookup"><span data-stu-id="55da3-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="55da3-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="55da3-109">Child Elements</span></span>  
  
|<span data-ttu-id="55da3-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="55da3-110">Element</span></span>|<span data-ttu-id="55da3-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55da3-111">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="55da3-112">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="55da3-112">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="55da3-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="55da3-113">Parent Elements</span></span>  
  
|<span data-ttu-id="55da3-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="55da3-114">Element</span></span>|<span data-ttu-id="55da3-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55da3-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="55da3-116">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="55da3-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="55da3-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="55da3-117">Example</span></span>  
 <span data-ttu-id="55da3-118">Nell'esempio seguente viene illustrato come utilizzare l' **\<mscorlib>** elemento per fare riferimento a una classe di crittografia e configurare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="55da3-118">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="55da3-119">È quindi possibile passare la stringa "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metodo e usare il <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> metodo per restituire un `MyCryptoRSAClass` oggetto.</span><span class="sxs-lookup"><span data-stu-id="55da3-119">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="55da3-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="55da3-120">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="55da3-121">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="55da3-121">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="55da3-122">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="55da3-122">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="55da3-123">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="55da3-123">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="55da3-124">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="55da3-124">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
