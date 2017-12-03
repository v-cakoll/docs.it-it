---
title: "Creazione di attività del flusso di lavoro tramite la classe Activity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 94433d398f662a96bf046603574ad881128a2081
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a>Creazione di attività del flusso di lavoro tramite la classe Activity
Il modo più semplice per creare un'attività usando [!INCLUDE[wf](../../../includes/wf-md.md)] in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] consiste nel creare una classe che eredita da <xref:System.Activities.Activity> che crea la funzionalità assemblando personalizzato attività o attività dal [libreria attività incorporata ](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md). In questo argomento viene illustrato come creare un'attività che consente di scrivere due messaggi nella console.  
  
### <a name="to-create-a-custom-activity-using-the-activity-designer"></a>Per creare un'attività personalizzata usando ActivityDesigner  
  
1.  Aprire [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].  
  
2.  Scegliere File, Nuovo, Progetto. Selezionare **Workflow 4.0** in **Visual c#** nel **tipi di progetto** window e selezionare il **v2010** nodo. Selezionare **libreria attività** nel **modelli** finestra. Assegnare al nuovo progetto il nome HelloActivity.  
  
3.  Aprire la nuova attività.  Trascinare un'attività <xref:System.Activities.Statements.Sequence> dalla casella degli strumenti nell'area di progettazione.  
  
4.  Trascinare un'attività <xref:System.Activities.Statements.WriteLine> nell'attività <xref:System.Activities.Statements.Sequence>. Immettere `"Hello World"` (con le virgolette) nei **testo** campo.  
  
5.  Trascinare una seconda attività <xref:System.Activities.Statements.WriteLine> nell'attività <xref:System.Activities.Statements.Sequence>, al di sotto della prima. Immettere `"Goodbye"` (con le virgolette) nei **testo** campo.
