---
title: '&lt;nameEntry&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
author: mcleblanc
ms.author: markl
ms.openlocfilehash: a4c29db3f84570d4d5e99a1deaf8beb3145c8ea1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626940"
---
# <a name="ltnameentrygt-element"></a><span data-ttu-id="e4f58-102">&lt;nameEntry&gt; Element</span><span class="sxs-lookup"><span data-stu-id="e4f58-102">&lt;nameEntry&gt; Element</span></span>
<span data-ttu-id="e4f58-103">Esegue il mapping di un nome di classe a un nome di algoritmo descrittivo, in modo da poter associare più nomi descrittivi a una classe.</span><span class="sxs-lookup"><span data-stu-id="e4f58-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
 <span data-ttu-id="e4f58-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e4f58-104">\<configuration></span></span>  
<span data-ttu-id="e4f58-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="e4f58-105">\<mscorlib></span></span>  
<span data-ttu-id="e4f58-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="e4f58-106">\<cryptographySettings></span></span>  
<span data-ttu-id="e4f58-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="e4f58-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="e4f58-108">\<nameEntry></span><span class="sxs-lookup"><span data-stu-id="e4f58-108">\<nameEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4f58-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4f58-109">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4f58-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e4f58-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e4f58-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e4f58-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4f58-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="e4f58-112">Attributes</span></span>  
  
|<span data-ttu-id="e4f58-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="e4f58-113">Attribute</span></span>|<span data-ttu-id="e4f58-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4f58-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e4f58-115">**name**</span><span class="sxs-lookup"><span data-stu-id="e4f58-115">**name**</span></span>|<span data-ttu-id="e4f58-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e4f58-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="e4f58-117">Specifica il nome descrittivo dell'algoritmo che implementa la classe di crittografia.</span><span class="sxs-lookup"><span data-stu-id="e4f58-117">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="e4f58-118">**class**</span><span class="sxs-lookup"><span data-stu-id="e4f58-118">**class**</span></span>|<span data-ttu-id="e4f58-119">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e4f58-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="e4f58-120">Specifica il valore per il **name** attributo il [ \<cryptoClass >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="e4f58-120">Specifies the value for the **name** attribute in the [\<cryptoClass>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4f58-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e4f58-121">Child Elements</span></span>  
 <span data-ttu-id="e4f58-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e4f58-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e4f58-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e4f58-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e4f58-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4f58-124">Element</span></span>|<span data-ttu-id="e4f58-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4f58-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e4f58-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e4f58-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="e4f58-127">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e4f58-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4f58-128">Note</span><span class="sxs-lookup"><span data-stu-id="e4f58-128">Remarks</span></span>  
 <span data-ttu-id="e4f58-129">Il **name** attributo può essere il nome di una delle classi astratte trovate nel <xref:System.Security.Cryptography> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e4f58-129">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="e4f58-130">Quando si chiama il **Create** metodo su una classe astratta di crittografia, il nome di classe astratta viene passato per il <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="e4f58-130">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="e4f58-131">**CreateFromName** restituisce un'istanza del tipo indicato per il **classe** attributo.</span><span class="sxs-lookup"><span data-stu-id="e4f58-131">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="e4f58-132">Se il **name** attributo è un nome breve, ad esempio RSA, è possibile usare questo nome quando si chiama il **CreateFromName** (metodo).</span><span class="sxs-lookup"><span data-stu-id="e4f58-132">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4f58-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="e4f58-133">Example</span></span>  
 <span data-ttu-id="e4f58-134">Nell'esempio seguente viene illustrato come utilizzare il  **\<nameEntry >** elemento a cui fare riferimento a una classe di crittografia e configurare il runtime.</span><span class="sxs-lookup"><span data-stu-id="e4f58-134">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="e4f58-135">È quindi possibile passare la stringa "RSA" per il <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metodo e usare il <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> metodo restituisca un `MyCryptoRSAClass` oggetto.</span><span class="sxs-lookup"><span data-stu-id="e4f58-135">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e4f58-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4f58-136">See also</span></span>
- [<span data-ttu-id="e4f58-137">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="e4f58-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="e4f58-138">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="e4f58-138">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="e4f58-139">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="e4f58-139">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="e4f58-140">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="e4f58-140">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
