---
title: Apprendimento tramite procedure dettagliate
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8ae2965-6a49-4155-89b0-7fab2c488ab1
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 38961451a51ae47d05d7625ee0e83da97261eb0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="learning-by-walkthroughs"></a>Apprendimento tramite procedure dettagliate
Il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentazione vengono fornite diverse procedure dettagliate. In questo argomento vengono discussi alcuni problemi generali relativi alle procedure, inclusa la risoluzione dei problemi, e vengono forniti i collegamenti a diverse procedure dettagliate di base per acquisire familiarità con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
> [!NOTE]
>  Nelle procedure dettagliate disponibili in questa sezione della Guida introduttiva viene esposto il codice di base che supporta la tecnologia [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. In pratica, si useranno i progetti di [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] e Windows Form per implementare le applicazioni [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Nella documentazione di [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] vengono forniti esempi e procedure dettagliate a questo scopo.  
  
## <a name="getting-started-walkthroughs"></a>Procedure dettagliate della Guida introduttiva  
 In questa sezione sono disponibili diverse procedure dettagliate basate sul database di esempio Northwind, in cui vengono presentate passo passo e con minime complessità le funzionalità di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 Di seguito è riportato l'ordine di esecuzione tipico che si consiglia di seguire:  
  
|Obiettivo|Visual Basic|C#|  
|---------------|------------------|---------|  
|Creare una classe di entità ed eseguire una semplice query.|[Procedura dettagliata: Modello a oggetti semplice e Query (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-visual-basic.md)|[Procedura dettagliata: Modello a oggetti semplice e Query (c#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-csharp.md)|  
|Aggiungere una seconda classe ed eseguire una query più complessa.<br /><br /> Richiede il completamento della procedura dettagliata precedente.|[Procedura dettagliata: Eseguire query tra relazioni (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md)|[Procedura dettagliata: Eseguire query tra relazioni (c#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-csharp.md)|  
|Aggiungere, modificare ed eliminare elementi nel database.|[Procedura dettagliata: Modifica dei dati (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-visual-basic.md)|[Procedura dettagliata: Modifica dei dati (c#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-csharp.md)|  
|Usare stored procedure.|[Procedura dettagliata: Utilizzo solo di Stored procedure (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)|[Procedura dettagliata: Utilizzo solo di Stored procedure (c#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)|  
  
## <a name="general"></a>Generale  
 Le informazioni seguenti riguardano queste procedure dettagliate in generale:  
  
-   Ambiente: in ogni procedura dettagliata di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene usato [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] come ambiente di sviluppo integrato (IDE).  
  
-   Motori SQL: queste procedure dettagliate sono scritte per essere implementate tramite SQL Server Express. Se non si dispone di SQL Server Express, è possibile scaricarlo gratuitamente. Per ulteriori informazioni, vedere [download dei database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
    > [!NOTE]
    >  Nelle procedure dettagliate di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene usato un nome file come stringa di connessione. La possibilità di specificare semplicemente un nome file è un aspetto pratico di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per gli utenti di SQL Server Express. Prestare sempre attenzione ai problemi di sicurezza. Per ulteriori informazioni, vedere [sicurezza in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md).  
  
-   [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]procedure dettagliate in genere richiedono il database di esempio Northwind. Per ulteriori informazioni, vedere [download dei database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
-   Le finestre di dialogo e i comandi di menu visualizzati nelle procedure dettagliate potrebbero non corrispondere a quelli descritti nella Guida, in quanto dipendono dalle impostazioni o dall'edizione di [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] in uso. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
-   Per le procedure dettagliate che riguardano scenari a più livelli è necessario che il computer configurato come server sia diverso dal computer di sviluppo. Inoltre è necessario disporre delle autorizzazioni appropriate per accedere al server.  
  
-   Il nome della classe che in genere rappresenta la tabella Orders nel database di esempio Northwind è `[Order]`. L'uso di caratteri di escape è obbligatorio, poiché `Order` è una parola chiave in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)].  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Possono verificarsi errori di runtime in quanto non si dispone di sufficienti autorizzazioni per accedere ai database usati in queste procedure dettagliate. Vedere i passaggi seguenti per risolvere il più comune di questi problemi.  
  
### <a name="log-on-issues"></a>Problemi di accesso  
 L'applicazione potrebbe tentare di accedere al database usando credenziali di accesso non accettate.  
  
##### <a name="to-verify-or-change-the-database-log-on"></a>Per verificare o modificare l'accesso al database  
  
1.  Di Windows **avviare** dal menu **tutti i programmi**, **Microsoft SQL Server 2005**, scegliere **strumenti di configurazione**, quindi fare clic su **Gestione configurazione SQL Server**.  
  
2.  Nel riquadro sinistro della finestra di **Gestione configurazione SQL Server**, fare clic su **servizi di SQL Server 2005**.  
  
3.  Nel riquadro di destra, fare doppio clic su **SQL Server (SQLEXPRESS)**, quindi fare clic su **proprietà**.  
  
4.  Fare clic su di **accesso** scheda e verificare come si sta tentando di accedere al server.  
  
     Nella maggior parte dei casi, **sistema locale** funziona.  
  
     Se si apporta una modifica, fare clic su **riavviare** per riavviare il servizio.  
  
### <a name="protocols"></a>Protocolli  
 A volte i protocolli possono non essere impostati correttamente per l'accesso dell'applicazione al database. Ad esempio, il **Named Pipes** protocollo, è necessario per le procedure dettagliate in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], non è abilitato per impostazione predefinita.  
  
##### <a name="to-enable-the-named-pipes-protocol"></a>Per abilitare il protocollo Named Pipes  
  
1.  Nel riquadro sinistro della finestra di **Gestione configurazione SQL Server**, espandere **la configurazione di rete SQL Server 2005**e quindi fare clic su **protocolli per SQLEXPRESS**.  
  
2.  Nel riquadro di destra, assicurarsi che il **Named Pipes** protocollo è abilitato. In caso contrario, fare doppio clic su **Named Pipes** e quindi fare clic su **abilitare**.  
  
     Sarà necessario arrestare e riavviare il servizio. Eseguire i passaggi illustrati nel blocco successivo.  
  
### <a name="stopping-and-restarting-the-service"></a>Arresto e riavvio del servizio  
 È necessario arrestare e riavviare i servizi per rendere effettive le modifiche.  
  
##### <a name="to-stop-and-restart-the-service"></a>Per arrestare e riavviare il servizio  
  
1.  Nel riquadro sinistro della finestra di **Gestione configurazione SQL Server**, fare clic su **servizi di SQL Server 2005**.  
  
2.  Nel riquadro di destra, fare doppio clic su **SQL Server (SQLEXPRESS)**, quindi fare clic su **arrestare**.  
  
3.  Fare doppio clic su **SQL Server (SQLEXPRESS)**, quindi fare clic su **riavviare**.  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
