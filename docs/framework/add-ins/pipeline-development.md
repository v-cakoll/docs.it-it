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
ms.openlocfilehash: 2d889b7de4bc766deda9b91877ceefb4aebfc551
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="pipeline-development"></a>Sviluppo pipeline
La pipeline del componente aggiuntivo è il percorso di segmenti della pipeline che l'applicazione host e il componente aggiuntivo deve utilizzare per comunicare tra loro.  
  
 Nella figura seguente mostra la pipeline di comunicazione e i segmenti.  
  
 ![Aggiungere&#45;nel modello di pipeline. ] (../../../docs/framework/add-ins/media/addin1.png "AddIn1")  
Pipeline del componente aggiuntivo  
  
 L'applicazione host è un'estremità della pipeline e il componente aggiuntivo è a altra estremità. A partire da ogni entità finale e spostamento verso il centro, l'applicazione host e il componente aggiuntivo dispone di una classe base astratta che definisce una vista del modello a oggetti che sono gli stessi. Questi tipi (classi) costituiscono il segmento della pipeline di visualizzazione e la visualizzazione host del segmento di pipeline del componente aggiuntivo. Il segmento di visualizzazione del componente della pipeline spesso contiene più di una classe astratta, ma la classe da cui il componente aggiuntivo eredita è noto come base per il componente aggiuntivo.  
  
 Il segmento della pipeline sul lato componente-scheda e la conversione di segmento della pipeline di adattatore sul lato host al flusso di tipi tra i segmenti della pipeline di visualizzazione e il segmento della pipeline del contratto. Il segmento centrale della pipeline è un contratto derivato dal <xref:System.AddIn.Contract.IContract> interfaccia. Questo contratto definisce i metodi che l'applicazione host e il componente aggiuntivo sia utilizzerà.  
  
 Se si caricano l'host e il componente aggiuntivo in domini applicazione separati, è necessario un limite di isolamento che separa l'ambito dell'applicazione host dall'ambito del componente aggiuntivo. Il contratto è il solo assembly caricati in host e i domini applicazione. L'host e il componente aggiuntivo ogni fare riferimento solo alla visualizzazione dei metodi del contratto. Di conseguenza, saranno separati da un livello di astrazione dal contratto.  
  
 Per lo sviluppo di segmenti della pipeline, è necessario creare una struttura di directory che li contengono. Per ulteriori informazioni sui requisiti di sviluppo e linee guida di ambito, vedere [requisiti di sviluppo Pipeline](http://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).  
  
 Nella figura seguente mostra i tipi che costituiscono i segmenti della pipeline. I nomi dei tipi illustrati nella figura sono arbitrari, ma tutti i tipi, ad eccezione dell'host e l'host consente di visualizzare gli attributi aggiuntivo richiesto in modo che possano essere individuate dai metodi che costruiscono un archivio di informazioni.  
  
 ![Aggiungere&#45;nel modello con gli attributi obbligatori per i tipi. ] (../../../docs/framework/add-ins/media/addin-model.png "AddIn_Model")  
Pipeline del componente aggiuntivo con tipi  
  
 Nella tabella seguente vengono descritti i segmenti di pipeline per l'attivazione di un componente aggiuntivo. Per ulteriori informazioni su questi segmenti, vedere [contratti, visualizzazioni e adattatori](http://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c).  
  
|Segmento della pipeline|Descrizione|  
|----------------------|-----------------|  
|Host|Assembly dell'applicazione che crea un'istanza di un componente aggiuntivo.|  
|Visualizzazione host del componente aggiuntivo|Rappresenta la visualizzazione dell'applicazione host di tipi di oggetti e metodi utilizzati per comunicare con il componente aggiuntivo. La visualizzazione host è un'interfaccia o classe base astratta.|  
|Adattatore sul lato host|Un assembly con una o più classi che adatta i metodi da e verso il contratto.<br /><br /> Il segmento della pipeline viene identificato tramite il <xref:System.AddIn.Pipeline.HostAdapterAttribute> attributo.<br /><br /> Gli assembly con più moduli non sono supportati.|  
|Contratto|Un'interfaccia derivata dal <xref:System.AddIn.Contract.IContract> interfaccia che definisce il protocollo per la comunicazione dei tipi tra l'host e il componente aggiuntivo.<br /><br /> Questo segmento della pipeline viene identificato tramite l'impostazione di <xref:System.AddIn.Pipeline.AddInContractAttribute> attributo.|  
|Sul lato componente-scheda|Un assembly con una o più classi che adatta i metodi da e verso il contratto.<br /><br /> Il segmento della pipeline viene identificato tramite il <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attributo.<br /><br /> Ogni assembly nella directory sul lato componente-scheda che contiene un tipo che ha un <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attributo verrà caricato nel dominio dell'applicazione del componente aggiuntivo.<br /><br /> Ogni assembly nella directory lato del componente aggiuntivo viene caricato nel dominio applicazione.<br /><br /> Gli assembly con più moduli non sono supportati.|  
|Visualizzazione del componente aggiuntivo|Un assembly che rappresenta la vista del componente aggiuntivo di tipi di oggetti e metodi utilizzati per comunicare con l'host. La visualizzazione di un componente aggiuntivo è un'interfaccia o classe base astratta.<br /><br /> Il segmento della pipeline viene identificato tramite il <xref:System.AddIn.Pipeline.AddInBaseAttribute> attributo.<br /><br /> Ogni assembly nella directory AddInViews che contiene un tipo che ha un <xref:System.AddIn.Pipeline.AddInBaseAttribute> attributo verrà caricato nel dominio dell'applicazione del componente aggiuntivo.|  
|Componente aggiuntivo|Un tipo di istanze che esegue un servizio per l'host.|  
  
## <a name="pipeline-activation-path"></a>Percorso di attivazione della pipeline  
 Nella figura seguente mostra l'attivazione dei tipi quando viene attivato un componente aggiuntivo. Viene illustrato il passaggio di oggetti all'host, ad esempio i risultati di un calcolo o una raccolta di oggetti. Questo è lo scenario più comune.  
  
 ![Aggiungere&#45;nel modello con percorso di attivazione. ] (../../../docs/framework/add-ins/media/addin6.png "AddIn6")  
Percorso di attivazione dal componente aggiuntivo all'host  
  
 Il percorso di attivazione della pipeline avviene nel modo seguente:  
  
1.  L'applicazione host attiva il componente aggiuntivo con il <xref:System.AddIn.Hosting.AddInToken.Activate%2A> metodo.  
  
2.  La vista del componente aggiuntivo, componenti sul lato componente-scheda e gli assembly del contratto vengono caricati nel dominio di applicazione del componente aggiuntivo.  
  
3.  Viene creata un'istanza dell'adattatore di lato del componente aggiuntivo utilizzando la vista del componente aggiuntivo (con la classe identificata dal <xref:System.AddIn.Pipeline.AddInBaseAttribute> attributo) come costruttore. L'adapter sul lato componente-eredita dal contratto.  
  
4.  L'adapter lato del componente aggiuntivo, tipizzato come contratto, viene passato attraverso il limite di isolamento (facoltativo) al costruttore dell'adattatore sul lato host.  
  
5.  La visualizzazione host della scheda componenti sul lato host e gli assembly del contratto vengono caricati nel dominio applicazione dell'host.  
  
6.  Viene creata un'istanza dell'adattatore sul lato host utilizzando il contratto come costruttore. Adattatore sul lato host eredita dalla visualizzazione host del componente aggiuntivo.  
  
7.  L'host è il componente aggiuntivo, tipizzato come l'host del componente aggiuntivo consente di visualizzare e può continuare a chiamare i metodi.  
  
## <a name="walkthroughs"></a>Procedure dettagliate  
 Esistono tre argomenti di questa procedura dettagliata viene descritto come creare pipeline utilizzando Visual Studio:  
  
-   [Procedura dettagliata: Creazione di un'applicazione estendibile](../../../docs/framework/add-ins/walkthrough-create-extensible-app.md)  
  
     Viene descritto un componente aggiuntivo di calcolatrice che esegue l'addizione, sottrazione, moltiplicazione e divisione calcoli per l'host.  
  
-   [Procedura dettagliata: Abilitazione della compatibilità con le versioni precedenti in base alle modifiche dell'Host](http://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
  
     Viene descritto un componente aggiuntivo di calcolo con funzionalità di calcolo avanzate e come mantenere la compatibilità con il componente aggiuntivo prima di calcolatrice.  
  
-   [Procedura dettagliata: Passaggio di raccolte tra componenti aggiuntivi e host](http://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
  
     Viene descritto come passare raccolte di dati attraverso la pipeline di uno scenario di archivio della Rubrica.  
  
## <a name="see-also"></a>Vedere anche  
 [Componente aggiuntivo per gli scenari di Pipeline](http://msdn.microsoft.com/library/feb70e0b-8734-494c-aeaf-b567f014043e)  
 [Componenti aggiuntivi ed estendibilità](../../../docs/framework/add-ins/index.md)
