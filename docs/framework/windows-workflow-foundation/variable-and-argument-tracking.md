---
title: Rilevamento di variabili e argomenti
ms.date: 03/30/2017
ms.assetid: 8f3d9d30-d899-49aa-b7ce-a8d0d32c4ff0
ms.openlocfilehash: 45ed3761cd7ead82650023b93a2f32a43e847339
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45560529"
---
# <a name="variable-and-argument-tracking"></a>Rilevamento di variabili e argomenti
Quando si rileva l'esecuzione di un flusso di lavoro, spesso è utile estrarre i dati. Tali dati offrono un contesto aggiuntivo quando si accede alla post-esecuzione di un record di rilevamento. In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], usando il rilevamento, è possibile estrarre qualsiasi variabile o argomento visibile all'interno dell'ambito di tutte le attività di un flusso di lavoro. I profili di rilevamento semplificano l'estrazione dei dati.  
  
## <a name="variables-and-arguments"></a>Variabili e argomenti  
 Le variabili e gli argomenti vengono estratti quando un'attività crea un oggetto ActivityStateRecord.  Una variabile può essere estratta solo se è inclusa nell'ambito dell'attività. Una variabile da estrarre in un'attività viene specificata nel modo seguente:  
  
-   Se una variabile viene specificata con il relativo nome, il rilevamento cerca la variabile all'interno dell'attività in fase di rilevamento e nelle attività padre. La variabile viene ricercata nell'ambito dell'attività corrente e nell'ambito padre.  
  
-   Se le variabili da estrarre vengono specificate con name = "*", vengono estratte tutte le variabili all'interno dell'attività corrente in fase di rilevamento. In questo caso, le variabili incluse nell'ambito ma definite nelle attività padre non vengono estratte.  
  
 Gli argomenti estratti dipendono dallo stato dell'attività. Quando lo stato di un'attività è Executing, possono essere estratti solo gli argomenti `InArguments`. Per qualsiasi altro stato dell'attività (Closed, Faulted, Canceled), entrambi gli argomenti InArguments e OutArguments sono disponibili per l'estrazione.  
  
 Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività. Le variabili e gli argomenti possono essere estratti solo con un oggetto <xref:System.Activities.Tracking.ActivityStateRecord>, pertanto vengono sottoscritti all'interno di un profilo di rilevamento tramite l'oggetto <xref:System.Activities.Tracking.ActivityStateQuery>.  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="protecting-information-stored-within-variables-and-arguments"></a>Protezione delle informazioni archiviate in variabili e argomenti  
 Una variabile o un argomento rilevato viene reso visibile per impostazione predefinita dal runtime di WF. Uno sviluppatore di flussi di lavoro può limitarne l'accesso eseguendo i passaggi seguenti.  
  
1.  Crittografia del valore di una variabile.  
  
2.  Controllo della creazione di un profilo di rilevamento per impedire l'estrazione di una variabile o di un argomento.  
  
3.  Per i partecipanti del rilevamento personalizzato, assicurarsi che il codice di WF non diffonda informazioni riservate archiviate nelle variabili o negli argomenti.  
  
## <a name="see-also"></a>Vedere anche  
 [Monitoraggio dell'infrastruttura di App di Windows Server](https://go.microsoft.com/fwlink/?LinkId=201273)  
 [Monitoraggio delle applicazioni con App Fabric](https://go.microsoft.com/fwlink/?LinkId=201275)
