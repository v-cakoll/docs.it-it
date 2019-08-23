---
title: Elemento <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: 0e09ec49024b769c516fd97085904781f64b4486
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921242"
---
# <a name="configuration-element"></a><span data-ttu-id="abcfe-102">\<Configuration >-elemento</span><span class="sxs-lookup"><span data-stu-id="abcfe-102">\<configuration> element</span></span>

<span data-ttu-id="abcfe-103">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="abcfe-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

<span data-ttu-id="abcfe-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="abcfe-104">**\<configuration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="abcfe-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="abcfe-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="abcfe-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="abcfe-106">Attributes</span></span>

<span data-ttu-id="abcfe-107">Nessuna</span><span class="sxs-lookup"><span data-stu-id="abcfe-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="abcfe-108">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="abcfe-108">Parent element</span></span>

<span data-ttu-id="abcfe-109">Nessuna</span><span class="sxs-lookup"><span data-stu-id="abcfe-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="abcfe-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="abcfe-110">Child elements</span></span>

|     | <span data-ttu-id="abcfe-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="abcfe-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="abcfe-112"> **\<assemblyBinding>** </span><span class="sxs-lookup"><span data-stu-id="abcfe-112">**\<assemblyBinding>**</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="abcfe-113">Specifica i criteri di associazione degli assembly al livello di configurazione.</span><span class="sxs-lookup"><span data-stu-id="abcfe-113">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="abcfe-114">Schema delle impostazioni del > di avvio  **\<** </span><span class="sxs-lookup"><span data-stu-id="abcfe-114">**\<startup>** Settings Schema</span></span>](./startup/index.md) | <span data-ttu-id="abcfe-115">Tutti gli elementi nello schema delle impostazioni di avvio.</span><span class="sxs-lookup"><span data-stu-id="abcfe-115">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="abcfe-116">Schema delle impostazioni del > di runtime  **\<** </span><span class="sxs-lookup"><span data-stu-id="abcfe-116">**\<runtime>** Settings Schema</span></span>](./runtime/index.md) | <span data-ttu-id="abcfe-117">Tutti gli elementi nello schema delle impostazioni di Runtime.</span><span class="sxs-lookup"><span data-stu-id="abcfe-117">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="abcfe-118">[Schema delle impostazioni di **> System. Runtime. Remoting \<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="abcfe-118">[**\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="abcfe-119">Tutti gli elementi nello schema delle impostazioni remote.</span><span class="sxs-lookup"><span data-stu-id="abcfe-119">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="abcfe-120">Schema delle impostazioni di **System .net > \<** </span><span class="sxs-lookup"><span data-stu-id="abcfe-120">**\<system.Net>** Settings Schema</span></span>](./network/index.md) | <span data-ttu-id="abcfe-121">Tutti gli elementi nello schema delle impostazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="abcfe-121">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="abcfe-122">Schema delle impostazioni > cryptographySettings  **\<** </span><span class="sxs-lookup"><span data-stu-id="abcfe-122">**\<cryptographySettings>** Settings Schema</span></span>](./cryptography/index.md) | <span data-ttu-id="abcfe-123">Tutti gli elementi nello schema delle impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="abcfe-123">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="abcfe-124">Schema delle sezioni di > di configurazione  **\<** </span><span class="sxs-lookup"><span data-stu-id="abcfe-124">**\<configuration>** Sections Schema</span></span>](configuration-sections-schema.md) | <span data-ttu-id="abcfe-125">Tutti gli elementi nello schema delle impostazioni della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="abcfe-125">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="abcfe-126">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="abcfe-126">Trace and Debug Settings Schema</span></span>](./trace-debug/index.md) | <span data-ttu-id="abcfe-127">Tutti gli elementi nello schema delle impostazioni di traccia e debug.</span><span class="sxs-lookup"><span data-stu-id="abcfe-127">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="abcfe-128">[Schema delle impostazioni di configurazione di ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="abcfe-128">[ASP.NET Configuration Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="abcfe-129">Tutti gli elementi nello schema di configurazione di ASP.NET, che include elementi per la configurazione di applicazioni e siti Web di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="abcfe-129">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="abcfe-130">Utilizzato nei file *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="abcfe-130">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="abcfe-131">[Schema delle impostazioni di > WebServices  **\<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="abcfe-131">[**\<webServices>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="abcfe-132">Tutti gli elementi nello schema delle impostazioni dei servizi Web.</span><span class="sxs-lookup"><span data-stu-id="abcfe-132">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="abcfe-133">Schema delle impostazioni Web</span><span class="sxs-lookup"><span data-stu-id="abcfe-133">Web Settings Schema</span></span>](./web/index.md) | <span data-ttu-id="abcfe-134">Tutti gli elementi nello schema delle impostazioni Web, che include gli elementi per la configurazione del funzionamento di ASP.NET con un'applicazione host, come IIS.</span><span class="sxs-lookup"><span data-stu-id="abcfe-134">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="abcfe-135">Utilizzato nei file *ASPNET. config* .</span><span class="sxs-lookup"><span data-stu-id="abcfe-135">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="abcfe-136">Note</span><span class="sxs-lookup"><span data-stu-id="abcfe-136">Remarks</span></span>

<span data-ttu-id="abcfe-137">Ogni file di configurazione deve contenere esattamente un  **\<elemento Configuration >** .</span><span class="sxs-lookup"><span data-stu-id="abcfe-137">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="abcfe-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="abcfe-138">See also</span></span>

- [<span data-ttu-id="abcfe-139">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="abcfe-139">Configuration file schema for the .NET Framework</span></span>](index.md)
