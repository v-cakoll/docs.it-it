---
title: Configurazione della convalida di attività
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 25a4eccb-b8fc-4857-a01d-2683b6341219
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f0b7099cbae2faf53e99f73a52f4c25f42ed6834
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="configuring-activity-validation"></a>Configurazione della convalida di attività
La convalida delle attività consente agli autori e agli utenti di attività di identificare e segnalare errori nella configurazione di un'attività prima della relativa esecuzione. Windows Workflow Foundation (WF) fornisce tre tipi di convalida delle attività seguenti:  
  
-   Attributi `RequiredArgument` e `OverloadGroup`.  
  
-   Convalida basata su codice imperativo.  
  
-   Vincoli dichiarativi.  
  
 Gli attributi `RequiredArgument` e `OverloadGroup` indicano che determinati argomenti di un'attività sono obbligatori. La convalida basata su codice imperativo fornisce un modo semplice per la convalida automatica di un'attività mentre i vincoli dichiarativi abilitano la convalida dell'attività e della relativa relazione con il flusso di lavoro contenitore. Se un'attività non viene configurata correttamente in base ai requisiti di convalida, vengono restituiti errori e avvisi di convalida. Se il flusso di lavoro contenitore viene creato tramite l'utilità di progettazione del flusso di lavoro, gli eventuali errori e avvisi di convalida vengono visualizzati nella finestra di progettazione. Se il flusso di lavoro viene creato al di fuori dell'utilità di progettazione del flusso di lavoro, gli eventuali errori di convalida vengono restituiti quando il flusso di lavoro viene richiamato. Indipendentemente dalla modalità con la quale il flusso di lavoro viene creato, se con errori di convalida, un flusso di lavoro non può mai essere eseguito. Contenuto della sezione viene fornita una panoramica su questi tipi di convalida delle attività e su come viene richiamata la convalida delle attività.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Argomenti obbligatori e gruppi di overload](../../../docs/framework/windows-workflow-foundation/required-arguments-and-overload-groups.md)  
 Viene descritto come usare gli attributi `RequiredArgument` e `OverloadGroup` per fornire la convalida.  
  
 [Convalida basata su codice imperativo](../../../docs/framework/windows-workflow-foundation/imperative-code-based-validation.md)  
 Viene descritto come usare la convalida basata su codice per attività basate sugli oggetti <xref:System.Activities.CodeActivity> e <xref:System.Activities.NativeActivity>.  
  
 [Vincoli dichiarativi](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md)  
 Viene descritto come usare vincoli dichiarativi per fornire la convalida delle attività complessa.  
  
 [Richiamo della convalida di attività](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md)  
 Viene illustrato quando la convalida delle attività viene richiamata automaticamente e come richiamare la convalida in modo esplicito.  
  
## <a name="reference"></a>Riferimenti  
  
## <a name="related-sections"></a>Sezioni correlate
