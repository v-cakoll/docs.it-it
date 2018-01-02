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
ms.workload: dotnet
ms.openlocfilehash: 0536197d4cb8b30d99f514d8066e94bf84bffdf3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="startup-settings-schema"></a>Schema delle impostazioni di avvio
Le impostazioni di avvio specificano la versione di Common Language Runtime che deve essere eseguita dall'applicazione.  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<requiredRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime. Le applicazioni compilate con la versione 1.1 devono usare l'elemento **\<supportedRuntime>**.|  
|[\<supportedRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|Specifica le versioni di Common Language Runtime supportate dall'applicazione.|  
|[\<startup>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|Contiene gli elementi **\<requiredRuntime>** e **\<supportedRuntime>**.|  
  
## <a name="see-also"></a>Vedere anche  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<PaveOver> Specifica della versione di runtime da usare](http://msdn.microsoft.com/en-us/c376208d-980d-42b4-865b-fbe0d9cc97c2)
