---
title: Rilevamento SQL
ms.date: 03/30/2017
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
ms.openlocfilehash: 88f44e5362684f755695aab154842fad2274134d
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094592"
---
# <a name="sql-tracking"></a>Rilevamento SQL
In questo esempio viene illustrato come scrivere un partecipante del rilevamento SQL personalizzato che scrive record di rilevamento in un database SQL. Windows Workflow Foundation (WF) fornisce il rilevamento del flusso di lavoro per ottenere visibilità nell'esecuzione di un'istanza del flusso di lavoro. Il runtime di rilevamento crea record di rilevamento del flusso di lavoro durante l'esecuzione di quest'ultimo. Per ulteriori informazioni sul rilevamento del flusso di lavoro, vedere [rilevamento e traccia del flusso di lavoro](../workflow-tracking-and-tracing.md).

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1. Verificare di avere installato SQL Server 2008, SQL Server 2008 Express o una versione più recente. Gli script impacchettati con l'esempio presuppongono l'uso di un'istanza di SQL Express sul computer locale. Se si dispone di un'istanza diversa, modificare gli script correlati al database prima di eseguire l'esempio.

2. Creare il database di rilevamento di SQL Server eseguendo Trackingsetup.cmd nella directory degli script (\WF\Basic\Tracking\SqlTracking\CS\Scripts). Verrà creato un database denominato TrackingSample.

    > [!NOTE]
    > Lo script crea il database nell'istanza predefinita di SQL Express. Se si desidera installarlo in un'istanza di database diversa, modificare lo script Trackingsetup.cmd.

3. Aprire SqlTrackingSample. sln in Visual Studio 2010.

4. Premere CTRL+MAIUSC+B per compilare la soluzione.

5. Premere F5 per eseguire l'applicazione.

     Viene aperta la finestra del browser in cui viene mostrata la visualizzazione directory per l'applicazione.

6. Nel browser fare clic su StockPriceService.xamlx.

7. Nel browser viene visualizzata la pagina StockPriceService contenente l'indirizzo WSDL del servizio locale. Copiare questo indirizzo.

     Un esempio di indirizzo WSDL del servizio locale è `http://localhost:65193/StockPriceService.xamlx?wsdl`.

8. Utilizzando Esplora file, eseguire il client di prova WCF (WcfTestClient. exe). che si trova nella directory Microsoft Visual Studio 10.0\Common7\IDE.

9. Nel client di prova WCF fare clic sul menu **file** e selezionare **Aggiungi servizio**. Incollare l'indirizzo del servizio locale nella casella di testo. Fare clic su **OK** per chiudere la finestra di dialogo.

10. Nel client di prova WCF fare doppio clic su **GetStockPrice**. Verrà visualizzata l'operazione `GetStockPrice` che accetta un parametro, digitare il valore `Contoso` e fare clic su **richiama**.

11. I record di rilevamento creati vengono scritti in un database SQL. Per visualizzare i record di rilevamento, aprire il database TrackingSample in SQL Management Studio e passare alle tabelle. Per ulteriori informazioni su SQL Server Management Studio, vedere [introduzione SQL Server Management Studio](/sql/ssms/sql-server-management-studio-ssms). SQL Server 2008 Management Studio Express è possibile scaricarlo [qui](https://www.microsoft.com/download/details.aspx?id=7593). Eseguendo una query di selezione sulle tabelle vengono visualizzati i dati all'interno dei record di rilevamento archiviati nelle rispettive tabelle.

#### <a name="to-uninstall-the-sample"></a>Per disinstallare l'esempio

1. Eseguire lo script Trackingcleanup.cmd nella directory di esempio (\WF\Basic\Tracking\SqlTracking).

    > [!NOTE]
    > Trackingcleanup.cmd tenta di eliminare il database nel computer locale SQL Express. Se si usa un'altra istanza di SQL Server, modificare Trackingcleanup.cmd.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`

## <a name="see-also"></a>Vedere anche

- [Esempi di monitoraggio di AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
