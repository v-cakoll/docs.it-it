---
title: Servizio casella degli strumenti
ms.date: 03/30/2017
ms.assetid: 742212d0-445e-41ed-9739-9ee848ce7f1b
ms.openlocfilehash: 0b3ea56d28d202bd8356fea1783b6675a708631d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516191"
---
# <a name="toolbox-service"></a>Servizio casella degli strumenti
In questo esempio viene illustrato come aggiornare le attività della casella degli strumenti di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] in base al contesto del flusso di lavoro. L'esempio contiene un flusso di lavoro che modifica il contenuto della casella degli strumenti in base alla selezione o meno di un'attività personalizzata.  
  
## <a name="discussion"></a>Discussione  
 Durante la creazione di flussi di lavoro, i clienti generalmente desiderano che Casella degli strumenti sia sensibile al contesto. Ad esempio, l'utente può volersi assicurare che nella Casella degli strumenti siano visualizzate alcune attività aggiuntive quando un'attività specifica viene aggiunta al flusso di lavoro. Se le attività vengono rimosse dal flusso di lavoro, la casella degli strumenti deve riflettere in modo appropriato i requisiti del dominio.  
  
 In una finestra di progettazione del flusso di lavoro riallocata è possibile verificare il controllo Casella degli strumenti e assicurarsi che in base alle modifiche del Modello nel flusso di lavoro, l'host attivi modifiche appropriate nel controllo Casella degli strumenti. Tuttavia, in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], la casella degli strumenti non viene controllata dall'utente e quindi per modificarne il contenuto è necessaria un'interfaccia. `IActivityToolboxService` è l'interfaccia necessaria.  
  
 L'API fornisce i quattro metodi seguenti.  
  
```  
public interface IActivityToolboxService   
{   
        void AddCategory(string categoryName);   
        void RemoveCategory(string categoryName);   
        void AddItem(string qualifiedTypeName, string categoryName);   
        void RemoveItem(string qualifiedTypeName, string categoryName);   
        IList<string> EnumCategories();   
        IList<string> EnumItems(string categoryName);   
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione WorkflowSimulator.sln.  
  
2.  Premere CTRL+MAIUSC+B per compilare la soluzione,  
  
3.  Aprire il file Workflow.xaml.  
  
4.  Aggiungere un **CustomActivity** trascinando e rilasciandolo dalla casella degli strumenti. Si noti che una categoria della casella degli strumenti aggiuntiva denominata: **nuova categoria WF** con un'attività aggiuntiva **assegnare**.  
  
5.  Deselezionare la **CustomActivity** trascinandovi un'altra attività.  
  
6.  L'elemento **assegnare** nella categoria **nuova categoria WF** nella casella degli strumenti viene rimosso. Inoltre, poiché non sono rimasti elementi nella categoria, questa viene anch'essa rimossa.  
  
7.  Selezionare il **CustomActivity** nuovamente e la categoria e **assegnare** attività vengono nuovamente aggiunte.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\IActivityToolboxService`
