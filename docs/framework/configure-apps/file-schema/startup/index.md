---
title: Schema delle impostazioni di avvio
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
ms.openlocfilehash: e5f9c9af64ff38e7c0f1f26ccab039261b052e30
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "61701515"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="2cc6a-102">Schema delle impostazioni di avvio</span><span class="sxs-lookup"><span data-stu-id="2cc6a-102">Startup settings schema</span></span>

<span data-ttu-id="2cc6a-103">Le impostazioni di avvio specificano la versione di Common Language Runtime che deve essere eseguita dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2cc6a-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="2cc6a-104">Elemento</span><span class="sxs-lookup"><span data-stu-id="2cc6a-104">Element</span></span>|<span data-ttu-id="2cc6a-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2cc6a-105">Description</span></span>|  
|-------------|-----------------|  
|[\<requiredRuntime>](requiredruntime-element.md)|<span data-ttu-id="2cc6a-106">Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="2cc6a-106">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="2cc6a-107">Le applicazioni compilate con la versione di runtime 1,1 devono usare l' **\<supportedRuntime>** elemento.</span><span class="sxs-lookup"><span data-stu-id="2cc6a-107">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[\<supportedRuntime>](supportedruntime-element.md)|<span data-ttu-id="2cc6a-108">Specifica le versioni di Common Language Runtime supportate dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2cc6a-108">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[\<startup>](startup-element.md)|<span data-ttu-id="2cc6a-109">Contiene gli **\<requiredRuntime>** **\<supportedRuntime>** elementi e.</span><span class="sxs-lookup"><span data-stu-id="2cc6a-109">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2cc6a-110">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="2cc6a-110">See also</span></span>

- [<span data-ttu-id="2cc6a-111">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="2cc6a-111">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2cc6a-112">Procedura: configurare un'app per supportare .NET Framework 4 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="2cc6a-112">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
