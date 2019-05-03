---
title: Instance Completion Action
ms.date: 03/30/2017
ms.assetid: 90cc99d2-9fef-42fd-bcbf-a56917993721
ms.openlocfilehash: 646015fbcdb7c734ae8584c7ca3979d64b81339f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791118"
---
# <a name="instance-completion-action"></a>Instance Completion Action
Il **Instance Completion Action** proprietà la Store di istanza del flusso di lavoro SQL consente di specificare se i dati e i metadati delle istanze del flusso di lavoro vengono eliminati dal database di persistenza dopo il completamento delle istanze. I valori consentiti per questa proprietà sono **DeleteAll** e **DeleteNothing**. Nell'elenco seguente vengono descritte queste opzioni:  
  
- **DeleteAll (impostazione predefinita).** Se il valore della proprietà viene impostato su DeleteAll, i dati e i metadati delle istanze del flusso di lavoro vengono eliminati dal database di persistenza dopo il completamento delle istanze.  
  
- **DeleteNothing.** Se il valore della proprietà viene impostato su DeleteNothing, i dati e i metadati delle istanze del flusso di lavoro vengono mantenuti nel database di persistenza anche dopo il completamento delle istanze.  
  
    > [!CAUTION]
    >  Il mantenimento delle informazioni sullo stato delle istanze dopo il relativo completamento comporta l'aumento delle dimensioni del database di persistenza. Se le dimensioni del database aumentano, le operazioni del database eseguite dal sottosistema di persistenza richiedono più tempo, pertanto è necessario eliminare periodicamente le informazioni sullo stato delle istanze dal database di persistenza affinché i servizi vengano eseguiti in base alle proprie esigenze di prestazione.
