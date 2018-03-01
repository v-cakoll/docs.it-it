---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location:
- Microsoft.VisualStudio.Activities.dll
api_type:
- Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4c50d9754b71386e6809d46cd9666987a704fbf7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a>Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
Crea un'istanza di [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) classe.  
  
## <a name="syntax"></a>Sintassi  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
#### <a name="parameters"></a>Parametri  
  
## <a name="parameter-values"></a>Valori parametro  
 *operationDescription*  
  
 Descrive l'operazione da eseguire nell'attività del flusso di lavoro che deve essere generata, includendo il nome dell'operazione, il tipo restituito e le informazioni sul parametro. Il valore di questo parametro non deve essere **null**. Dovrebbe descrivere un'operazione sincrona che utilizza un contratto di messaggio e accetta un argomento con un messaggio. Se queste condizioni non vengono soddisfatte, il risultato runtime dell'utilizzo del costruttore e gli altri metodi di questa classe non vengono definiti.  
  
 *configurationName*  
  
 Specifica il nome della configurazione dell'endpoint. Il valore di questo parametro non deve essere **null** o vuoto. Se queste condizioni non vengono soddisfatte, il risultato runtime dell'utilizzo del costruttore e gli altri metodi di questa classe non vengono definiti.  
  
 *proxyNamespace*  
  
 Specifica lo spazio dei nomi del servizio per l'operazione. Il valore di questo parametro non deve essere **null** o vuoto. Se queste condizioni non vengono soddisfatte, il risultato runtime dell'utilizzo del costruttore e gli altri metodi di questa classe non vengono definiti.  
  
## <a name="see-also"></a>Vedere anche  
 [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
