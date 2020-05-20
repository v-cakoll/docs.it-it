---
title: Progettazione e implementazione di attività personalizzate
description: Questo articolo fornisce le risorse per la creazione di attività personalizzate in Workflow Foundation creando attività composite o creando nuovi tipi di attività.
ms.date: 03/30/2017
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
ms.openlocfilehash: 9c184bff9518bb5581f3bf4cd408db224736192b
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419993"
---
# <a name="designing-and-implementing-custom-activities"></a>Progettazione e implementazione di attività personalizzate
Le attività personalizzate in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] vengono create assemblando le attività fornite dal sistema nelle attività composte o creando nuovi tipi che derivano dall'oggetto <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> o <xref:System.Activities.NativeActivity>. Contenuto della sezione viene illustrato come creare attività personalizzate con uno dei metodi.  
  
> [!IMPORTANT]
> Le attività personalizzate vengono visualizzate per impostazione predefinita nella finestra di progettazione del flusso di lavoro come un semplice rettangolo con il nome dell'attività. Per fornire una rappresentazione visiva personalizzata dell'attività nella finestra di progettazione del flusso di lavoro è inoltre necessario creare una finestra di progettazione personalizzata. Per altre informazioni, vedere [uso di ActivityDesigner e modelli personalizzati](using-custom-activity-designers-and-templates.md).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Opzioni di creazione di attività](activity-authoring-options-in-wf.md)  
 Viene illustrata la creazione di stili disponibili in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].  
  
 [Uso di un'attività personalizzata](using-a-custom-activity.md)  
 Viene descritto come aggiungere un'attività personalizzata a un progetto flusso di lavoro.  
  
  [Creazione di attività asincrone](creating-asynchronous-activities-in-wf.md)  
 Viene illustrato come creare attività asincrone.  
  
 [Configurazione della convalida di attività](configuring-activity-validation.md)  
 Viene illustrato come usare la convalida delle attività per identificare e segnalare errori nella configurazione di un'attività prima della relativa esecuzione.  
  
 [Creazione di un'attività in fase di esecuzione](creating-an-activity-at-runtime-with-dynamicactivity.md)  
 Viene illustrato come creare attività in fase di esecuzione usando <xref:System.Activities.DynamicActivity>.  
  
 [Proprietà di esecuzione del flusso di lavoro](workflow-execution-properties.md)  
 Viene illustrato come usare le proprietà di esecuzione del flusso di lavoro per aggiungere proprietà specifiche del contesto all'ambiente di un'attività.  
  
 [Uso di delegati di attività](using-activity-delegates.md)  
 Viene illustrato come creare e usare attività che contengono delegati di attività.
  
 [Uso di estensioni di attività](using-activity-extensions.md)  
 Viene descritto come creare e usare le estensioni di attività.  
  
 [Utilizzo di feed OData da un flusso di lavoro](consuming-odata-feeds-from-a-workflow.md)  
 Vengono descritti i diversi metodi per chiamare WCF Data Services da un flusso di lavoro.  
  
 [Ambito e visibilità della definizione di attività](activity-definition-scoping-and-visibility.md)  
 Vengono descritte le opzioni e le regole per definire l'ambito dei dati e la visibilità dei membri per le attività.
