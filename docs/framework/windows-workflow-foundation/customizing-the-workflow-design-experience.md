---
title: Personalizzazione della fase di progettazione del flusso di lavoro
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 27be398d874747b65ae051224070d3f40f1fbbb0
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715130"
---
# <a name="customizing-the-workflow-design-experience"></a>Personalizzazione della fase di progettazione del flusso di lavoro

Gli scenari per la progettazione di attività personalizzate e per la riallocazione del Progettazione flussi di lavoro di Windows sono stati semplificati in .NET Framework 4. Pertanto lo sviluppo e la distribuzione sono più semplici e più flessibili. Il cambiamento di infrastruttura principale è costituito dal fatto che il nuovo modello di programmazione dell'ActivityDesigner è basato su Windows Presentation Foundation (WPF). In questo modo è possibile definire in modo dichiarativo gli ActivityDesigner e riallocare le Progettazione flussi di lavoro in altre applicazioni con una procedura comparativa facile. In caso di riallocazione, è possibile sviluppare un editor di espressioni personalizzato per supportare IntelliSense o un dominio di espressioni semplificato. L'integrazione con Windows Communication Foundation (WCF) è diventata più semplice grazie all'uso dei servizi del flusso di lavoro. Gli ActivityDesigner personalizzati e l'albero degli elementi del modello possono essere usati per migliorare le esperienze in fase di progettazione nelle progettazioni flussi di lavoro riallocate.

## <a name="in-this-section"></a>Contenuto della sezione

 [Uso di finestre di progettazione e modelli di attività personalizzati](using-custom-activity-designers-and-templates.md)

 Viene descritto come creare nuovi ActivityDesigner e modelli personalizzati.

 [Riallocazione di Progettazione flussi di lavoro](rehosting-the-workflow-designer.md)

 Viene descritto come riospitare l'Progettazione flussi di lavoro Windows all'esterno di Visual Studio e come visualizzare gli errori di convalida.

 [Uso di un editor di espressioni personalizzato](using-a-custom-expression-editor.md)

 Viene descritto come implementare un editor di espressioni personalizzato da usare con le finestre di progettazione dei flussi di lavoro riallocate all'esterno di Visual Studio 2010.

## <a name="reference"></a>Reference

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a>Vedere anche

- [Estensione di Windows Workflow Foundation](extend.md)
- [Finestra di progettazione](./samples/designer.md)
- [ActivityDesigner personalizzati](./samples/custom-activity-designers.md)
- [Riallocazione della finestra di progettazione](./samples/designer-rehosting.md)
