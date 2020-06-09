---
title: Elenco delle attività
ms.date: 03/30/2017
ms.assetid: 5540e185-ce8e-4db3-83b0-2b9f5bf71829
ms.openlocfilehash: 8d43cc878d54efbd4908f92c3405bef2c7956f94
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602167"
---
# <a name="activity-list"></a>Elenco delle attività
In questo argomento vengono elencate tutte le attività definite da Windows Communication Foundation (WCF).  
  
> [!NOTE]
> È inoltre possibile definire attività a livello di programmazione allo scopo di raggruppare più tracce utente. Per altre informazioni, vedere [creazione di tracce di codice utente](emitting-user-code-traces.md).  
  
## <a name="servicemodel-activities"></a>Attività ServiceModel  
 Nella tabella seguente sono elencate tutte le attività relative ai principali scenari di utilizzo.  
  
|Label|Nome attività|Tipo di attività|Descrizione|  
|-----------|-------------------|-------------------|-----------------|  
|A, M|Attività di ambiente|N/D (non controllata da ServiceModel)|Attività il cui ID viene impostato in TLS prima che venga effettuata qualsiasi chiamata al codice di ServiceModel, sia esso lato client o lato server.<br /><br /> Esempio: un'attività in cui viene chiamato il metodo Open sul client WCF o viene chiamato serviceHost. Open.|  
|b|Costrutto<br /><br /> ChannelFactory. ContractType : "[tipo]".|Costrutto||  
|C|Apri<br /><br /> [ClientBase&#124;ChannelFactory]. ContractType : "[tipo]".|Apri||  
|I|Close [ClientBase&#124;ChannelFactory]. ContractType : "[tipo]".|Chiudi||  
|M|Costruzione ServiceHost. ServiceType: "[tipo]".|Costrutto||  
|N|Apertura di ServiceHost. ServiceType: "[tipo]".|Apri||  
|Z|Chiusura di ServiceHost. ServiceType: "[tipo]".|Chiudi||  
|O|Attesa su "[indirizzo]".|ListenAt|Questa attività, così come la prossima, sono specifiche del trasporto. L'attività di tipo ListenAt rappresenta il contenuto che corrisponde all'indirizzo su cui il listener del canale è in attesa. Nel caso di MSMQ ciò corrisponde alla coda stessa, in quanto alla coda è associato un unico indirizzo. Nel caso di trasporti orientati alla connessione, questa attività resta in attesa di connessioni in ingresso. Nel caso di MSMQ, invece, questa attività resta in attesa di messaggi MSMQ. Infine, questa attività viene creata durante l'attività ServiceHost.Open () e contiene le tracce riferite alla creazione e all'eliminazione del listener nonché al trasferimento dell'esecuzione a tutte le attività di tipo ReceiveBytes.|  
|P|Ricezione byte sulla connessione "[indirizzo]". Ricezione messaggio MSMQ.|ReceiveBytes|In questa attività verranno elaborati i dati che alla fine riceveranno un messaggio WCF. Nel caso di trasporto orientato alla connessione o del protocollo HTTP, il sistema attende i byte in ingresso. Nel caso del protocollo TCP/pipe con nome, la durata di questa attività corrisponde alla durata della connessione, in quanto il momento di creazione dell'attività coincide con quello di creazione della connessione. Nel caso del protocollo HTTP, la durata di questa attività corrisponde a quella di una richiesta di messaggio e viene considerata a partire dal momento in cui il messaggio viene inviato. Questa attività, se applicabile, contiene le tracce riferite alla creazione e all'eliminazione della connessione nonché al trasferimento dell'esecuzione a tutte le attività di elaborazione di messaggi (ovvero di oggetti).<br /><br /> Nel caso di MSMQ, questa attività corrisponde a quella da cui viene recuperato il messaggio MSMQ.|  
|Q|Elaborazione messaggio [numero]. Nota: il parametro [numero] è un valore monotonicamente crescente inizialmente pari a 1.|ProcessMessage|Questa attività prevede l'elaborazione di un messaggio in ingresso Questa attività viene avviata quando vengono ricevuti tutti i dati (byte, messaggio MSMQ) per formare un oggetto messaggio WCF. Le tracce contenute in questa attività riguardano l'elaborazione delle intestazioni.<br /><br /> Dopo aver formato un messaggio che può essere inviato e dopo aver ricercato l'ID attività corrispondente, il sistema passa all'attività ServiceHost ProcessAction.|  
|D, S|Elaborazione azione "[azione]".|ProcessAction|Questa attività prevede l'elaborazione del messaggio attraverso lo stack Trasporto/Sicurezza/RM per inviare il messaggio al codice utente al momento della ricezione e restituire il messaggio sul percorso inverso al momento dell'invio.<br /><br /> Nel server, questa attività utilizza l'ID attività propagata se viene inviato nell'intestazione del messaggio tramite "propagazione attività"; in caso contrario, viene creato un nuovo GUID.<br /><br /> In questa attività viene inoltre elaborato il messaggio di risposta dei contratti di Request/Reply.|  
|T|Esecuzione "[IContratto.Operazione]".|ExecuteUserCode|Questa attività prevede l'esecuzione del codice utente dopo l'invio al lato server e rappresenta una linea di delimitazione fra il codice ServiceHost e il codice fornito dall'utente.|  
  
## <a name="security-activities"></a>Attività di sicurezza  
 Nella tabella seguente sono elencate tutte le attività riferite alla sicurezza.  
  
|Nome attività|Tipo di attività|Descrizione|  
|-------------------|-------------------|-----------------|  
|Impostazione sessione protetta|SetupSecurity|Esiste soltanto sul lato client. Contiene tutti gli scambi RST*/SCT per eseguire l'autenticazione e l'impostazione del contesto di sicurezza. Se `propagateActivity` = `true` , questa attività viene unita alle attività di RST/SCT dell'azione di processo corrispondente del servizio \* .|  
|Chiusura sessione protetta|SetupSecurity|Esiste sul lato client. Contiene lo scambio di messaggi di annullamento per eseguire la chiusura della sessione protetta. Se `propagateActivity` = `true` , questa attività viene unita all'azione di elaborazione "Annulla" del servizio.|  
  
 Nella tabella seguente sono elencate tutte le attività riferite a COM+.  
  
|Nome attività|Tipo di attività|Descrizione|  
|-------------------|-------------------|-----------------|  
|Creazione istanza COM+|TransferToCOMPlus|1 istanza di attività per ogni chiamata COM+ dal codice WCF|  
|Esegui COM+\<operation>|TransferToCOMPlus|1 istanza di attività per ogni chiamata COM+ dal codice WCF|  
  
## <a name="wmi-activities"></a>Attività WMI  
 Nella tabella seguente sono elencate tutte le attività riferite a WMI.  
  
|Nome attività|Tipo di attività|Descrizione|  
|-------------------|-------------------|-----------------|  
|Ottenimento WMI|WMIGetObject|Questa attività prevede il recupero di dati da WMI da parte dell'utente.|  
|Inserimento WMI|WmiPutInstance|Questa attività prevede l'aggiornamento dei dati tramite WMI da parte dell'utente|
