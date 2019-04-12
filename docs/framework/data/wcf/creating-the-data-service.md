---
title: Creare un servizio dati WCF in Visual Studio
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: e8d82ff8958af12842366911b6633ea6b2e0efbb
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/12/2019
ms.locfileid: "59517226"
---
# <a name="create-the-data-service"></a>Creazione del servizio dati

In questo argomento, si crea un servizio dati di esempio che utilizza WCF Data Services per esporre un [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed basato sul database Northwind di esempio. L'attività è costituita dai passaggi principali seguenti:

1. Creare un'applicazione Web ASP.NET.

2. Definizione del modello di dati tramite gli strumenti di Entity Data Model.

3. Aggiunta del servizio dati all'applicazione Web.

4. Abilitazione dell'accesso al servizio dati.

## <a name="create-the-aspnet-web-app"></a>Creare l'app web ASP.NET

1. In Visual Studio sul **File** dal menu **New** > **progetto**.

1. Nel **nuovo progetto** della finestra di dialogo in Visual Basic o Visual c#, selezionare la **Web** categoria e quindi selezionare **applicazione Web ASP.NET**.

1. Immettere `NorthwindService` come nome del progetto e quindi selezionare **OK**.

1. Nel **nuova applicazione Web ASP.NET** finestra di dialogo, seleziona **vuota** e quindi selezionare **OK**.

1. (Opzione facoltativa) Specificare un numero specifico di porta per l'applicazione Web. Nota: il numero della porta `12345` viene usato in questa serie di argomenti della Guida rapida.

    1. Nelle **Esplora soluzioni**destro del mouse sul progetto ASP.NET appena creato e quindi scegliere **proprietà**.

    2. Selezionare il **Web** scheda e impostare il valore della **porta specifica** casella di testo `12345`.

## <a name="define-the-data-model"></a>Definizione del modello di dati

1. Nelle **Esplora soluzioni**, fare doppio clic il nome del progetto ASP.NET e quindi fare clic su **Add** > **nuovo elemento**.

2. Nel **Aggiungi nuovo elemento** finestra di dialogo, seleziona la **Data** categoria e quindi selezionare **ADO.NET Entity Data Model**.

3. Immettere il nome del modello di dati, `Northwind.edmx`.

4. Nel **procedura guidata Entity Data Model**, selezionare **Entity Framework Designer da Database**, quindi fare clic su **Avanti**.

5. Connettere il modello di dati al database effettuando una delle operazioni seguenti e quindi fare clic su **successivo**:

    -   Se non si dispone di una connessione al database già configurata, fare clic su **nuova connessione** e creare una nuova connessione. Per altre informazioni, vedere [Procedura: Creare connessioni a database di SQL Server](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)). A questa istanza di SQL Server deve essere collegato il database Northwind di esempio.

         \- oppure -

    -   Se si dispone di una connessione al database già configurata per connettersi al database Northwind, selezionarla dall'elenco delle connessioni.

6. Nella pagina finale della procedura guidata, selezionare le caselle di controllo relative a tutte le tabelle nel database e deselezionare le caselle di controllo relative a visualizzazioni e stored procedure.

7. Fare clic su **fine** per chiudere la procedura guidata.

## <a name="create-the-wcf-data-service"></a>Creare il servizio dati WCF

1. Nelle **Esplora soluzioni**destro del mouse sul progetto ASP.NET e quindi scegliere **Add** > **nuovo elemento**.

2. Nel **Aggiungi nuovo elemento** finestra di dialogo, seleziona la **WCF Data Services** modello di elemento dal **Web** categoria.

   ![Modello di elemento di WCF Data Services in Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Il **di WCF Data Services** modello è disponibile in Visual Studio 2015, ma non in Visual Studio 2017.

3. Per il nome del servizio, digitare `Northwind`.

     In Visual Studio verranno creati i file del markup XML e del codice per il nuovo servizio. Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice. Nelle **Esplora soluzioni**, il servizio ha il denominato Northwind con estensione *. svc.cs* oppure *. svc*.

4. Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo del contenitore di entità del modello di dati, che in questo caso corrisponde a `NorthwindEntities`. La definizione di classe dovrà essere analoga alla seguente:

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a>Abilitare l'accesso alle risorse del servizio dati

1. Nel codice per il servizio dati sostituire il codice segnaposto nella funzione `InitializeService` con il codice seguente:

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]

     In questo modo i client autorizzati saranno in grado di accedere in lettura e scrittura alle risorse per i set di entità specificati.

    > [!NOTE]
    > I client che possono accedere all'applicazione ASP.NET saranno inoltre in grado di accedere alle risorse esposte dal servizio dati. Per impedire l'accesso non autorizzato alle risorse in un servizio dati di produzione, è inoltre necessario proteggere l'applicazione stessa. Per altre informazioni, vedere [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).

## <a name="next-steps"></a>Passaggi successivi

Avere creato un nuovo servizio dati che espone un feed OData che è basato sul database di esempio Northwind ed è stato abilitato l'accesso al feed per i client che dispone delle autorizzazioni per l'applicazione Web ASP.NET. Quindi verrà avviare il servizio dati da Visual Studio e accedere ai feed inviando richieste GET HTTP attraverso un browser Web OData:

> [!div class="nextstepaction"]
> [Accedere al servizio da un web browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a>Vedere anche

- [Strumenti di ADO.NET Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))