---
title: "Utilizzo dell'attività InvokeMethod"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6643550-d043-4ac7-8069-9c55ebbb4233
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5dd488a01e00af0661ee7ee110c79d2c56a0b777
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-invokemethod-activity"></a>Utilizzo dell'attività InvokeMethod
In questo esempio viene illustrato come utilizzare il <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) attività per richiamare metodi pubblici nelle classi pubbliche. Il <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) attività consente a un flusso di lavoro chiamare metodi negli oggetti, passare parametri, ottenere il valore restituito, specificare tipi per i metodi generici e indicare se il metodo è sincrono o asincrona. 
  
 È disponibile una versione non generica del <xref:System.Activities.Statements.InvokeMethod> attività in cui il valore restituito è impostato per il <xref:System.Activities.Statements.InvokeMethod.Result%2A> proprietà e una versione generica del <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) attività in cui viene restituito il valore restituito tramite il <!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> --> [ <code>System.Activities.Statements.InvokeMethod\`1.Result</code> ](https://msdn.microsoft.com/library/dd987724.aspx) proprietà di tipo `TResult`.  
  
 In questo esempio viene illustrato come chiamare diversi tipi di metodo. Nell'elenco seguente sono indicati in dettaglio i tipi di metodo illustrati nell'esempio:  
  
-   Richiamare un metodo di istanza senza parametri.  
  
-   Richiamare un metodo di istanza con due parametri (System.String e System.Int32).  
  
-   Richiamare un metodo di istanza con due parametri (System.String e System.Int32) e una matrice di parametri di tipo System.String[].  
  
-   Richiamare un metodo di istanza con due parametri (due numeri System.Int32) e un risultato di tipo System.Int32.  
  
     Il valore restituito viene associato a una variabile e stampato nella console tramite l'attività <xref:System.Activities.Statements.WriteLine>.  
  
-   Richiamare un metodo statico con due parametri (System.String e System.Int32).  
  
-   Richiamare un metodo di istanza con un parametro generico (System.String).  
  
-   Richiamare un metodo statico con due parametri generici (System.String e System.Int32).  
  
-   Richiamare un metodo di istanza che dispone di un parametro passato dal riferimento (System.String).  
  
     Il parametro a cui si fa riferimento viene associato a una variabile e stampato nella console tramite l'attività <xref:System.Activities.Statements.WriteLine>.  
  
-   Richiamare un metodo di istanza asincrono.  
  
## <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione InvokeMethodUsage.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere CTRL+F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`  
  
## <a name="see-also"></a>Vedere anche
