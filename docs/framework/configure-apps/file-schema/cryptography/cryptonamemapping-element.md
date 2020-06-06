---
title: <cryptoNameMapping> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping
helpviewer_keywords:
- <cryptoNameMapping> element
- cryptoNameMapping element
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
ms.openlocfilehash: d31c5cd52ffe0e2a6eb5784735e76436d216444b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155219"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="44b6c-102">\<cryptoNameMapping> Elemento</span><span class="sxs-lookup"><span data-stu-id="44b6c-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="44b6c-103">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="44b6c-103">Contains mappings of classes to friendly names.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**

## <a name="syntax"></a><span data-ttu-id="44b6c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44b6c-104">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44b6c-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="44b6c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="44b6c-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="44b6c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44b6c-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="44b6c-107">Attributes</span></span>  
 <span data-ttu-id="44b6c-108">No.</span><span class="sxs-lookup"><span data-stu-id="44b6c-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="44b6c-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="44b6c-109">Child Elements</span></span>  
  
|<span data-ttu-id="44b6c-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="44b6c-110">Element</span></span>|<span data-ttu-id="44b6c-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44b6c-111">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="44b6c-112">Contiene un elenco di classi di crittografia che dispongono di un mapping a un nome descrittivo nell' **\<nameEntry>** elemento.</span><span class="sxs-lookup"><span data-stu-id="44b6c-112">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="44b6c-113">Esegue il mapping di un nome di classe a un nome di algoritmo descrittivo, in modo da poter associare più nomi descrittivi a una classe.</span><span class="sxs-lookup"><span data-stu-id="44b6c-113">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="44b6c-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="44b6c-114">Parent Elements</span></span>  
  
|<span data-ttu-id="44b6c-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="44b6c-115">Element</span></span>|<span data-ttu-id="44b6c-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44b6c-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="44b6c-117">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44b6c-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="44b6c-118">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="44b6c-118">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="44b6c-119">Contiene i mapping di classi e nomi descrittivi.</span><span class="sxs-lookup"><span data-stu-id="44b6c-119">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="44b6c-120">Contiene l' \<cryptographySettings> elemento.</span><span class="sxs-lookup"><span data-stu-id="44b6c-120">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="44b6c-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="44b6c-121">Example</span></span>  
 <span data-ttu-id="44b6c-122">Nell'esempio seguente viene illustrato come utilizzare l' **\<cryptoNameMapping>** elemento per fare riferimento a una classe di crittografia e configurare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="44b6c-122">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="44b6c-123">È quindi possibile passare la stringa "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metodo e usare il <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> metodo per restituire un `MyCryptoRSAClass` oggetto.</span><span class="sxs-lookup"><span data-stu-id="44b6c-123">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="44b6c-124">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="44b6c-124">See also</span></span>

- [<span data-ttu-id="44b6c-125">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="44b6c-125">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="44b6c-126">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="44b6c-126">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="44b6c-127">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="44b6c-127">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="44b6c-128">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="44b6c-128">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
