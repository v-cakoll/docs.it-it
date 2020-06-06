---
title: <nameEntry> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: a339638587f8b544bbc1b0073553f6232ce09694
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "71699784"
---
# <a name="nameentry-element"></a><span data-ttu-id="63b66-102">\<nameEntry> Elemento</span><span class="sxs-lookup"><span data-stu-id="63b66-102">\<nameEntry> Element</span></span>
<span data-ttu-id="63b66-103">Esegue il mapping di un nome di classe a un nome di algoritmo descrittivo, in modo da poter associare più nomi descrittivi a una classe.</span><span class="sxs-lookup"><span data-stu-id="63b66-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameEntry>**  
  
## <a name="syntax"></a><span data-ttu-id="63b66-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63b66-104">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63b66-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="63b66-105">Attributes and Elements</span></span>  
 <span data-ttu-id="63b66-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="63b66-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63b66-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="63b66-107">Attributes</span></span>  
  
|<span data-ttu-id="63b66-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="63b66-108">Attribute</span></span>|<span data-ttu-id="63b66-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="63b66-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="63b66-110">**nome**</span><span class="sxs-lookup"><span data-stu-id="63b66-110">**name**</span></span>|<span data-ttu-id="63b66-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="63b66-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="63b66-112">Specifica il nome descrittivo dell'algoritmo implementato dalla classe di crittografia.</span><span class="sxs-lookup"><span data-stu-id="63b66-112">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="63b66-113">**classe**</span><span class="sxs-lookup"><span data-stu-id="63b66-113">**class**</span></span>|<span data-ttu-id="63b66-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="63b66-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="63b66-115">Specifica il valore per l'attributo **Name** nell' [\<cryptoClass>](cryptoclass-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="63b66-115">Specifies the value for the **name** attribute in the [\<cryptoClass>](cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63b66-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="63b66-116">Child Elements</span></span>  
 <span data-ttu-id="63b66-117">No.</span><span class="sxs-lookup"><span data-stu-id="63b66-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63b66-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="63b66-118">Parent Elements</span></span>  
  
|<span data-ttu-id="63b66-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="63b66-119">Element</span></span>|<span data-ttu-id="63b66-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="63b66-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="63b66-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="63b66-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="63b66-122">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="63b66-122">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63b66-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="63b66-123">Remarks</span></span>  
 <span data-ttu-id="63b66-124">L'attributo **Name** può essere il nome di una delle classi astratte trovate nello <xref:System.Security.Cryptography> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="63b66-124">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="63b66-125">Quando si chiama il metodo **create** in una classe di crittografia astratta, il nome della classe astratta viene passato al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="63b66-125">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="63b66-126">**CreateFromName** restituisce un'istanza del tipo indicato dall'attributo **Class** .</span><span class="sxs-lookup"><span data-stu-id="63b66-126">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="63b66-127">Se l'attributo **Name** è un nome breve, ad esempio RSA, è possibile usare tale nome quando si chiama il metodo **CreateFromName** .</span><span class="sxs-lookup"><span data-stu-id="63b66-127">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63b66-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="63b66-128">Example</span></span>  
 <span data-ttu-id="63b66-129">Nell'esempio seguente viene illustrato come utilizzare l' **\<nameEntry>** elemento per fare riferimento a una classe di crittografia e configurare il Runtime.</span><span class="sxs-lookup"><span data-stu-id="63b66-129">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="63b66-130">È quindi possibile passare la stringa "RSA" al <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metodo e usare il <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> metodo per restituire un `MyCryptoRSAClass` oggetto.</span><span class="sxs-lookup"><span data-stu-id="63b66-130">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="63b66-131">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="63b66-131">See also</span></span>

- [<span data-ttu-id="63b66-132">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="63b66-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="63b66-133">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="63b66-133">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="63b66-134">Servizi di crittografia</span><span class="sxs-lookup"><span data-stu-id="63b66-134">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="63b66-135">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="63b66-135">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
