---
title: Tipi di vincoli
ms.date: 03/30/2017
ms.assetid: b6b246e6-1130-4698-9625-c5c42abcbfed
ms.openlocfilehash: 202a2c7b3a3fc400552e42c8606457964af66af2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506612"
---
# <a name="constraint-types"></a>Tipi di vincoli
In questo esempio vengono illustrate due modalità diverse per applicare vincoli a un flusso di lavoro: uno dall'interno dell'attività (compilazione) e un altro dall'esterno (criteri). In questo scenario, un autore di attività (di una società di software di terze parti) desidera convalidare la relazione tra due argomenti. In questo caso, il costo deve essere minore o uguale al prezzo. Si tratta di un vincolo di compilazione di convalida generale.  
  
 Il proprietario di un negozio desidera aggiungere alcune convalide a questa attività generica. In tal caso, desidera che la maggior parte dei prodotti abbia un prezzo pari ad almeno $9.99. Pertanto, usa un vincolo di criteri che si trova nella parte superiore dell'attività `CreateProduct`.  
  
 Nell'esempio:  
  
 L'autore di attività (compilazione) deve:  
  
-   Creare un vincolo (`PriceGreaterThanCost`), ovvero il punto in cui far risiedere l'intera logica di convalida.  
  
-   Eseguire l'override del metodo `System.Activities.CodeActivity.OnGetConstraints()` e aggiungere il vincolo (`PriceGreaterThanCost`) ai vincoli <xref:System.Collections.IList>.  
  
 L'autore del flusso di lavoro (criteri) deve:  
  
-   Creare un flusso di lavoro con un'istanza dell'attività da convalidare (`CreateProduct`).  
  
-   Creare un vincolo (`MaxPrice`),  
  
-   Creare un'istanza <xref:System.Activities.Validation.ValidationSettings> (`validationSettings`) e aggiungere il vincolo (`MaxPrice`) alla raccolta `AdditionalConstraints`. A questo punto l'autore del flusso di lavoro può aggiungere vincoli di criteri a qualsiasi attività, ad esempio Sequence o Parallel.  
  
-   Chiamare il metodo <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, che restituisce una raccolta <xref:System.Activities.Validation.ValidationResults> di oggetti <xref:System.Activities.Validation.ValidationError>.  
  
-   (Facoltativo) Stampare gli oggetti <xref:System.Activities.Validation.ValidationError>.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Aprire la soluzione di esempio ConstraintTypes.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compilare ed eseguire la soluzione.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Validation\ConstraintLibrary`