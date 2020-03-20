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
ms.openlocfilehash: ed28ae4a52085cbfa781b4baf2ee1eafbeff6eb4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154829"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="64cd6-102">\<module> Element (Impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="64cd6-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="64cd6-103">Aggiunge un nuovo modulo proxy all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="64cd6-103">Adds a new proxy module to the application.</span></span>  

<span data-ttu-id="64cd6-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="64cd6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="64cd6-105">&nbsp;&nbsp;[**\<>system.net**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="64cd6-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="64cd6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>defaultProxy**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="64cd6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="64cd6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>modulo**</span><span class="sxs-lookup"><span data-stu-id="64cd6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**</span></span>

## <a name="syntax"></a><span data-ttu-id="64cd6-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64cd6-108">Syntax</span></span>  
  
```xml  
<module
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64cd6-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="64cd6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="64cd6-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="64cd6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64cd6-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="64cd6-111">Attributes</span></span>  
  
|<span data-ttu-id="64cd6-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="64cd6-112">**Attribute**</span></span>|<span data-ttu-id="64cd6-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="64cd6-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="64cd6-114">Il nome completo del <xref:System.Type.FullName%2A> tipo (indicato dalla proprietà) e il <xref:System.Reflection.Assembly.FullName%2A> nome dell'assembly (indicato dalla proprietà), separati da una virgola, che implementa il proxy.</span><span class="sxs-lookup"><span data-stu-id="64cd6-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64cd6-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="64cd6-115">Child Elements</span></span>  
 <span data-ttu-id="64cd6-116">No.</span><span class="sxs-lookup"><span data-stu-id="64cd6-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="64cd6-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="64cd6-117">Parent Elements</span></span>  
  
|<span data-ttu-id="64cd6-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="64cd6-118">**Element**</span></span>|<span data-ttu-id="64cd6-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="64cd6-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="64cd6-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="64cd6-120">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="64cd6-121">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="64cd6-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64cd6-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="64cd6-122">Remarks</span></span>  
 <span data-ttu-id="64cd6-123">L'elemento `module` registra le classi <xref:System.Net.IWebProxy> proxy che implementano l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="64cd6-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="64cd6-124">Dopo la registrazione della classe proxy, `module` può essere utilizzato per richiedere informazioni mediante il proxy supportato.</span><span class="sxs-lookup"><span data-stu-id="64cd6-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="64cd6-125">Il valore `type` dell'attributo deve essere il nome della classe del modulo e il nome della corrispondente libreria a collegamento dinamico (DLL).</span><span class="sxs-lookup"><span data-stu-id="64cd6-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="64cd6-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="64cd6-126">Configuration Files</span></span>  
 <span data-ttu-id="64cd6-127">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="64cd6-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="64cd6-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="64cd6-128">Example</span></span>  
 <span data-ttu-id="64cd6-129">Nell'esempio seguente viene registrato una classe proxy personalizzata.</span><span class="sxs-lookup"><span data-stu-id="64cd6-129">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64cd6-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64cd6-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="64cd6-131">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="64cd6-131">Network Settings Schema</span></span>](index.md)
