---
title: Servizio solo XAML di base
ms.date: 03/30/2017
ms.assetid: c106feb0-0245-43b5-aefe-93ce0e4d38eb
ms.openlocfilehash: f4f296a97b9c3093874c5ec8e05023e84b0af44a
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45583466"
---
# <a name="basic-xaml-only-service"></a>Servizio solo XAML di base
In questo esempio viene illustrato come creare un servizio solo XAML. Lo scenario è quello di un servizio di diagnostica per problemi correlati all'auto. Il servizio viene implementato come flusso di lavoro che pone al client una serie di domande per diagnosticare il problema. Esistono due tipi di problema diagnosticabili dal servizio (l'auto non parte oppure l'aria condizionata non funziona). Il flusso di lavoro usa il modello Request/Reply della finestra di progettazione per esporre tre operazioni di servizio semplici. Il servizio viene ospitato in IIS creando una directory virtuale in IIS e copiando i file service1.xamlx e Web.config nella directory virtuale. Non è richiesto alcun codice compilato. Per impostazione predefinita in questo esempio copierà automaticamente i file necessari nella directory virtuale creata quando si seguono le istruzioni di installazione per gli esempi di WCF e WF: [monouso procedura di installazione per gli esempi Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) quando compilato in Visual Studio 2010.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Caricare la soluzione del progetto in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] e compilare il progetto.  
  
2.  Eseguire l'applicazione client generata in [directory soluzione di base]\Client\bin\debug.  
  
3.  L'applicazione stampa le opzioni, ne seleziona una e pone alcune domande, rispondendo con sì o no (utilizzo di chiavi S/N). Quando il servizio ha diagnosticato i problemi, l'applicazione stampa una diagnosi.  
  
4.  L'applicazione torna alle opzioni. È possibile diagnosticare un altro problema o uscire dall'applicazione.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLService`