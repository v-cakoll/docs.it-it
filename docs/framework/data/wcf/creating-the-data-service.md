---
title: Creazione di un servizio dati WCF in Visual Studio
description: Informazioni su come creare un servizio dati di esempio che usa WCF Data Services per esporre un feed OData in base a un database di esempio.
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: 739cb6971209792724a2e939ca4f4821d5879c8c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247791"
---
# <a name="create-the-data-service"></a>Creazione del servizio dati

In questo argomento viene creato un servizio dati di esempio che usa WCF Data Services per esporre un feed di Open Data Protocol (OData) basato sul database di esempio Northwind. L'attività è costituita dai passaggi principali seguenti:

1. Creare un'applicazione Web ASP.NET.

2. Definizione del modello di dati tramite gli strumenti di Entity Data Model.

3. Aggiunta del servizio dati all'applicazione Web.

4. Abilitazione dell'accesso al servizio dati.

## <a name="create-the-aspnet-web-app"></a>Creare l'app Web ASP.NET

1. Nel menu **File** in Visual Studio selezionare **Nuovo** > **Progetto**.

1. Nella finestra di dialogo **nuovo progetto** , in Visual Basic o Visual C# selezionare la categoria **Web** e quindi selezionare **applicazione Web ASP.NET**.

1. Immettere `NorthwindService` come nome del progetto e quindi fare clic su **OK**.

1. Nella finestra di dialogo **nuova applicazione Web ASP.NET** selezionare **vuoto** e quindi fare clic su **OK**.

1. (Opzione facoltativa) Specificare un numero specifico di porta per l'applicazione Web. Nota: `12345` in questa serie di argomenti della Guida introduttiva viene usato il numero di porta.

    1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto ASP.NET appena creato, quindi scegliere **Proprietà**.

    2. Selezionare la scheda **Web** e impostare il valore della casella di testo **porta specifica** su `12345` .

## <a name="define-the-data-model"></a>Definizione del modello di dati

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nome del progetto ASP.NET, quindi scegliere **Aggiungi**  >  **nuovo elemento**.

2. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare la categoria di **dati** , quindi selezionare **ADO.NET Entity Data Model**.

3. Per il nome del modello di dati, immettere `Northwind.edmx` .

4. Nella **procedura guidata di Entity Data Model**selezionare **EF Designer from database**e quindi fare clic su **Next**.

5. Connettere il modello di dati al database effettuando una delle operazioni seguenti, quindi fare clic su **Avanti**:

    - Se non è già stata configurata una connessione di database, fare clic su **nuova connessione** e creare una nuova connessione. Per altre informazioni, vedere [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)). A questa istanza di SQL Server deve essere collegato il database Northwind di esempio.

         \- - oppure -

    - Se si dispone di una connessione al database già configurata per connettersi al database Northwind, selezionarla dall'elenco delle connessioni.

6. Nella pagina finale della procedura guidata, selezionare le caselle di controllo relative a tutte le tabelle nel database e deselezionare le caselle di controllo relative a visualizzazioni e stored procedure.

7. Fare clic su **Fine** per chiudere la procedura guidata.

## <a name="create-the-wcf-data-service"></a>Creare il servizio dati WCF

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto ASP.NET, quindi scegliere **Aggiungi**  >  **nuovo elemento**.

2. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare il modello di elemento **servizio dati WCF** dalla categoria **Web** .

   ![Modello di elemento del servizio dati WCF in Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Il modello di **servizio dati WCF** è disponibile in visual studio 2015, ma non in visual studio 2017 o versioni successive.

3. Per il nome del servizio, digitare `Northwind` .

     In Visual Studio verranno creati i file del markup XML e del codice per il nuovo servizio. Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice. In **Esplora soluzioni**il nome del servizio è Northwind con estensione *svc.cs* o *svc. vb*.

4. Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo del contenitore di entità del modello di dati, che in questo caso corrisponde a `NorthwindEntities`. La definizione di classe dovrà essere analoga alla seguente:

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a>Abilitare l'accesso alle risorse del servizio dati

1. Nel codice per il servizio dati sostituire il codice segnaposto nella funzione `InitializeService` con il codice seguente:

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]

     In questo modo i client autorizzati saranno in grado di accedere in lettura e scrittura alle risorse per i set di entità specificati.

    > [!NOTE]
    > I client che possono accedere all'applicazione ASP.NET saranno inoltre in grado di accedere alle risorse esposte dal servizio dati. Per impedire l'accesso non autorizzato alle risorse in un servizio dati di produzione, è inoltre necessario proteggere l'applicazione stessa. Per altre informazioni, vedere [Securing WCF Data Services](securing-wcf-data-services.md).

## <a name="next-steps"></a>Passaggi successivi

È stato creato un nuovo servizio dati che espone un feed OData basato sul database di esempio Northwind ed è stato abilitato l'accesso al feed per i client che dispongono delle autorizzazioni per l'applicazione Web ASP.NET. Successivamente, si avvierà il servizio dati da Visual Studio e si accede al feed OData inviando richieste HTTP GET tramite un Web browser:

> [!div class="nextstepaction"]
> [Accedere al servizio da un Web browser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a>Vedere anche

- [Strumenti Entity Data Model ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
