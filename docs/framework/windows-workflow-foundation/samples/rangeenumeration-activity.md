---
title: Attività RangeEnumeration
ms.date: 03/30/2017
ms.assetid: ca5b78f4-94fa-4aa7-830d-26039ac422c8
ms.openlocfilehash: 9aa04c80f20e2d410fb49e2d07d836c8c5ab1b4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="rangeenumeration-activity"></a>Attività RangeEnumeration
In questo esempio viene illustrato come creare un'attività personalizzata che scorre una raccolta di numeri. Nella tabella seguente sono indicati in dettaglio i file principali inclusi nell'esempio.  
  
|Nome file|Descrizione|  
|---------------|-----------------|  
|RangeEnumeration.cs|Definisce un'attività personalizzata denominata `RangeEnumeration` che esegue l'override della classe <xref:System.Activities.NativeActivity> e riproduce un ciclo continuo di una serie di numeri.|  
|RangeEnumerationSample.cs|Applicazione client che usa l'attività `RangeEnumeration` per scorrere una raccolta di numeri.|  
  
 Nella tabella seguente sono indicate in dettaglio le proprietà dell'attività `RangeEnumeration`.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|Start|Integer da cui iniziare il ciclo.|  
|Interrompi|Integer in corrispondenza del quale arrestare il ciclo.|  
|Passaggio|Specifica la durata di ogni iterazione.|  
|Corpo|Specifica il codice da eseguire durante ogni iterazione.|  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione RangeEnumeration.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere CTRL+F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\RangeEnumeration`