---
title: Convalida di attività esterna
ms.date: 03/30/2017
ms.assetid: 49619f59-9819-484a-bcd8-5596308e8551
ms.openlocfilehash: 1ceb1d2b2f7e8926479fa4c53cfb82a5cdb3a83f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517800"
---
# <a name="external-activity-validation"></a>Convalida di attività esterna
In questo esempio viene illustrato come aggiungere la logica di convalida a un'attività incorporata di cui l'utente non è l'autore. La logica di convalida consiste nell'imporre che tutte le attività <xref:System.Activities.Statements.If> presenti nel flusso di lavoro dispongano d un proprio set di proprietà <xref:System.Activities.Statements.If.Then%2A> o <xref:System.Activities.Statements.If.Else%2A>. La logica di convalida include inoltre la verifica che tutte le attività <xref:System.Activities.Statements.Pick> presenti nel flusso di lavoro dispongano di più di un ramo e, in caso contrario, che venga generato un avviso.  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 Questo esempio crea un flusso di lavoro con un'istanza di ogni attività da convalidare: l'attività <xref:System.Activities.Statements.If> e l'attività <xref:System.Activities.Statements.Pick>. Per ogni comportamento di convalida viene creato <xref:System.Activities.Validation.Constraint>. I vincoli creati in questo esempio sono `ConstraintError_IfShouldHaveThenOrElse` e `ConstraintWarning_PickHasOneBranch`. Questi vincoli vengono quindi aggiunti alla raccolta `AdditionalConstraints` di un'istanza di <xref:System.Activities.Validation.ValidationSettings>. Infine, viene chiamato il metodo `static`<xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> di <xref:System.Activities.Validation.ActivityValidationServices> per convalidare le attività nel flusso di lavoro e i risultati della convalida vengono stampati nella console.  
  
> [!NOTE]
>  È possibile aggiungere vincoli di criteri a qualsiasi attività. Ad esempio, è possibile aggiungere un vincolo di criteri a un'attività <xref:System.Activities.Statements.Sequence> o <xref:System.Activities.Statements.Parallel>.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione ExternalActivityValidation.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere CTRL+F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ExternalActivityValidation`