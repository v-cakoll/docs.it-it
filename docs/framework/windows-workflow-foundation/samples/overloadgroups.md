---
title: OverloadGroups
ms.date: 03/30/2017
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
ms.openlocfilehash: 489d27e05c96d3b3893052254a879d1c9d75788c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515623"
---
# <a name="overloadgroups"></a>OverloadGroups
Questo esempio è costituito da un'attività (`CreateLocation`) che dispone di due caratteristiche interessanti:  
  
1.  Presenta alcuni argomenti obbligatori e alcuni facoltativi.  
  
2.  Consente all'utente di scegliere di fornire uno di due set diversi di argomenti.  
  
 Questi comportamenti sono portati a termine usando queste due funzionalità:  
  
-   `[isRequired]` convalida l'assegnazione di un'attività specifica da parte di una proprietà e, in caso contrario, genera un'eccezione.  
  
-   `[OverloadGroup]` raggruppa un set di argomenti, in modo che l'utente dell'attività possa scegliere quale usare. L'utente non può usare argomenti da gruppi di overload diversi nella stessa istanza.  
  
 Dopo avere configurato flussi di lavoro diversi, chiamare il metodo <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> che restituisce una raccolta <xref:System.Activities.Validation.ValidationResults> di oggetti <xref:System.Activities.Validation.Constraint>. Stampare gli oggetti <xref:System.Activities.Validation.Constraint> nella console.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Aprire il **OverloadGroups.sln** soluzione di esempio [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compilare ed eseguire la soluzione.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`
