---
title: Personalizzazione della fase di progettazione del flusso di lavoro
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 41be55391ae9481f6c2e4feb76443f7fb676b69d
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141933"
---
# <a name="customizing-the-workflow-design-experience"></a>Personalizzazione della fase di progettazione del flusso di lavoro

The scenarios for designing custom activities and for rehosting the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] have been greatly simplified in .NET Framework 4. Pertanto lo sviluppo e la distribuzione sono più semplici e più flessibili. The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF). In questo modo è possibile definire in modo dichiarativo gli ActivityDesigner e riallocare [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in altre applicazioni in modo semplice. In caso di riallocazione, è possibile sviluppare un editor di espressioni personalizzato per supportare IntelliSense o un dominio di espressioni semplificato. The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services. Gli ActivityDesigner personalizzati e l'albero degli elementi del modello possono essere usati per migliorare le esperienze in fase di progettazione nelle progettazioni flussi di lavoro riallocate.

## <a name="in-this-section"></a>Contenuto della sezione

 [Uso di finestre di progettazione e modelli di attività personalizzati](using-custom-activity-designers-and-templates.md)

 Viene descritto come creare nuovi ActivityDesigner e modelli personalizzati.

 [Riallocazione di Progettazione flussi di lavoro](rehosting-the-workflow-designer.md)

 Describes how to re-host the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] outside of Visual Studio and how to display validation errors.

 [Uso di un editor di espressioni personalizzato](using-a-custom-expression-editor.md)

 Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.

## <a name="reference"></a>Reference

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a>Vedere anche

- [Estensione di Windows Workflow Foundation](extend.md)
- [Finestra di progettazione](./samples/designer.md)
- [ActivityDesigner personalizzati](./samples/custom-activity-designers.md)
- [Riallocazione della finestra di progettazione](./samples/designer-rehosting.md)
