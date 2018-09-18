---
title: Formattazione di messaggi nei servizi flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 6d15d44b-20f8-4cb7-bd4f-598c32781ebc
ms.openlocfilehash: eb9a6b3a83a28154dc968bd4c1c41d34028bdd41
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "46003035"
---
# <a name="formatting-messages-in-workflow-services"></a>Formattazione di messaggi nei servizi flusso di lavoro
In questo esempio viene illustrato come tipi utente diversi possono essere usati nelle attività di messaggistica (servizi WF). Il servizio di esempio è un semplice servizio di approvazione spese ed espone tre operazioni. `ApproveExpense` accetta un tipo di contratto dati e mostra come usare i tipi noti. L'operazione restituisce `true` o `false` in base all'ammontare della spesa. `ApprovePO` accetta un tipo XmlSerializer e restituisce `true` o `false` in base all'ammontare della spesa.`ApprovedVendor` accetta un tipo di contratto di messaggio e restituisce `true` o `false` se il fornitore è presente l'elenco di fornitori approvati o se la richiesta proviene dal reparto finanziario (il reparto finanziario può utilizzare qualsiasi fornitore).  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Caricare la soluzione del progetto in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] e compilare il progetto.  
  
2.  Eseguire innanzitutto il servizio, generato in [directory soluzione di base]FormatterService\bin\debug\.  
  
3.  Eseguire quindi l'applicazione Client, generata in [directory soluzione di base]\FormatterClient\bin\debug.  
  
4.  Il client chiama tre operazioni nel servizio e stampa i risultati. Al termine premere INVIO per uscire dal client e quindi dal servizio.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Formatter`