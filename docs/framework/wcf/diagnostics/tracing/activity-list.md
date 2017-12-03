---
title: "Elenco delle attività"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5540e185-ce8e-4db3-83b0-2b9f5bf71829
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3c3b478d88eff022d8cb28f4123291f4662644ba
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="activity-list"></a>Elenco delle attività
In questo argomento sono elencate tutte le attività definite in [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
> [!NOTE]
>  È inoltre possibile definire attività a livello di programmazione allo scopo di raggruppare più tracce utente. Per ulteriori informazioni, vedere [la creazione di tracce di codice utente](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md).  
  
## <a name="servicemodel-activities"></a>Attività ServiceModel  
 Nella tabella seguente sono elencate tutte le attività relative ai principali scenari di utilizzo.  
  
|Etichetta|Nome attività|Tipo di attività|Descrizione|  
|-----------|-------------------|-------------------|-----------------|  
|A, M|Attività di ambiente|N/D (non controllata da ServiceModel)|Attività il cui ID viene impostato in TLS prima che venga effettuata qualsiasi chiamata al codice di ServiceModel, sia esso lato client o lato server.<br /><br /> Esempio: un'attività in cui viene chiamata l'attività di apertura del client [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] oppure dove viene chiamata l'attività serviceHost.open.|  
|B|Costrutto<br /><br /> ChannelFactory. ContractType : "[tipo]".|Costrutto||  
|C|Apri<br /><br /> [ClientBase &#124; ChannelFactory]. ContractType : "[tipo]".|Apri||  
|I|Chiusura [ClientBase &#124; ChannelFactory]. ContractType : "[tipo]".|Chiudi||  
|M|Costruzione ServiceHost. ServiceType: "[tipo]".|Costrutto||  
|N|Apertura di ServiceHost. ServiceType: "[tipo]".|Apri||  
|Z|Chiusura di ServiceHost. ServiceType: "[tipo]".|Chiudi||  
|O|Attesa su "[indirizzo]".|ListenAt|Questa attività, così come la prossima, sono specifiche del trasporto. L'attività di tipo ListenAt rappresenta il contenuto che corrisponde all'indirizzo su cui il listener del canale è in attesa. Nel caso di MSMQ ciò corrisponde alla coda stessa, in quanto alla coda è associato un unico indirizzo. Nel caso di trasporti orientati alla connessione, questa attività resta in attesa di connessioni in ingresso. Nel caso di MSMQ, invece, questa attività resta in attesa di messaggi MSMQ. Infine, questa attività viene creata durante l'attività ServiceHost.Open () e contiene le tracce riferite alla creazione e all'eliminazione del listener nonché al trasferimento dell'esecuzione a tutte le attività di tipo ReceiveBytes.|  
|P|Ricezione byte sulla connessione "[indirizzo]". Ricezione messaggio MSMQ.|ReceiveBytes|In questa attività vengono elaborati i dati che sono destinati a ottenere un messaggio di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]. Nel caso di trasporto orientato alla connessione o del protocollo HTTP, il sistema attende i byte in ingresso. Nel caso del protocollo TCP/pipe con nome, la durata di questa attività corrisponde alla durata della connessione, in quanto il momento di creazione dell'attività coincide con quello di creazione della connessione. Nel caso del protocollo HTTP, la durata di questa attività corrisponde a quella di una richiesta di messaggio e viene considerata a partire dal momento in cui il messaggio viene inviato. Questa attività, se applicabile, contiene le tracce riferite alla creazione e all'eliminazione della connessione nonché al trasferimento dell'esecuzione a tutte le attività di elaborazione di messaggi (ovvero di oggetti).<br /><br /> Nel caso di MSMQ, questa attività corrisponde a quella da cui viene recuperato il messaggio MSMQ.|  
|Q|Elaborazione messaggio [numero]. Nota: il parametro [numero] è un valore monotonicamente crescente inizialmente pari a 1.|ProcessMessage|Questa attività prevede l'elaborazione di un messaggio in ingresso e viene avviata quando tutti i dati (byte e messaggio MSMQ) vengono ricevuti per formare un oggetto di messaggio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]. Le tracce contenute in questa attività riguardano l'elaborazione delle intestazioni.<br /><br /> Dopo aver formato un messaggio che può essere inviato e dopo aver ricercato l'ID attività corrispondente, il sistema passa all'attività ServiceHost ProcessAction.|  
|D, S|Elaborazione azione "[azione]".|ProcessAction|Questa attività prevede l'elaborazione del messaggio attraverso lo stack Trasporto/Sicurezza/RM per inviare il messaggio al codice utente al momento della ricezione e restituire il messaggio sul percorso inverso al momento dell'invio.<br /><br /> Nel server, questa attività utilizza l'ID attività propagato se viene inviato nell'intestazione del messaggio tramite "Propagazione di attività"; in caso contrario, viene creato un nuovo GUID.<br /><br /> In questa attività viene inoltre elaborato il messaggio di risposta dei contratti di Request/Reply.|  
|T|Esecuzione "[IContratto.Operazione]".|ExecuteUserCode|Questa attività prevede l'esecuzione del codice utente dopo l'invio al lato server e rappresenta una linea di delimitazione fra il codice ServiceHost e il codice fornito dall'utente.|  
  
## <a name="security-activities"></a>Attività di sicurezza  
 Nella tabella seguente sono elencate tutte le attività riferite alla sicurezza.  
  
|Nome attività|Tipo di attività|Descrizione|  
|-------------------|-------------------|-----------------|  
|Impostazione sessione protetta|SetupSecurity|Esiste soltanto sul lato client. Contiene tutti gli scambi RST*/SCT per eseguire l'autenticazione e l'impostazione del contesto di sicurezza. Se `propagateActivity` = `true`, questa attività viene unita con corrispondente processo azione RST del servizio\*attività /SCT.|  
|Chiusura sessione protetta|SetupSecurity|Esiste sul lato client. Contiene lo scambio di messaggi di annullamento per eseguire la chiusura della sessione protetta. Se `propagateActivity` = `true`, questa attività viene unita con l'azione di processo "Cancel" dal servizio.|  
  
 Nella tabella seguente sono elencate tutte le attività riferite a COM+.  
  
|Nome attività|Tipo di attività|Descrizione|  
|-------------------|-------------------|-----------------|  
|Creazione istanza COM+|TransferToCOMPlus|È possibile creare una sola istanza di attività per ogni chiamata COM+ tramite codice [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]|  
|Eseguire COM+ \<operazione >|TransferToCOMPlus|È possibile creare una sola istanza di attività per ogni chiamata COM+ tramite codice [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]|  
  
## <a name="wmi-activities"></a>Attività WMI  
 Nella tabella seguente sono elencate tutte le attività riferite a WMI.  
  
|Nome attività|Tipo di attività|Descrizione|  
|-------------------|-------------------|-----------------|  
|Ottenimento WMI|WMIGetObject|Questa attività prevede il recupero di dati da WMI da parte dell'utente.|  
|Inserimento WMI|WmiPutInstance|Questa attività prevede l'aggiornamento dei dati tramite WMI da parte dell'utente|
