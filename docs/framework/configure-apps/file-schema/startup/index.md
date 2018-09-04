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
manager: markl
ms.openlocfilehash: 68f37e3efca784b94be90d5779c9bc402f144448
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43530334"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="97e49-102">Schema delle impostazioni di avvio</span><span class="sxs-lookup"><span data-stu-id="97e49-102">Startup Settings Schema</span></span>
<span data-ttu-id="97e49-103">Le impostazioni di avvio specificano la versione di Common Language Runtime che deve essere eseguita dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="97e49-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="97e49-104">Elemento</span><span class="sxs-lookup"><span data-stu-id="97e49-104">Element</span></span>|<span data-ttu-id="97e49-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97e49-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97e49-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="97e49-106">\<requiredRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|<span data-ttu-id="97e49-107">Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="97e49-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="97e49-108">Le applicazioni compilate con la versione 1.1 devono usare l'elemento **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="97e49-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="97e49-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="97e49-109">\<supportedRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|<span data-ttu-id="97e49-110">Specifica le versioni di Common Language Runtime supportate dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="97e49-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="97e49-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="97e49-111">\<startup></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|<span data-ttu-id="97e49-112">Contiene gli elementi **\<requiredRuntime>** e **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="97e49-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97e49-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97e49-113">See Also</span></span>  
 [<span data-ttu-id="97e49-114">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="97e49-114">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="97e49-115">\<PaveOver> Specifica della versione di runtime da usare</span><span class="sxs-lookup"><span data-stu-id="97e49-115">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](https://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
