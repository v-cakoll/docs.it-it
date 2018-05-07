---
title: Creazione di attività di controllo del flusso personalizzate
ms.date: 03/30/2017
ms.assetid: 27f409f6-2d1d-4cfb-9765-93eb2ad667d5
ms.openlocfilehash: 124ecd23ca2a856b6efd0e75f816c6f188c9425f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="creating-custom-flow-control-activities"></a>Creazione di attività di controllo del flusso personalizzate
.NET Framework contiene una gamma di attività di controllo del flusso che funzionano in modo analogo alle strutture di programmazione astratte (come <xref:System.Activities.Statements.Flowchart>) o alle istruzioni di programmazione standard (come <xref:System.Activities.Statements.If>). In questo argomento viene illustrata l'architettura di uno dei progetti di esempio, [Non-Generic ForEach](../../../docs/framework/windows-workflow-foundation/samples/non-generic-foreach.md).  
  
## <a name="creating-the-custom-class"></a>Creazione della classe personalizzata  
 Poiché la classe Non-Generic ForEach dovrà pianificare le attività figlio, dovrà effettuare la derivazione da <xref:System.Activities.NativeActivity>, dal momento che le attività che derivano da <xref:System.Workflow.Activities.CodeActivity> non dispongono di questa funzionalità.  
  
```  
public sealed class ForEach : NativeActivity  
    {  
```  
  
 La classe personalizzata richiede diversi membri per archiviare i dati usati dall'attività e fornire la funzionalità per eseguire le attività figlio dell'attività. Tali membri includono:  
  
-   `valueEnumerator`: oggetto <xref:System.Activities.Variable%601> non pubblico di tipo <xref:System.Collections.IEnumerator> usato per scorrere la raccolta di elementi. Questo membro è di tipo <xref:System.Activities.Variable%601> perché usato internamente all'attività, piuttosto che essere un argomento o una proprietà pubblica, che verrebbero usati se questo oggetto avesse un'origine esterna all'attività.  
  
-   `OnChildComplete`: proprietà <xref:System.Activities.CompletionCallback> pubblica che viene eseguita quando ogni figlio completa l'esecuzione. Questo membro è definito come una proprietà CLR, poiché il relativo valore non varia per istanze diverse dell'attività.  
  
-   `Values`: raccolta di input usata per le iterazioni dell'attività figlio. Questo membro è di tipo <xref:System.Activities.InArgument%601>, poiché l'origine dei dati è esterna all'attività, ma non si prevedono modifiche del contenuto della raccolta durante l'esecuzione dell'attività. Se, nel corso dell'esecuzione, l'attività avesse avuto bisogno che la funzionalità modificasse il contenuto di questa raccolta (per aggiungere o rimuovere attività, ad esempio), questo membro sarebbe stato definito come <xref:System.Activities.ActivityAction>, oggetto che sarebbe poi stato valutato a ogni accesso, in modo da rendere le modifiche disponibili all'attività.  
  
-   `Body`: questo membro definisce l'attività da eseguire per ogni elemento nella raccolta `Values`. Questo membro viene definito come <xref:System.Activities.ActivityAction> in modo da essere valutato a ogni accesso.  
  
-   `Execute`: questo metodo usa i membri non pubblici `InternalExecute`, `OnForEachComplete` e `GetStateAndExecute` per pianificare l'esecuzione e assegnare il gestore di completamento dell'attività figlio definita nel membro Body.  
  
-   `CacheMetadata`: questo membro fornisce al runtime le informazioni necessarie per eseguire l'attività. Per impostazione predefinita, il metodo `CacheMetadata` di un'attività informa il runtime di tutti i membri pubblici dell'attività, ma poiché questa attività usa membri privati per alcune funzionalità, deve informare il runtime della loro esistenza perché ne tenga conto. In questo caso, viene eseguito l'override della funzione `CacheMetadata` in modo che sia possibile accedere al membro `valueEnumerator` privato. Questo membro crea inoltre un argomento per i valori dell'attività in modo che possano essere passati nell'attività durante l'esecuzione.
