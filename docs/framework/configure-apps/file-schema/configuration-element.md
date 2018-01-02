---
title: '&lt;configurazione&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 3874a613879d099ede4968b5bce349aefa015a38
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="configuration-element"></a><span data-ttu-id="c23bb-102">\<configurazione > elemento</span><span class="sxs-lookup"><span data-stu-id="c23bb-102">\<configuration> element</span></span>

<span data-ttu-id="c23bb-103">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c23bb-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

<span data-ttu-id="c23bb-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="c23bb-104">**\<configuration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c23bb-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c23bb-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="c23bb-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="c23bb-106">Attributes</span></span>

<span data-ttu-id="c23bb-107">nessuno</span><span class="sxs-lookup"><span data-stu-id="c23bb-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="c23bb-108">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="c23bb-108">Parent element</span></span>

<span data-ttu-id="c23bb-109">nessuno</span><span class="sxs-lookup"><span data-stu-id="c23bb-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="c23bb-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c23bb-110">Child elements</span></span>

|     | <span data-ttu-id="c23bb-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c23bb-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c23bb-112">**\<assemblyBinding >**</span><span class="sxs-lookup"><span data-stu-id="c23bb-112">**\<assemblyBinding>**</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="c23bb-113">Specifica i criteri di associazione degli assembly al livello di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c23bb-113">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="c23bb-114">**\<avvio >** Schema delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="c23bb-114">**\<startup>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/startup/index.md) | <span data-ttu-id="c23bb-115">Tutti gli elementi nello schema delle impostazioni di avvio.</span><span class="sxs-lookup"><span data-stu-id="c23bb-115">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="c23bb-116">**\<runtime >** Schema delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="c23bb-116">**\<runtime>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/runtime/index.md) | <span data-ttu-id="c23bb-117">Tutti gli elementi nello schema delle impostazioni di runtime.</span><span class="sxs-lookup"><span data-stu-id="c23bb-117">All elements in the runtime settings schema.</span></span> |
| [<span data-ttu-id="c23bb-118">**\<System.Runtime.Remoting >** Schema delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="c23bb-118">**\<system.runtime.remoting>** Settings Schema</span></span>](http://msdn.microsoft.com/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) | <span data-ttu-id="c23bb-119">Tutti gli elementi nello schema delle impostazioni di comunicazione remota.</span><span class="sxs-lookup"><span data-stu-id="c23bb-119">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="c23bb-120">**\<system.Net >** Schema delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="c23bb-120">**\<system.Net>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/network/index.md) | <span data-ttu-id="c23bb-121">Tutti gli elementi nello schema delle impostazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="c23bb-121">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="c23bb-122">**\<cryptographySettings >** Schema delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="c23bb-122">**\<cryptographySettings>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | <span data-ttu-id="c23bb-123">Tutti gli elementi nello schema delle impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="c23bb-123">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="c23bb-124">**\<configurazione >** Schema delle sezioni</span><span class="sxs-lookup"><span data-stu-id="c23bb-124">**\<configuration>** Sections Schema</span></span>](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | <span data-ttu-id="c23bb-125">Tutti gli elementi nello schema delle impostazioni di sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c23bb-125">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="c23bb-126">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="c23bb-126">Trace and Debug Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | <span data-ttu-id="c23bb-127">Tutti gli elementi nello schema delle impostazioni di traccia e debug.</span><span class="sxs-lookup"><span data-stu-id="c23bb-127">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="c23bb-128">[Schema delle impostazioni di configurazione ASP.NET](https://msdn.microsoft.com/library/b5ysx397(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="c23bb-128">[ASP.NET Configuration Settings Schema](https://msdn.microsoft.com/library/b5ysx397(v=vs.100).aspx)</span></span> | <span data-ttu-id="c23bb-129">Tutti gli elementi nello schema di configurazione ASP.NET, che include gli elementi per la configurazione di applicazioni e siti Web di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c23bb-129">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="c23bb-130">Utilizzato *Web. config* file.</span><span class="sxs-lookup"><span data-stu-id="c23bb-130">Used in *Web.config* files.</span></span> |
| [<span data-ttu-id="c23bb-131">**\<webServices >** Schema delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="c23bb-131">**\<webServices>** Settings Schema</span></span>](http://msdn.microsoft.com/f84d6d55-1add-4eb7-ae46-33df5833ea2e) | <span data-ttu-id="c23bb-132">Tutti gli elementi nello schema delle impostazioni di servizi Web.</span><span class="sxs-lookup"><span data-stu-id="c23bb-132">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="c23bb-133">Schema delle impostazioni Web</span><span class="sxs-lookup"><span data-stu-id="c23bb-133">Web Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/web/index.md) | <span data-ttu-id="c23bb-134">Tutti gli elementi nello schema delle impostazioni Web, che include gli elementi per la configurazione del funzionamento di ASP.NET con un'applicazione host, come IIS.</span><span class="sxs-lookup"><span data-stu-id="c23bb-134">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="c23bb-135">Utilizzato *ASPNET* file.</span><span class="sxs-lookup"><span data-stu-id="c23bb-135">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="c23bb-136">Note</span><span class="sxs-lookup"><span data-stu-id="c23bb-136">Remarks</span></span>

<span data-ttu-id="c23bb-137">Ogni file di configurazione deve contenere esattamente un  **\<configurazione >** elemento.</span><span class="sxs-lookup"><span data-stu-id="c23bb-137">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="c23bb-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c23bb-138">See also</span></span>

[<span data-ttu-id="c23bb-139">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c23bb-139">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
