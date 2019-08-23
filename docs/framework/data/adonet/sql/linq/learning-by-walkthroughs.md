---
title: Apprendimento tramite procedure dettagliate
ms.date: 03/30/2017
ms.assetid: a8ae2965-6a49-4155-89b0-7fab2c488ab1
ms.openlocfilehash: f1061842343d7a700d3af5da5fdc6aec2f79396d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929218"
---
# <a name="learning-by-walkthroughs"></a>Apprendimento tramite procedure dettagliate
La [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentazione fornisce diverse procedure dettagliate. In questo argomento vengono discussi alcuni problemi generali relativi alle procedure, inclusa la risoluzione dei problemi, e vengono forniti i collegamenti a diverse procedure dettagliate di base per acquisire familiarità con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
> [!NOTE]
> Nelle procedure dettagliate disponibili in questa sezione della Guida introduttiva viene esposto il codice di base che supporta la tecnologia [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. In pratica, si utilizzeranno in genere i progetti Object Relational Designer e Windows Forms per implementare le [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applicazioni. La documentazione di O/R Designer fornisce esempi e procedure dettagliate a questo scopo.  
  
## <a name="getting-started-walkthroughs"></a>Procedure dettagliate della Guida introduttiva  
 In questa sezione sono disponibili diverse procedure dettagliate basate sul database di esempio Northwind, in cui vengono presentate passo passo e con minime complessità le funzionalità di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 Di seguito è riportato l'ordine di esecuzione tipico che si consiglia di seguire:  
  
|Obiettivo|Visual Basic|C#|  
|---------------|------------------|---------|  
|Creare una classe di entità ed eseguire una semplice query.|[Procedura dettagliata: Modello a oggetti e query semplici (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-visual-basic.md)|[Procedura dettagliata: Modello a oggetti e query sempliciC#()](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-csharp.md)|  
|Aggiungere una seconda classe ed eseguire una query più complessa.<br /><br /> Richiede il completamento della procedura dettagliata precedente.|[Procedura dettagliata: Esecuzione di query tra relazioni (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md)|[Procedura dettagliata: Esecuzione di query tra relazioniC#()](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-csharp.md)|  
|Aggiungere, modificare ed eliminare elementi nel database.|[Procedura dettagliata: Manipolazione dei dati (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-visual-basic.md)|[Procedura dettagliata: Manipolazione di dati (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-csharp.md)|  
|Usare stored procedure.|[Procedura dettagliata: Utilizzo solo di stored procedure (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)|[Procedura dettagliata: Utilizzo solo di stored procedureC#()](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)|  
  
## <a name="general"></a>Generale  
 Le informazioni seguenti riguardano queste procedure dettagliate in generale:  
  
- Ambiente: Ogni [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] procedura dettagliata usa Visual Studio come Integrated Development Environment (IDE).  
  
- Motori SQL: Queste procedure dettagliate vengono scritte per essere implementate tramite SQL Server Express. Se non si dispone di SQL Server Express, è possibile scaricarlo gratuitamente. Per ulteriori informazioni, vedere [download di database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
    > [!NOTE]
    > Nelle procedure dettagliate di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene usato un nome file come stringa di connessione. La possibilità di specificare semplicemente un nome file è un aspetto pratico di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per gli utenti di SQL Server Express. Prestare sempre attenzione ai problemi di sicurezza. Per ulteriori informazioni, vedere [sicurezza in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md).  
  
- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]per le procedure dettagliate è in genere necessario il database di esempio Northwind. Per ulteriori informazioni, vedere [download di database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
- Le finestre di dialogo e i comandi di menu visualizzati nelle procedure dettagliate potrebbero essere diversi da quelli descritti nella Guida, a seconda delle impostazioni attive o dell'edizione di Visual Studio. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
- Per le procedure dettagliate che riguardano scenari a più livelli è necessario che il computer configurato come server sia diverso dal computer di sviluppo. Inoltre è necessario disporre delle autorizzazioni appropriate per accedere al server.  
  
- Il nome della classe che in genere rappresenta la tabella Orders nel database di esempio Northwind è `[Order]`. L'escape è obbligatorio perché `Order` è una parola chiave in Visual Basic.  
  
## <a name="troubleshooting"></a>Risoluzione dei problemi  
 Possono verificarsi errori di runtime in quanto non si dispone di sufficienti autorizzazioni per accedere ai database usati in queste procedure dettagliate. Vedere i passaggi seguenti per risolvere il più comune di questi problemi.  
  
### <a name="log-on-issues"></a>Problemi di accesso  
 L'applicazione potrebbe tentare di accedere al database usando credenziali di accesso non accettate.  
  
##### <a name="to-verify-or-change-the-database-log-on"></a>Per verificare o modificare l'accesso al database  
  
1. Dal menu **Start** di Windows scegliere **tutti i programmi**, **Microsoft SQL Server 2005**, scegliere **strumenti di configurazione**, quindi fare clic su **Gestione configurazione SQL Server**.  
  
2. Nel riquadro sinistro della **Gestione configurazione SQL Server**fare clic su **SQL Server servizi di 2005**.  
  
3. Nel riquadro destro fare clic con il pulsante destro del mouse su **SQL Server (SQLEXPRESS)** , quindi scegliere **Proprietà**.  
  
4. Fare clic sulla scheda **accesso** e verificare il modo in cui si sta tentando di accedere al server.  
  
     Nella maggior parte dei casi, il **sistema locale** funziona.  
  
     Se si effettua una modifica, fare clic su **Riavvia** per riavviare il servizio.  
  
### <a name="protocols"></a>Protocolli  
 A volte i protocolli possono non essere impostati correttamente per l'accesso dell'applicazione al database. Il protocollo **Named Pipes** , che è necessario per le procedure dettagliate in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], ad esempio, non è abilitato per impostazione predefinita.  
  
##### <a name="to-enable-the-named-pipes-protocol"></a>Per abilitare il protocollo Named Pipes  
  
1. Nel riquadro sinistro del **Gestione configurazione SQL Server**espandere **SQL Server configurazione di rete 2005**e quindi fare clic su **protocolli per SQLEXPRESS**.  
  
2. Nel riquadro destro verificare che sia abilitato il protocollo **Named Pipes** . In caso contrario, fare clic con il pulsante destro del mouse su Named Pipes, quindi scegliere **Abilita**.  
  
     Sarà necessario arrestare e riavviare il servizio. Eseguire i passaggi illustrati nel blocco successivo.  
  
### <a name="stopping-and-restarting-the-service"></a>Arresto e riavvio del servizio  
 È necessario arrestare e riavviare i servizi per rendere effettive le modifiche.  
  
##### <a name="to-stop-and-restart-the-service"></a>Per arrestare e riavviare il servizio  
  
1. Nel riquadro sinistro della **Gestione configurazione SQL Server**fare clic su **SQL Server servizi di 2005**.  
  
2. Nel riquadro destro fare clic con il pulsante destro del mouse su **SQL Server (SQLEXPRESS)** , quindi scegliere **Arresta**.  
  
3. Fare clic con il pulsante destro del mouse su **SQL Server (SQLEXPRESS)** , quindi scegliere **Riavvia**.  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
