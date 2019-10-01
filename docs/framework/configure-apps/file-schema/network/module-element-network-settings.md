---
title: Elemento <module> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
ms.openlocfilehash: 15f4d10a70dc3c6abd32869f5b7b0006a799b4bf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698038"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="f2550-102">Elemento > \<module (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="f2550-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="f2550-103">Aggiunge un nuovo modulo proxy all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f2550-103">Adds a new proxy module to the application.</span></span>  
  
[<span data-ttu-id="f2550-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="f2550-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f2550-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f2550-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="f2550-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f2550-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="f2550-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<module >**</span><span class="sxs-lookup"><span data-stu-id="f2550-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2550-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2550-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2550-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f2550-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f2550-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f2550-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2550-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="f2550-111">Attributes</span></span>  
  
|<span data-ttu-id="f2550-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="f2550-112">**Attribute**</span></span>|<span data-ttu-id="f2550-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f2550-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="f2550-114">Il nome completo del tipo (indicato dalla proprietà <xref:System.Type.FullName%2A>) e il nome dell'assembly (indicato dalla proprietà <xref:System.Reflection.Assembly.FullName%2A>), separati da una virgola, che implementa il proxy.</span><span class="sxs-lookup"><span data-stu-id="f2550-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2550-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f2550-115">Child Elements</span></span>  
 <span data-ttu-id="f2550-116">No.</span><span class="sxs-lookup"><span data-stu-id="f2550-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f2550-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f2550-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f2550-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="f2550-118">**Element**</span></span>|<span data-ttu-id="f2550-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f2550-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f2550-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="f2550-120">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="f2550-121">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="f2550-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2550-122">Note</span><span class="sxs-lookup"><span data-stu-id="f2550-122">Remarks</span></span>  
 <span data-ttu-id="f2550-123">L'elemento `module` registra le classi proxy che implementano l'interfaccia <xref:System.Net.IWebProxy>.</span><span class="sxs-lookup"><span data-stu-id="f2550-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="f2550-124">Dopo la registrazione della classe proxy, `module` può essere utilizzato per richiedere informazioni mediante il proxy supportato.</span><span class="sxs-lookup"><span data-stu-id="f2550-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="f2550-125">Il valore dell'attributo `type` deve corrispondere al nome della classe del modulo e al nome della corrispondente libreria di collegamento dinamico (DLL).</span><span class="sxs-lookup"><span data-stu-id="f2550-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f2550-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="f2550-126">Configuration Files</span></span>  
 <span data-ttu-id="f2550-127">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f2550-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2550-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="f2550-128">Example</span></span>  
 <span data-ttu-id="f2550-129">Nell'esempio seguente viene registrata una classe proxy personalizzata.</span><span class="sxs-lookup"><span data-stu-id="f2550-129">The following example registers a custom proxy class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <module  
        type="Test.CustomWebProxy, TestProxy, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b23a5c561934e385"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2550-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2550-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="f2550-131">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="f2550-131">Network Settings Schema</span></span>](index.md)
