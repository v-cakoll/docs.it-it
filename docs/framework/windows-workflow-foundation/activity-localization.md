---
title: "Localizzazione di attività"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ee7bc16-e609-469a-a3e8-8062952e2676
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18856fe11d95d5b54bc580b83eae35badb4d86e6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="activity-localization"></a>Localizzazione di attività
Quando le applicazioni e i componenti del flusso di lavoro possono essere localizzati in altre impostazioni cultura e lingue, le stringhe di risorsa devono essere usate in modo da poter essere localizzate senza ricompilare.  
  
## <a name="activity-localization"></a>Localizzazione di attività  
 Come avviene con tutte le applicazioni che devono essere localizzate (rilasciate in versioni diverse per lingue e impostazioni cultura differenti), qualsiasi stringa visualizzata all'utente non deve essere inserita direttamente nel codice, bensì archiviata in un file di risorse. Le stringhe sono quindi possibile accedere tramite <!--zz <xref:System.Environment.GetResourceString> --> `GetResourceString`. Se si sta sviluppando un componente che viene distribuito in diverse lingue, si desidera anche usare stringhe di risorsa per i messaggi di convalida delle attività, i dati di rilevamento definiti dall'utente, i messaggi di traccia e quelli di errore.  
  
 Nell'esercizio seguente viene illustrato come usare un file di risorse.  
  
#### <a name="using-resource-files-for-localized-strings"></a>Uso di file di risorse per le stringhe localizzate  
  
1.  In [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], pulsante destro del mouse sul progetto in **Esplora** e selezionare **Aggiungi...** , **Nuovo elemento...** .  
  
2.  Selezionare **File di risorse** e denominare il file Errorresources. Fare clic su **Aggiungi**.  
  
3.  Aprire il file di risorse. Aggiungere una nuova voce con un **nome** ErrorString e **valore** "dell'attività non è valido."  
  
4.  Aggiungere le seguenti istruzioni `using` alla classe.  
  
    ```  
    using System.Reflection;  
    using System.Resources;  
    ```  
  
5.  Creare un gestore di risorse nel progetto.  
  
    ```  
    ResourceManager ErrorManager;  
    ...  
    ErrorManager = new ResourceManager("MyNamespace.ErrorResources", Assembly.GetExecutingAssembly());  
    ```  
  
6.  Ottenere la stringa dal gestore di risorse in cui è richiesta.  
  
    ```  
    String errorMessage = ErrorManager.GetString("ErrorString");  
    ```  
  
 Nell'esempio di codice seguente viene illustrato come usare le stringhe localizzate nel metodo <xref:System.Activities.Activity.CacheMetadata%2A>.  
  
```  
       protected override void CacheMetadata(CodeActivityMetadata metadata)  
        {  
           .....  
          // rest of the code elided for brevity  
           .....  
            if (this.Value != null && this.To != null)  
            {  
                if (!TypeHelper.AreTypesCompatible(this.Value.ArgumentType, this.To.ArgumentType))  
                {  
//---------------------------------------------  
// ** SR.TypeMismatchForAssign will fetch the string from the resource manager **  
//---------------------------------------------  
                    metadata.AddValidationError(SR.TypeMismatchForAssign(  
                                this.Value.ArgumentType,  
                                this.To.ArgumentType,  
                                this.DisplayName));  
                }  
            }  
        }  
```
