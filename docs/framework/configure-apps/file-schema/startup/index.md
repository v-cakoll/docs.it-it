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
# <a name="startup-settings-schema"></a>Schema delle impostazioni di avvio

Le impostazioni di avvio specificano la versione di Common Language Runtime che deve essere eseguita dall'applicazione.  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<requiredRuntime>](requiredruntime-element.md)|Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime. Le applicazioni compilate con la versione 1.1 devono usare l'elemento **\<supportedRuntime>**.|  
|[\<supportedRuntime>](supportedruntime-element.md)|Specifica le versioni di Common Language Runtime supportate dall'applicazione.|  
|[\<startup>](startup-element.md)|Contiene gli elementi **\<requiredRuntime>** e **\<supportedRuntime>**.|  
  
## <a name="see-also"></a>Vedere anche

- [Schema dei file di configurazione](../index.md)
- [Procedura: Configurare un'app per supportare .NET Framework 4 o versioni successive](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
