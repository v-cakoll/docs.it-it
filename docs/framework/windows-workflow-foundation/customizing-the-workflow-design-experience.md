---
title: Personalizzazione della fase di progettazione del flusso di lavoro
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9916e30812e167e108a1ca9b958aa6d15fbd1f41
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="customizing-the-workflow-design-experience"></a>Personalizzazione della fase di progettazione del flusso di lavoro
In [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] sono stati semplificati gli scenari per progettare le attività personalizzate e riallocare [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]. Pertanto lo sviluppo e la distribuzione sono più semplici e più flessibili. La modifica infrastrutturale principale prevede che il nuovo modello di programmazione dell'ActivityDesigner sia compilato in base a [!INCLUDE[avalon1](../../../includes/avalon1-md.md)]. In questo modo è possibile definire in modo dichiarativo gli ActivityDesigner e riallocare [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in altre applicazioni in modo semplice. In caso di riallocazione, è possibile sviluppare un editor di espressioni personalizzato per supportare IntelliSense o un dominio di espressioni semplificato. L'integrazione con [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] è diventata più semplice grazie all'utilizzo dei servizi flusso di lavoro. Gli ActivityDesigner personalizzati e l'albero degli elementi del modello possono essere usati per migliorare le esperienze in fase di progettazione nelle progettazioni flussi di lavoro riallocate.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Uso di finestre di progettazione e modelli di attività personalizzati](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md)  
 Viene descritto come creare nuovi ActivityDesigner e modelli personalizzati.  
  
 [Riallocazione di Progettazione flussi di lavoro](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 Viene descritto come riallocare [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] all'esterno di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] e come visualizzare gli errori di convalida.  
  
 [Uso di un editor di espressioni personalizzato](../../../docs/framework/windows-workflow-foundation/using-a-custom-expression-editor.md)  
 Viene descritto come implementare un editor di espressioni personalizzato da usare con le progettazioni flussi di lavoro riallocate all'esterno di [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
## <a name="reference"></a>Riferimento  
 <xref:System.Activities.Presentation.ActivityDesigner>  
  
## <a name="see-also"></a>Vedere anche  
 [Estensione di Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/extend.md)  
 [Finestra di progettazione](../../../docs/framework/windows-workflow-foundation/samples/designer.md)  
 [Gli ActivityDesigner personalizzati](../../../docs/framework/windows-workflow-foundation/samples/custom-activity-designers.md)  
 [Riallocazione della finestra di progettazione](../../../docs/framework/windows-workflow-foundation/samples/designer-rehosting.md)
