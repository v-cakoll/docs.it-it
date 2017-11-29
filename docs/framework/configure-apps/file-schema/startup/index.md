---
title: Schema delle impostazioni di avvio
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 61ea6d0c974683e73e835720cff48ff84169217e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="startup-settings-schema"></a><span data-ttu-id="92276-102">Schema delle impostazioni di avvio</span><span class="sxs-lookup"><span data-stu-id="92276-102">Startup Settings Schema</span></span>
<span data-ttu-id="92276-103">Le impostazioni di avvio specificano la versione di Common Language Runtime che deve essere eseguita dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="92276-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="92276-104">Elemento</span><span class="sxs-lookup"><span data-stu-id="92276-104">Element</span></span>|<span data-ttu-id="92276-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92276-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92276-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="92276-106">\<requiredRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|<span data-ttu-id="92276-107">Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="92276-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="92276-108">Le applicazioni compilate con la versione 1.1 devono usare l'elemento **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="92276-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="92276-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="92276-109">\<supportedRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|<span data-ttu-id="92276-110">Specifica le versioni di Common Language Runtime supportate dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="92276-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="92276-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="92276-111">\<startup></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|<span data-ttu-id="92276-112">Contiene gli elementi **\<requiredRuntime>** e **\<supportedRuntime>**.</span><span class="sxs-lookup"><span data-stu-id="92276-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="92276-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92276-113">See Also</span></span>  
 [<span data-ttu-id="92276-114">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="92276-114">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="92276-115">\<PaveOver> Specifica della versione di runtime da usare</span><span class="sxs-lookup"><span data-stu-id="92276-115">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](http://msdn.microsoft.com/en-us/c376208d-980d-42b4-865b-fbe0d9cc97c2)
