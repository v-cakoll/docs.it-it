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
# <a name="startup-settings-schema"></a>Schema delle impostazioni di avvio

Le impostazioni di avvio specificano la versione di Common Language Runtime che deve essere eseguita dall'applicazione.  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<requiredRuntime>](requiredruntime-element.md)|Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime. Le applicazioni compilate con la versione di runtime 1,1 devono usare l' **\<supportedRuntime>** elemento.|  
|[\<supportedRuntime>](supportedruntime-element.md)|Specifica le versioni di Common Language Runtime supportate dall'applicazione.|  
|[\<startup>](startup-element.md)|Contiene gli **\<requiredRuntime>** **\<supportedRuntime>** elementi e.|  
  
## <a name="see-also"></a>Vedi anche

- [Schema del file di configurazione](../index.md)
- [Procedura: configurare un'app per supportare .NET Framework 4 o versioni successive](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
