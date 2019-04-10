---
title: Creazione di attività del flusso di lavoro tramite la classe Activity
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 1bec10b6ae9fb43319cfb6acbf59133e1acca09c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59322316"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a>Creazione di attività del flusso di lavoro tramite la classe Activity
Il modo più semplice per creare un'attività mediante Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] consiste nel creare una classe che eredita da <xref:System.Activities.Activity> che crea la funzionalità assemblando personalizzate attività o le attività eseguite dal [predefiniti Libreria attività](net-framework-4-5-built-in-activity-library.md). In questo argomento viene illustrato come creare un'attività che consente di scrivere due messaggi nella console.

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a>Per creare un'attività personalizzata usando ActivityDesigner

1. Open Visual Studio 2012.

2. Scegliere File, Nuovo, Progetto. Selezionare **Workflow 4.0** sotto **Visual c#** nel **tipi di progetto** finestra e selezionare il **v2010** nodo. Selezionare **libreria di attività** nel **modelli** finestra. Assegnare al nuovo progetto il nome HelloActivity.

3. Aprire la nuova attività.  Trascinare un'attività <xref:System.Activities.Statements.Sequence> dalla casella degli strumenti nell'area di progettazione.

4. Trascinare un'attività <xref:System.Activities.Statements.WriteLine> nell'attività <xref:System.Activities.Statements.Sequence>. Immettere `"Hello World"` (con le virgolette) nella **testo** campo.

5. Trascinare una seconda attività <xref:System.Activities.Statements.WriteLine> nell'attività <xref:System.Activities.Statements.Sequence>, al di sotto della prima. Immettere `"Goodbye"` (con le virgolette) nella **testo** campo.
