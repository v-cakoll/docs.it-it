---
title: Utilizzo di un'attività personalizzata
ms.date: 03/30/2017
ms.assetid: 8f356419-681a-4175-ae93-878eee970249
ms.openlocfilehash: 6ca67ef7a8c4330d0182e960fc3fdcce656976a4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962218"
---
# <a name="using-a-custom-activity"></a>Utilizzo di un'attività personalizzata
Le attività che derivano da <xref:System.Activities.Activity> o le relative sottoclassi possono essere composte in flussi di lavoro più grandi o create direttamente nel codice. In questo argomento viene descritto come usare le attività personalizzate nei flussi di lavoro creati nel codice o nella finestra di progettazione.  
  
> [!NOTE]
> È possibile utilizzare attività personalizzate nello stesso progetto in cui sono definite, purché sia l'attività personalizzata che l'attività che lo utilizza vengano compilate, ad esempio caricate da un tipo di creazione di istanze generato dal processo di compilazione, se l'attività di riferimento viene caricata. in modo dinamico (ad esempio, usando ActivityXAMLServices), l'assembly a cui si fa riferimento deve essere inserito in un progetto diverso o il codice XAML generato dalla finestra di progettazione deve essere modificato manualmente per abilitare questa operazione.  
  
#### <a name="using-a-custom-activity-to-a-workflow-project"></a>Uso di un'attività personalizzata per un progetto di flusso di lavoro  
  
1. Aggiungere un riferimento dal progetto host al progetto della libreria di attività contenente l'attività personalizzata.  
  
2. Compilare la soluzione.  
  
3. Per usare l'attività personalizzata nella finestra di progettazione, individuare l'attività personalizzata nella casella degli strumenti e trascinare l'attività nell'area di progettazione.  
  
4. Per usare l'attività personalizzata nel codice, aggiungere un'istruzione Using che fa riferimento al progetto di attività personalizzata e passare una nuova istanza dell'attività a <xref:System.Activities.WorkflowInvoker.Invoke%2A>.
