---
title: Sviluppo pipeline
ms.date: 03/30/2017
helpviewer_keywords:
- add-in pipeline [.NET Framework], segments
- activation path for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], activation path
- communication pipeline for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], pipeline development
ms.assetid: 932788f2-b87d-44cf-82f9-04492a8b2722
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f981d667f3cbf35ab010ac5bd26a9ecd5c2aae11
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2018
ms.locfileid: "50135441"
---
# <a name="pipeline-development"></a>Sviluppo pipeline
La pipeline del componente aggiuntivo è il percorso dei segmenti di pipeline che l'applicazione host e il componente aggiuntivo deve usare per comunicare tra loro.  
  
 La figura seguente mostra la pipeline di comunicazione e i segmenti.  
  
 ![Aggiungere&#45;nel modello di pipeline. ](../../../docs/framework/add-ins/media/addin1.png "AddIn1")  
Pipeline del componente aggiuntivo  
  
 L'applicazione host è in un'entità finale della pipeline e il componente aggiuntivo è a altra estremità. A partire da ogni entità finale e spostandosi verso il centro, l'applicazione host e il componente aggiuntivo hanno una classe base astratta che definisce una visualizzazione del modello a oggetti che sono gli stessi. Questi tipi (classi) costituiscono il segmento di pipeline nella visualizzazione componente aggiuntivo e la visualizzazione host del segmento di pipeline del componente aggiuntivo. Il segmento di pipeline nella visualizzazione componente aggiuntivo contiene spesso più di una classe astratta, ma la classe da cui il componente aggiuntivo eredita è detta la base del componente aggiuntivo.  
  
 Il segmento di pipeline dell'adattatore lato componente aggiuntivo e la conversione di segmento di adattatore lato host della pipeline il flusso dei tipi tra i segmenti della pipeline di visualizzazione e il segmento di pipeline di contratto. Il segmento centrale della pipeline è un contratto derivato dal <xref:System.AddIn.Contract.IContract> interfaccia. Questo contratto definisce i metodi che l'applicazione host e il componente aggiuntivo sia utilizzerà.  
  
 Se si caricano l'host e il componente aggiuntivo in domini applicazione distinti, è necessario un limite di isolamento che separa l'ambito dell'applicazione host dall'ambito del componente aggiuntivo. Il contratto è l'unico assembly caricati in host e i domini applicazione componente aggiuntivo. L'host e il componente aggiuntivo in ogni fare riferimento solo per la visualizzazione dei metodi del contratto. Pertanto, sono separati da un livello di astrazione dal contratto.  
  
 Per lo sviluppo di segmenti della pipeline, è necessario creare una struttura di directory che li contengono. Per altre informazioni sui requisiti di sviluppo e linee guida di ambito, vedere [requisiti di sviluppo delle Pipeline](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
 La figura seguente mostra i tipi che costituiscono i segmenti della pipeline. I nomi dei tipi illustrati nella figura sono arbitrari, ma tutti i tipi, ad eccezione dell'host e host di visualizzazione degli attributi di componente aggiuntivo richiedono in modo che possano essere individuate dai metodi che costituiscono un archivio di informazioni.  
  
 ![Aggiungere&#45;nel modello con gli attributi obbligatori per i tipi. ](../../../docs/framework/add-ins/media/addin-model.png "AddIn_Model")  
Pipeline del componente aggiuntivo con i tipi  
  
 Nella tabella seguente vengono descritti i segmenti di pipeline per l'attivazione di un componente aggiuntivo. Per altre informazioni su questi segmenti, vedere [contratti, viste e adattatori](https://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c).  
  
|Segmento di pipeline|Descrizione|  
|----------------------|-----------------|  
|Host|Assembly dell'applicazione che crea un'istanza di un componente aggiuntivo.|  
|Visualizzazione host del componente aggiuntivo|Rappresenta la visualizzazione dell'applicazione host di tipi di oggetto e i metodi utilizzati per comunicare con il componente aggiuntivo. La visualizzazione host è un'interfaccia o classe base astratta.|  
|Adattatore lato host|Un assembly con una o più classi che adatta i metodi da e verso il contratto.<br /><br /> Questo segmento di pipeline viene identificato tramite il <xref:System.AddIn.Pipeline.HostAdapterAttribute> attributo.<br /><br /> Gli assembly multimodulo non sono supportati.|  
|Contratto|Un'interfaccia che deriva dal <xref:System.AddIn.Contract.IContract> interfaccia e che definisce il protocollo per la comunicazione dei tipi tra l'host e il componente aggiuntivo.<br /><br /> Questo segmento di pipeline viene identificato tramite l'impostazione di <xref:System.AddIn.Pipeline.AddInContractAttribute> attributo.|  
|Adattatore lato componente-|Un assembly con una o più classi che adatta i metodi da e verso il contratto.<br /><br /> Questo segmento di pipeline viene identificato tramite il <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attributo.<br /><br /> Ogni assembly nella directory dell'adattatore lato componente aggiuntivo che contiene un tipo che ha un <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attributo viene caricato dominio dell'applicazione del componente aggiuntivo.<br /><br /> Ogni assembly nella directory del lato componente aggiuntivo viene caricato nel proprio dominio applicazione.<br /><br /> Non sono supportati gli assembly multimodulo|  
|Visualizzazione componente aggiuntivo|Un assembly che rappresenta visualizzazione del componente aggiuntivo dei tipi di oggetto e i metodi utilizzati per comunicare con l'host. La visualizzazione componente aggiuntivo è un'interfaccia o classe base astratta.<br /><br /> Questo segmento di pipeline viene identificato tramite il <xref:System.AddIn.Pipeline.AddInBaseAttribute> attributo.<br /><br /> Ogni assembly nella directory AddInViews che contiene un tipo che ha un <xref:System.AddIn.Pipeline.AddInBaseAttribute> attributo viene caricato dominio dell'applicazione del componente aggiuntivo.|  
|Componente aggiuntivo|Un tipo con istanze che esegue un servizio per l'host.|  
  
## <a name="pipeline-activation-path"></a>Percorso di attivazione della pipeline  
 La figura seguente mostra l'attivazione dei tipi quando un componente aggiuntivo viene attivato. Viene illustrato il passaggio di oggetti all'host, ad esempio i risultati di un calcolo o una raccolta di oggetti. Questo è lo scenario più comune.  
  
 ![Aggiungere&#45;nel modello con il percorso di attivazione. ](../../../docs/framework/add-ins/media/addin6.png "AddIn6")  
Percorso di attivazione dal componente aggiuntivo all'host  
  
 Il percorso di attivazione della pipeline viene eseguita come indicato di seguito:  
  
1.  L'applicazione host viene attivata con il componente aggiuntivo di <xref:System.AddIn.Hosting.AddInToken.Activate%2A> (metodo).  
  
2.  La visualizzazione componente aggiuntivo, componente aggiuntivo adattatore lato componente e gli assembly del contratto vengono caricati nel dominio di applicazione del componente aggiuntivo.  
  
3.  Viene creata un'istanza dell'adattatore lato componente aggiuntivo utilizzando la visualizzazione componente aggiuntivo (con la classe identificata dal <xref:System.AddIn.Pipeline.AddInBaseAttribute> attributo) come relativo costruttore. L'adattatore lato componente aggiuntivo eredita dal contratto.  
  
4.  L'adattatore lato componente aggiuntivo, che viene inserito come contratto, viene passato attraverso il limite di isolamento (facoltativo) al costruttore dell'adattatore lato host.  
  
5.  La visualizzazione host della scheda add-sul lato host e gli assembly del contratto vengono caricati nel dominio applicazione dell'host.  
  
6.  Un'istanza dell'adattatore lato host viene creata usando il contratto relativo costruttore. L'adattatore lato host eredita dalla visualizzazione host del componente aggiuntivo.  
  
7.  L'host ha il componente aggiuntivo, tipizzato come l'host consente di visualizzare il componente aggiuntivo di e può continuare a chiamare i relativi metodi.  
  
## <a name="walkthroughs"></a>Procedure dettagliate  
 Esistono tre procedure dettagliate che illustrano come creare le pipeline con Visual Studio:  
  
-   [Procedura dettagliata: Creazione di un'applicazione estendibile](../../../docs/framework/add-ins/walkthrough-create-extensible-app.md)  
  
     Descrive un componente aggiuntivo di calcolatrice che esegue l'addizione, sottrazione, moltiplicazione e divisione calcoli per l'host.  
  
-   [Procedura dettagliata: Abilitazione della compatibilità con le versioni precedenti in base alle modifiche dell'Host](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
  
     Descrive un componente aggiuntivo della calcolatrice con funzionalità di calcolo avanzate e su come mantenere la compatibilità con il componente aggiuntivo prima di calcolatrice.  
  
-   [Procedura dettagliata: Passaggio di raccolte tra host e componenti aggiuntivi](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
  
     Viene descritto come passare raccolte di dati tramite la pipeline mediante uno scenario di archivio della Rubrica.  
  
## <a name="see-also"></a>Vedere anche  
- [Componente aggiuntivo in scenari con Pipeline](https://msdn.microsoft.com/library/feb70e0b-8734-494c-aeaf-b567f014043e)  
- [Componenti aggiuntivi ed estendibilità](../../../docs/framework/add-ins/index.md)
