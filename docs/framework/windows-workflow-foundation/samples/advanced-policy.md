---
title: Criteri avanzati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75a22c88-5e54-4ae8-84cb-fbb22a612f0a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b9752b5779f4fbb525488e88f2f11c98de7b4ba8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="advanced-policy"></a>Criteri avanzati
Questo esempio estende l'esempio di criterio semplice. Oltre alle regole di sconto residenziale e sconto aziendale dell'esempio di criterio semplice, sono state aggiunte molte nuove regole.  
  
 Viene aggiunta una regola per valori elevati, che consente uno sconto maggiore per gli ordini di alto valore. Viene fornito un valore di priorità minore rispetto alle due regole precedenti che sovrascriverà il campo dello sconto e avrà la precedenza rispetto a entrambe le regole di sconto residenziale e aziendale.  
  
 Viene aggiunta una regola di calcolo del totale, che calcola il totale in base al livello di sconto. Viene mostrato come fare riferimento a un metodo definito sull'attività del flusso di lavoro e come usare le azioni else. Questa regola dimostra anche il comportamento mutevole, dal momento che verrà valutata a ogni modifica del campo di sconto. Inoltre, viene mostrata l'attribuzione del metodo con RuleWriteAttribute sul metodo CalculateTotal. Ciò fa in modo che regole con impatto (ErrorTotalRule) vengano rivalutate ogni qualvolta il metodo viene eseguito.  
  
 L'ultima regola aggiunta rileva gli errori (in questo caso il Totale inferiore a 0). Se si verifica tale condizione, l'esecuzione del criterio verrà interrotta.  
  
 Infine, vengono aggiunte le chiamate a `Console.Writeline` come azioni a ogni regola in modo da fornire più visibilità all'esecuzione della regola, dimostrando allo stesso tempo che è possibile accedere a metodi statici sui tipi a cui viene fatto riferimento. È anche possibile usare il rilevamento per ottenere visibilità nelle regole eseguite.  
  
 Le regole usate in questo esempio sono:  
  
 **ResidentialDiscountRule:**  
  
 IF OrderValue > 500 AND CustomerType = Residential  
  
 THEN Discount = 5%  
  
 **BusinessDiscountRule:**  
  
 IF OrderValue > 10000 AND CustomerType = Business  
  
 THEN Discount = 10%  
  
 **HighValueDiscountRule:**  
  
 IF OrderValue > 20000  
  
 THEN Discount = 15%  
  
 **TotalRule:**  
  
 IF Discount > 0  
  
 THEN CalculateTotal(OrderValue, Discount)  
  
 ELSE Total = OrderValue  
  
 **ErrorTotalRule:**  
  
 Se totale \< 0  
  
 THEN Error = "Fired ErrorTotalRule"; Halt  
  
 La valutazione e l'esecuzione delle regole può essere inoltre visualizzata tramite traccia e rilevamento.  
  
### <a name="to-build-the-sample"></a>Per compilare l'esempio  
  
1.  Aprire la soluzione in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Premere CTRL+MAIUSC+B per compilare la soluzione,  
  
3.  Eseguire la soluzione senza debug premendo CTRL+F5.  
  
### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
-   Nella finestra del prompt dei comandi di SDK eseguire il file con estensione exe nella cartella AdvancedPolicy\bin\debug (oppure nella cartella AdvancedPolicy\bin per la versione Visual Basic dell'esempio), collocata sotto la cartella principale dell'esempio.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\AdvancedPolicy`  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [Criteri semplici](../../../../docs/framework/windows-workflow-foundation/samples/simple-policy.md)
