---
title: '&lt;services&gt; di &lt;workflowRuntime&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 219a05b1-f573-45c9-849b-e86bc373b62f
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5a2535eb12d6c962de6a031c4637559b0cdb02d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltservicesgt-of-ltworkflowruntimegt"></a>&lt;services&gt; di &lt;workflowRuntime&gt;
Rappresenta una raccolta di servizi da aggiungere al motore di <xref:System.Workflow.Runtime.WorkflowRuntime>. Gli elementi sono di tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.  I servizi specificati nella raccolta verranno inizializzati dal motore di runtime del flusso di lavoro e verranno aggiunti ai relativi servizi quando verrà chiamato il costruttore <xref:System.Workflow.Runtime.WorkflowRuntime> appropriato. Pertanto, i servizi specificati nella raccolta devono seguire regole precise riguardanti le firme dei relativi costruttori. Per altre informazioni, vedere <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [File di configurazione del flusso di lavoro](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)
