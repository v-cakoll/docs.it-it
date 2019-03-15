---
title: Creazione di attività di controllo del flusso personalizzate
ms.date: 03/30/2017
ms.assetid: 27f409f6-2d1d-4cfb-9765-93eb2ad667d5
ms.openlocfilehash: 2be47281335066def5c1d267cd709db5a8ff1187
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2019
ms.locfileid: "57847011"
---
# <a name="creating-custom-flow-control-activities"></a>Creazione di attività di controllo del flusso personalizzate
.NET Framework contiene un'ampia gamma di attività di controllo di flusso che funzionano in modo analogo a strutture di programmazione astratte (ad esempio <xref:System.Activities.Statements.Flowchart>) o per le istruzioni di programmazione standard (ad esempio <xref:System.Activities.Statements.If>). In questo argomento viene illustrata l'architettura di uno dei progetti di esempio, [Non-Generic ForEach](./samples/non-generic-foreach.md).  
  
## <a name="creating-the-custom-class"></a>Creazione della classe personalizzata  
 Poiché la classe Non-Generic ForEach dovrà pianificare le attività figlio, dovrà effettuare la derivazione da <xref:System.Activities.NativeActivity>, dal momento che le attività che derivano da <xref:System.Workflow.Activities.CodeActivity> non dispongono di questa funzionalità.  
  
```  
public sealed class ForEach : NativeActivity  
    {  
```  
  
 La classe personalizzata richiede diversi membri per archiviare i dati usati dall'attività e fornire la funzionalità per eseguire le attività figlio dell'attività. Tali membri includono:  
  
-   `valueEnumerator`: Il non pubbliche <xref:System.Activities.Variable%601> di tipo <xref:System.Collections.IEnumerator> utilizzato per scorrere la raccolta di elementi. Questo membro è di tipo <xref:System.Activities.Variable%601> perché usato internamente all'attività, piuttosto che essere un argomento o una proprietà pubblica, che verrebbero usati se questo oggetto avesse un'origine esterna all'attività.  
  
-   `OnChildComplete`: Pubblico <xref:System.Activities.CompletionCallback> proprietà che viene eseguita quando ogni figlio completa l'esecuzione. Questo membro è definito come una proprietà CLR, poiché il relativo valore non varia per istanze diverse dell'attività.  
  
-   `Values`: La raccolta di input usati per le iterazioni dell'attività figlio. Questo membro è di tipo <xref:System.Activities.InArgument%601>, poiché l'origine dei dati è esterna all'attività, ma non si prevedono modifiche del contenuto della raccolta durante l'esecuzione dell'attività. Se, nel corso dell'esecuzione, l'attività avesse avuto bisogno che la funzionalità modificasse il contenuto di questa raccolta (per aggiungere o rimuovere attività, ad esempio), questo membro sarebbe stato definito come <xref:System.Activities.ActivityAction>, oggetto che sarebbe poi stato valutato a ogni accesso, in modo da rendere le modifiche disponibili all'attività.  
  
-   `Body`: Questo membro definisce l'attività da eseguire per ogni elemento di `Values` raccolta. Questo membro viene definito come <xref:System.Activities.ActivityAction> in modo da essere valutato a ogni accesso.  
  
-   `Execute`: Questo metodo Usa il `InternalExecute`, `OnForEachComplete`, e `GetStateAndExecute` membri non pubblici per pianificare l'esecuzione e assegnare il gestore di completamento dell'attività figlio definita nel membro Body.  
  
-   `CacheMetadata`: Questo membro fornisce il runtime con le informazioni necessarie per eseguire l'attività. Per impostazione predefinita, il metodo `CacheMetadata` di un'attività informa il runtime di tutti i membri pubblici dell'attività, ma poiché questa attività usa membri privati per alcune funzionalità, deve informare il runtime della loro esistenza perché ne tenga conto. In questo caso, viene eseguito l'override della funzione `CacheMetadata` in modo che sia possibile accedere al membro `valueEnumerator` privato. Questo membro crea inoltre un argomento per i valori dell'attività in modo che possano essere passati nell'attività durante l'esecuzione.
