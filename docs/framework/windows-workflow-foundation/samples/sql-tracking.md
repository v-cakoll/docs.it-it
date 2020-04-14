---
title: Rilevamento SQL
ms.date: 03/30/2017
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
ms.openlocfilehash: 72bfcaac2903b3e7fa5679422ad4feaa79e93211
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243180"
---
# <a name="sql-tracking"></a>Rilevamento SQL

In questo esempio viene illustrato come scrivere un partecipante di rilevamento SQL personalizzato che scrive i record di rilevamento in un database SQL. Windows Workflow Foundation (WF) fornisce il rilevamento del flusso di lavoro per ottenere visibilità sull'esecuzione di un'istanza del flusso di lavoro. Il runtime di rilevamento crea record di rilevamento del flusso di lavoro durante l'esecuzione di quest'ultimo. Per ulteriori informazioni sul rilevamento del flusso di lavoro, vedere [Rilevamento e traccia del flusso di lavoro](../workflow-tracking-and-tracing.md).

## <a name="use-the-sample"></a>Usare l'esempio

1. Verificare di avere installato SQL Server 2008, SQL Server 2008 Express o una versione più recente. Gli script impacchettati con l'esempio presuppongono l'uso di un'istanza di SQL Express sul computer locale. Se si dispone di un'istanza diversa, modificare gli script correlati al database prima di eseguire l'esempio.

2. Creare il database di rilevamento di SQL Server eseguendo Trackingsetup.cmd nella directory degli script (\WF\Basic\Tracking\SqlTracking\CS\Scripts). Verrà creato un database denominato TrackingSample.

   > [!NOTE]
   > Lo script crea il database nell'istanza predefinita di SQL Express. Se si desidera installarlo in un'istanza di database diversa, modificare lo script Trackingsetup.cmd.

3. Aprire SqlTrackingSample.sln in Visual Studio 2010.Open SqlTrackingSample.sln in Visual Studio 2010.

4. Premere **Ctrl**+**Maiusc**+**B** per compilare la soluzione.

5. Premere **F5** per eseguire l'applicazione.

   Viene aperta la finestra del browser in cui viene mostrata la visualizzazione directory per l'applicazione.

6. Nel browser fare clic su StockPriceService.xamlx.

7. Nel browser viene visualizzata la pagina StockPriceService contenente l'indirizzo WSDL del servizio locale. Copiare questo indirizzo.

   Un esempio dell'indirizzo WSDL `http://localhost:65193/StockPriceService.xamlx?wsdl`del servizio locale è .

8. Utilizzando Esplora file, eseguire il client di test WCF (WcfTestClient.exe). Si trova nella *directory di Microsoft Visual Studio 10.0, Common7, IDE*.

9. Nel client di test WCF, fare clic sul menu **File** e selezionare **Aggiungi servizio**. Incollare l'indirizzo del servizio locale nella casella di testo. Fare clic su **OK** per chiudere la finestra di dialogo.

10. Nel client di test WCF fare doppio clic su **GetStockPrice**. Verrà aperta `GetStockPrice` l'operazione che accetta un `Contoso` parametro, digitare il valore e fare clic su **Richiama**.

11. I record di rilevamento creati vengono scritti in un database SQL. Per visualizzare i record di rilevamento, aprire il database TrackingSample in SQL Management Studio e passare alle tabelle. Eseguendo una query di selezione sulle tabelle vengono visualizzati i dati all'interno dei record di rilevamento archiviati nelle rispettive tabelle.

   Per ulteriori informazioni su SQL Server Management Studio, vedere [Introduzione a SQL Server Management Studio.](/sql/ssms/sql-server-management-studio-ssms) Scaricare SQL Server Management Studio [qui](https://aka.ms/ssmsfullsetup).

## <a name="uninstall-the-sample"></a>Disinstallare l'esempio

1. Eseguire lo script Trackingcleanup.cmd nella directory di esempio (*.*

    > [!NOTE]
    > Trackingcleanup.cmd tenta di eliminare il database nel computer locale SQL Express. Se si usa un'altra istanza di SQL Server, modificare Trackingcleanup.cmd.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`

## <a name="see-also"></a>Vedere anche

- [Monitoraggio](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
