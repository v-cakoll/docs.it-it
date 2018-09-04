---
title: Argomenti dinamici
ms.date: 03/30/2017
ms.assetid: 122ad479-d306-4602-a943-5aefe711329d
ms.openlocfilehash: dcf6b84889f3bd7d043f736336c39634cd5384c7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43530441"
---
# <a name="dynamic-arguments"></a>Argomenti dinamici
In questo esempio viene illustrato come implementare un'attività per la quale gli argomenti sono definiti dal consumer dell'attività anziché dall'autore dell'attività. Questa operazione viene eseguita tramite l'override del modo in cui i metadati dell'attività vengono costruiti dal runtime.  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 Prima dell'esecuzione il runtime compila una descrizione di un'attività esaminando i membri pubblici del tipo di attività e dichiarando automaticamente argomenti, variabili, attività figlio e delegati di attività come parte dei metadati di un'attività. Ciò ha lo scopo di assicurare la costruzione corretta di un flusso di lavoro, nonché di gestire relazioni della fase di runtime e regole di durata. In genere l'autore di un'attività ne definisce gli argomenti specificando membri pubblici per il tipo di attività che deriva da <xref:System.Activities.Argument>. Per ogni membro pubblico che deriva da <xref:System.Activities.Argument> il runtime crea un oggetto <xref:System.Activities.RuntimeArgument> e lo associa all'argomento fornito dall'utente impostato su tale membro. In alcuni casi, tuttavia, il consumer dell'attività fornisce una configurazione che determina il set di argomenti. L'autore di un'attività esegue l'override di <xref:System.Activities.Activity.CacheMetadata%2A> per personalizzare il modo in cui vengono compilati i metadati dell'attività, incluso il set di argomenti associato all'attività.  
  
 In questo esempio viene illustrato come compilare dinamicamente un elenco di argomenti per un'attività che richiama un metodo. Il consumer dell'attività specifica il tipo e il nome del metodo da richiamare insieme a una raccolta di argomenti da passare a tale metodo.  
  
> [!NOTE]
>  Lo scopo di questo esempio è illustrare come eseguire l'override di <xref:System.Activities.CodeActivity.CacheMetadata%2A> e come usare <xref:System.Activities.RuntimeArgument>. È necessario considerare diversi aspetti per quanto riguarda i tipi di metodi che possono essere richiamati da questa attività. Ad esempio, non funziona con generics o matrici di parametri. L'attività <xref:System.Activities.Statements.InvokeMethod> disponibile in.NET di Framework consente di gestire questi e altri casi.  
  
 L'attività `MethodInvoke` esegue l'override di <xref:System.Activities.CodeActivity.CacheMetadata%2A> e inizia creando un oggetto <xref:System.Activities.RuntimeArgument> per gestire qualsiasi risultato della chiamata del metodo. Associa questo <xref:System.Activities.RuntimeArgument> all'oggetto <xref:System.Activities.OutArgument> impostabile pubblicamente denominato `Result`. Se `MethodInvoke.Result` è `null`, il runtime lo popola automaticamente con un oggetto <xref:System.Activities.OutArgument> configurato con l'espressione predefinita per il relativo tipo. Questo comportamento significa che l'autore di un'attività non deve mai controllare se la proprietà di un argomento è `null`.  
  
 L'override di <xref:System.Activities.CodeActivity.CacheMetadata%2A> determina quindi l'oggetto `MethodInfo` usato per la chiamata dagli oggetti `MethodName` e `TargetType` forniti dall'utente. Il metodo `DetermineMethodInfo` accetta il parametro <xref:System.Activities.CodeActivityMetadata> passato all'override di <xref:System.Activities.CodeActivity.CacheMetadata%2A> in modo che qualsiasi errore di configurazione possa essere restituito come errore di convalida. Questa operazione viene effettuata chiamando `metadata.AddValidationError`.  
  
 Dopo l'impostazione di `MethodInfo`, l'esempio scorre i parametri `MethodInfo`. Per ogni parametro crea un oggetto <xref:System.Activities.RuntimeArgument> e lo associa all'argomento corrispondente nella raccolta fornita dall'utente della proprietà `Parameters`. Infine, la raccolta di oggetti <xref:System.Activities.RuntimeArgument>s viene associata all'attività mediante una chiamata a `metadata.SetArgumentsCollection`.  
  
 Si noti che la risoluzione dell'argomento può essere effettuata usando un oggetto <xref:System.Activities.RuntimeArgument>, come nel caso di `resultArgument` o l'argomento fornito dall'utente, come nel caso della raccolta `Parameters`.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file DynamicArguments.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere CTRL+F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\DynamicArguments`