---
title: InvokeMethod
ms.date: 03/30/2017
ms.assetid: 04988eb3-65f8-456d-b1bd-509f5d05a57c
ms.openlocfilehash: 12d028515c34c0e3593c90b81a5589fb05f36b82
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="invokemethod"></a>InvokeMethod
In questo esempio vengono illustrate le diverse modalità di utilizzo dell'attività <xref:System.Activities.Statements.InvokeMethod> per richiamare metodi di una classe.  
  
 Un metodo appartiene a una classe e rappresenta un set di operazioni autonomo. L'attività <xref:System.Activities.Statements.InvokeMethod> consente di chiamare metodi in base a oggetti o tipi, passare parametri e ottenere il valore restituito. È possibile richiamare i metodi in modo sincrono o asincrono.  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 In questo esempio viene usata l'attività <xref:System.Activities.Statements.InvokeMethod> per eseguire gli scenari seguenti:  
  
1.  Richiamare un metodo di istanza senza parametri.  
  
2.  Richiamare un metodo di istanza con due parametri (<xref:System.String> e <xref:System.Int32>).  
  
3.  Richiamare un metodo di istanza con due parametri (<xref:System.String> e <xref:System.Int32>) e una matrice di parametri di tipo <xref:System.String>[].  
  
4.  Richiamare un metodo di istanza con due parametri di tipo <xref:System.Int32> e un risultato di tipo <xref:System.Int32>. In questo scenario il valore restituito viene associato a una variabile e usato in un'altra attività. Viene visualizzato nella console usando l'attività <xref:System.Activities.Statements.WriteLine>.  
  
5.  Richiamare un metodo statico con due parametri di tipo <xref:System.String> e <xref:System.Int32>.  
  
6.  Richiamare un metodo di istanza con un parametro generico di tipo <xref:System.String>.  
  
7.  Richiamare un metodo statico con due parametri generici di tipo <xref:System.String> e <xref:System.Int32>.  
  
8.  Richiamare un metodo di istanza che dispone di un parametro passato da un riferimento di tipo <xref:System.String>. In questo scenario il parametro di riferimento viene associato a una variabile (`outParam`) e usato in un'altra attività. Viene visualizzato nella console usando l'attività <xref:System.Activities.Statements.WriteLine>.  
  
9. Richiamare un metodo di istanza asincrono.  
  
10. Richiamare due metodi diversi nella stessa istanza di un oggetto usando due attività <xref:System.Activities.Statements.InvokeMethod>.  
  
11. Archiviare un valore in un'istanza di un oggetto.  
  
12. Recuperare un valore da un'istanza di un oggetto.  
  
## <a name="to-use-this-sample"></a>Per usare questo esempio  
 Questo esempio è fornito in due versioni. La prima versione di questo esempio illustra l'uso di <xref:System.Activities.Statements.InvokeMethod> tramite codice c# usando il modello di programmazione di Windows Workflow Foundation (WF) ed è disponibile nella cartella codedworkflow\cs. La seconda versione, che si trova nella cartella DesignerWorkflow\CS, illustra l'uso di <xref:System.Activities.Statements.InvokeMethod> tramite XAML.  
  
#### <a name="to-run-the-coded-workflow-sample"></a>Per eseguire l'esempio di flusso di lavoro codificato  
  
1.  Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione InvokeMethodUsage.sln nella cartella CodedWorkflow\CS.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere CTRL+F5.  
  
#### <a name="to-run-the-designer-workflow-sample"></a>Per eseguire l'esempio di flusso di lavoro di progettazione  
  
1.  Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione InvokeMethodUsage.sln nella cartella DesignerWorkflow\CS.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere CTRL+F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`