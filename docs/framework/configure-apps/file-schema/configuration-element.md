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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "69921242"
---
# <a name="configuration-element"></a><span data-ttu-id="1f4f2-102">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="1f4f2-102">\<configuration> element</span></span>

<span data-ttu-id="1f4f2-103">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

**\<configuration>**

## <a name="syntax"></a><span data-ttu-id="1f4f2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1f4f2-104">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="1f4f2-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="1f4f2-105">Attributes</span></span>

<span data-ttu-id="1f4f2-106">nessuno</span><span class="sxs-lookup"><span data-stu-id="1f4f2-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="1f4f2-107">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="1f4f2-107">Parent element</span></span>

<span data-ttu-id="1f4f2-108">nessuno</span><span class="sxs-lookup"><span data-stu-id="1f4f2-108">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="1f4f2-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1f4f2-109">Child elements</span></span>

|     | <span data-ttu-id="1f4f2-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1f4f2-110">Description</span></span> |
| --- | ----------- |
| [**\<assemblyBinding>**](assemblybinding-element-for-configuration.md) | <span data-ttu-id="1f4f2-111">Specifica i criteri di associazione degli assembly al livello di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-111">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="1f4f2-112">**\<startup>** Schema delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="1f4f2-112">**\<startup>** Settings Schema</span></span>](./startup/index.md) | <span data-ttu-id="1f4f2-113">Tutti gli elementi nello schema delle impostazioni di avvio.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-113">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="1f4f2-114">**\<runtime>** Schema delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="1f4f2-114">**\<runtime>** Settings Schema</span></span>](./runtime/index.md) | <span data-ttu-id="1f4f2-115">Tutti gli elementi nello schema delle impostazioni di Runtime.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-115">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="1f4f2-116">[**\<system.runtime.remoting>** Schema delle impostazioni](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1f4f2-116">[**\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="1f4f2-117">Tutti gli elementi nello schema delle impostazioni remote.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-117">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="1f4f2-118">**\<system.Net>** Schema delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="1f4f2-118">**\<system.Net>** Settings Schema</span></span>](./network/index.md) | <span data-ttu-id="1f4f2-119">Tutti gli elementi nello schema delle impostazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-119">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="1f4f2-120">**\<cryptographySettings>** Schema delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="1f4f2-120">**\<cryptographySettings>** Settings Schema</span></span>](./cryptography/index.md) | <span data-ttu-id="1f4f2-121">Tutti gli elementi nello schema delle impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-121">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="1f4f2-122">**\<configuration>** Schema delle sezioni</span><span class="sxs-lookup"><span data-stu-id="1f4f2-122">**\<configuration>** Sections Schema</span></span>](configuration-sections-schema.md) | <span data-ttu-id="1f4f2-123">Tutti gli elementi nello schema delle impostazioni della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-123">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="1f4f2-124">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="1f4f2-124">Trace and Debug Settings Schema</span></span>](./trace-debug/index.md) | <span data-ttu-id="1f4f2-125">Tutti gli elementi nello schema delle impostazioni di traccia e debug.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-125">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="1f4f2-126">[Schema delle impostazioni di configurazione di ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1f4f2-126">[ASP.NET Configuration Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="1f4f2-127">Tutti gli elementi nello schema di configurazione di ASP.NET, che include elementi per la configurazione di applicazioni e siti Web di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-127">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="1f4f2-128">Utilizzato nei file *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="1f4f2-128">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="1f4f2-129">[**\<webServices>** Schema delle impostazioni](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1f4f2-129">[**\<webServices>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="1f4f2-130">Tutti gli elementi nello schema delle impostazioni dei servizi Web.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-130">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="1f4f2-131">Schema delle impostazioni Web</span><span class="sxs-lookup"><span data-stu-id="1f4f2-131">Web Settings Schema</span></span>](./web/index.md) | <span data-ttu-id="1f4f2-132">Tutti gli elementi nello schema delle impostazioni Web, che include gli elementi per la configurazione del funzionamento di ASP.NET con un'applicazione host, come IIS.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-132">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="1f4f2-133">Utilizzato nei file *ASPNET. config* .</span><span class="sxs-lookup"><span data-stu-id="1f4f2-133">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="1f4f2-134">Commenti</span><span class="sxs-lookup"><span data-stu-id="1f4f2-134">Remarks</span></span>

<span data-ttu-id="1f4f2-135">Ogni file di configurazione deve contenere esattamente un **\<configuration>** elemento.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-135">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f4f2-136">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="1f4f2-136">See also</span></span>

- [<span data-ttu-id="1f4f2-137">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1f4f2-137">Configuration file schema for the .NET Framework</span></span>](index.md)
