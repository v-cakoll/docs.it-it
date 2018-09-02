---
title: Expressions2
ms.date: 03/30/2017
ms.assetid: 43a85905-77b5-4893-bb38-1cb9b293d69d
ms.openlocfilehash: e852b62e6d0b6b4b3ddc19b197902de5325310a1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43464869"
---
# <a name="expressions"></a>Espressioni
In questo esempio viene illustrato come usare espressioni di base in un flusso di lavoro. È costituito da un flusso di lavoro che calcola statistiche del salario di base per due dipendenti di una società fittizia. Due classi, `Employee` e `SalaryStats`, sono definite in Employee.cs e SalaryStats.cs. Queste classi vengono usate in un flusso di lavoro che illustra come eseguire calcoli aritmetici semplici e operazioni di stringa su proprietà di variabili di tipi complessi.  
  
 Il flusso di lavoro del calcolo del salario è definito sia in XAML che in C# per dimostrare i due stili di creazione. La versione XAML è contenuta in SalaryCalculation.xaml e può essere visualizzata e modificata nella finestra di progettazione del flusso di lavoro. La versione C# si trova in Program.cs. Le espressioni usate in XAML sono conformi alla sintassi di Visual Basic e usano attività di espressione <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> e <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> per l'esecuzione. Per altre informazioni, vedere le espressioni Visual Basic [espressioni Visual Basic](https://go.microsoft.com/fwlink/?LinkId=165912). D'altra parte le espressioni in C# sono scritte come espressioni lambda e utilizzo attività di espressione <xref:System.Activities.Expressions.LambdaValue%601> e <xref:System.Activities.Expressions.LambdaReference%601>. La scrittura di espressioni come espressioni lambda consente al compilatore C# di fornire evidenziazione della sintassi e verifica statica. Per altre informazioni sulle espressioni lambda in c#, vedere [espressioni Lambda (Guida per programmatori c#)](https://go.microsoft.com/fwlink/?LinkId=182082). Se un flusso di lavoro viene creato nel codice usando Visual Basic, vengono usate le espressioni lambda di Visual Basic. Per altre informazioni sulle espressioni lambda in Visual Basic, vedere [espressioni Lambda (Visual Basic)](https://go.microsoft.com/fwlink/?LinkId=152437). Per altre informazioni sulla creazione di flussi di lavoro mediante codice, vedere [creazione di flussi di lavoro, attività e le espressioni tramite codice imperativo](../../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).  
  
#### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1.  Aprire la soluzione Expressions.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Premere CTRL + MAIUSC + B per compilare la soluzione oppure selezionare **Compila soluzione** dalle **compilazione** menu.  
  
    > [!NOTE]
    >  Per aprire SalaryCalculation.xaml nella finestra di progettazione di Visual Studio, è necessario compilare innanzitutto il progetto per assicurarsi che le classi `Employee` e `SalaryStats` sono disponibili nella finestra di progettazione.  
  
3.  Una volta completata la compilazione, premere F5 o selezionare **Avvia debug** dalle **Debug** menu. In alternativa è possibile premere CTRL+F5 o selezionare **Avvia senza eseguire debug** dalle **Debug** menu per l'esecuzione senza debug.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Expressions`