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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154829"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="649d8-102">Elemento \<module> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="649d8-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="649d8-103">Aggiunge un nuovo modulo proxy all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="649d8-103">Adds a new proxy module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**

## <a name="syntax"></a><span data-ttu-id="649d8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="649d8-104">Syntax</span></span>  
  
```xml  
<module
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="649d8-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="649d8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="649d8-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="649d8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="649d8-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="649d8-107">Attributes</span></span>  
  
|<span data-ttu-id="649d8-108">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="649d8-108">**Attribute**</span></span>|<span data-ttu-id="649d8-109">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="649d8-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="649d8-110">Il nome completo del tipo (indicato dalla <xref:System.Type.FullName%2A> proprietà) e il nome dell'assembly (indicato dalla <xref:System.Reflection.Assembly.FullName%2A> proprietà), separati da una virgola, che implementa il proxy.</span><span class="sxs-lookup"><span data-stu-id="649d8-110">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="649d8-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="649d8-111">Child Elements</span></span>  
 <span data-ttu-id="649d8-112">No.</span><span class="sxs-lookup"><span data-stu-id="649d8-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="649d8-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="649d8-113">Parent Elements</span></span>  
  
|<span data-ttu-id="649d8-114">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="649d8-114">**Element**</span></span>|<span data-ttu-id="649d8-115">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="649d8-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="649d8-116">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="649d8-116">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="649d8-117">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="649d8-117">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="649d8-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="649d8-118">Remarks</span></span>  
 <span data-ttu-id="649d8-119">L' `module` elemento registra le classi proxy che implementano l' <xref:System.Net.IWebProxy> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="649d8-119">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="649d8-120">Dopo la registrazione della classe proxy, `module` può essere utilizzato per richiedere informazioni mediante il proxy supportato.</span><span class="sxs-lookup"><span data-stu-id="649d8-120">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="649d8-121">Il valore dell' `type` attributo deve corrispondere al nome della classe del modulo e al nome della corrispondente libreria di collegamento dinamico (dll).</span><span class="sxs-lookup"><span data-stu-id="649d8-121">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="649d8-122">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="649d8-122">Configuration Files</span></span>  
 <span data-ttu-id="649d8-123">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="649d8-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="649d8-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="649d8-124">Example</span></span>  
 <span data-ttu-id="649d8-125">Nell'esempio seguente viene registrata una classe proxy personalizzata.</span><span class="sxs-lookup"><span data-stu-id="649d8-125">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="649d8-126">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="649d8-126">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="649d8-127">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="649d8-127">Network Settings Schema</span></span>](index.md)
