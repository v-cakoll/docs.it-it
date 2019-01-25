---
title: Schema delle impostazioni di avvio
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 12f91a1c74e85cbce0c8f641f202a181beb7412c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728908"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="ab90b-102">Schema delle impostazioni di avvio</span><span class="sxs-lookup"><span data-stu-id="ab90b-102">Startup settings schema</span></span>

<span data-ttu-id="ab90b-103">Le impostazioni di avvio specificano la versione di Common Language Runtime che deve essere eseguita dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ab90b-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="ab90b-104">Elemento</span><span class="sxs-lookup"><span data-stu-id="ab90b-104">Element</span></span>|<span data-ttu-id="ab90b-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ab90b-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ab90b-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="ab90b-106">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="ab90b-107">Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ab90b-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="ab90b-108">Le applicazioni compilate con la versione 1.1 devono usare l'elemento **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="ab90b-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="ab90b-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="ab90b-109">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="ab90b-110">Specifica le versioni di Common Language Runtime supportate dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ab90b-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="ab90b-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="ab90b-111">\<startup></span></span>](startup-element.md)|<span data-ttu-id="ab90b-112">Contiene gli elementi **\<requiredRuntime>** e **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="ab90b-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab90b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab90b-113">See also</span></span>

- [<span data-ttu-id="ab90b-114">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="ab90b-114">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ab90b-115">Procedura: Configurare un'app per supportare .NET Framework 4 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="ab90b-115">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
