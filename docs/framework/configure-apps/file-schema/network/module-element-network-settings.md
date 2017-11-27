---
title: '&lt;modulo&gt; elemento (impostazioni di rete)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a039f6ed985997c5557659abd299fe0fc7699a1b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltmodulegt-element-network-settings"></a><span data-ttu-id="0ad1a-102">&lt;modulo&gt; elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="0ad1a-102">&lt;module&gt; Element (Network Settings)</span></span>
<span data-ttu-id="0ad1a-103">Aggiunge un nuovo modulo proxy all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0ad1a-103">Adds a new proxy module to the application.</span></span>  
  
 <span data-ttu-id="0ad1a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0ad1a-104">\<configuration></span></span>  
<span data-ttu-id="0ad1a-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="0ad1a-105">\<system.net></span></span>  
<span data-ttu-id="0ad1a-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="0ad1a-106">\<defaultProxy></span></span>  
<span data-ttu-id="0ad1a-107">\<modulo ></span><span class="sxs-lookup"><span data-stu-id="0ad1a-107">\<module></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ad1a-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ad1a-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ad1a-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0ad1a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0ad1a-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0ad1a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ad1a-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="0ad1a-111">Attributes</span></span>  
  
|<span data-ttu-id="0ad1a-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="0ad1a-112">**Attribute**</span></span>|<span data-ttu-id="0ad1a-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0ad1a-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="0ad1a-114">Il nome completo del tipo (indicato dal <xref:System.Type.FullName%2A> proprietà) e il nome dell'assembly (indicato dal <xref:System.Reflection.Assembly.FullName%2A> proprietà), separati da una virgola, che implementa il proxy.</span><span class="sxs-lookup"><span data-stu-id="0ad1a-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ad1a-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0ad1a-115">Child Elements</span></span>  
 <span data-ttu-id="0ad1a-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0ad1a-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0ad1a-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0ad1a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0ad1a-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="0ad1a-118">**Element**</span></span>|<span data-ttu-id="0ad1a-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0ad1a-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0ad1a-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="0ad1a-120">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="0ad1a-121">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="0ad1a-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ad1a-122">Note</span><span class="sxs-lookup"><span data-stu-id="0ad1a-122">Remarks</span></span>  
 <span data-ttu-id="0ad1a-123">Il `module` elemento consente di registrare le classi proxy che implementano il <xref:System.Net.IWebProxy> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="0ad1a-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="0ad1a-124">Dopo la registrazione della classe proxy, `module` può essere utilizzato per richiedere informazioni mediante il proxy supportato.</span><span class="sxs-lookup"><span data-stu-id="0ad1a-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="0ad1a-125">Il valore per il `type` attributo deve essere il nome della classe del modulo e il nome della relativa libreria a collegamento dinamico (DLL) corrispondente.</span><span class="sxs-lookup"><span data-stu-id="0ad1a-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="0ad1a-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="0ad1a-126">Configuration Files</span></span>  
 <span data-ttu-id="0ad1a-127">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="0ad1a-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ad1a-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ad1a-128">Example</span></span>  
 <span data-ttu-id="0ad1a-129">Nell'esempio seguente registra una classe proxy personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0ad1a-129">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0ad1a-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ad1a-130">See Also</span></span>  
 <xref:System.Net.IWebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="0ad1a-131">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="0ad1a-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
