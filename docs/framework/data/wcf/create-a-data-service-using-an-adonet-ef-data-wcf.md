---
title: "Procedura: creare un servizio dati tramite un'origine dati ADO.NET Entity Framework (WCF Data Services)"
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
ms.openlocfilehash: 0aea4c21b5ea34cb0e8d944d37c879e918d6b27e
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74800594"
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a>Procedura: creare un servizio dati tramite un'origine dati ADO.NET Entity Framework (WCF Data Services)

WCF Data Services espone i dati di entità come servizio dati. Questi dati dell'entità vengono forniti dal framework ADO. NETEntity quando l'origine dati è un database relazionale. In questo argomento viene illustrato come creare un modello di dati basato su Entity Framework in un'applicazione Web di Visual Studio basata su un database esistente e come utilizzare questo modello di dati per creare un nuovo servizio dati.

Entity Framework fornisce inoltre un strumento da riga di comando che può generare un modello di Entity Framework all'esterno di un progetto di Visual Studio. Per altre informazioni, vedere [procedura: usare EdmGen. exe per generare i file di modello e di mapping](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).

## <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a>Per aggiungere un modello di Entity Framework basato su un database esistente a un'applicazione Web esistente

1. Scegliere **aggiungi** > **nuovo elemento**dal menu **progetto** .

2. Nel riquadro **modelli** fare clic sulla categoria di **dati** , quindi selezionare **ADO.NET Entity Data Model**.

3. Immettere il nome del modello e quindi fare clic su **Aggiungi**.

     Verrà visualizzata la prima pagina della procedura guidata Entity Data Model.

4. Nella finestra di dialogo **Scegli contenuto Model** selezionare **genera da database**. Fare quindi clic su **Avanti**.

5. Fare clic sul pulsante **nuova connessione** .

6. Nella finestra di dialogo **Proprietà connessione** Digitare il nome del server, selezionare il metodo di autenticazione, digitare il nome del database, quindi fare clic su **OK**.

     La finestra di dialogo **scegliere la connessione dati** viene aggiornata con le impostazioni di connessione del database.

7. Verificare che la casella **di controllo Salva le impostazioni di connessione dell'entità in app. config come:** sia selezionata. Fare quindi clic su **Avanti**.

8. Nella finestra di dialogo **Scegli oggetti di database** selezionare tutti gli oggetti di database che si intende esporre nel servizio dati.

    > [!NOTE]
    > Gli oggetti inclusi nel modello di dati non vengono esposti automaticamente dal servizio dati. Devono essere esposti in modo esplicito mediante il servizio stesso. Per ulteriori informazioni, vedere [configurazione del servizio dati](configuring-the-data-service-wcf-data-services.md).

9. Fare clic su **Fine** per completare la procedura guidata.

     Verrà creato un modello di dati predefinito in base al database specifico. Entity Framework consente di personalizzare il modello di dati. Per ulteriori informazioni, vedere [attività di Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).

## <a name="to-create-the-data-service-by-using-the-new-data-model"></a>Per creare il servizio dati usando il nuovo modello di dati

1. In Visual Studio aprire il file con estensione edmx che rappresenta il modello di dati.

2. In **browser modello**fare clic con il pulsante destro del mouse sul modello, scegliere **Proprietà**, quindi prendere nota del nome del contenitore di entità.

3. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nome del progetto ASP.NET, quindi scegliere **Aggiungi** > **nuovo elemento**.

4. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare il modello **WCF Data Services** nella categoria **Web** .

   ![Modello di elemento del servizio dati WCF in Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Il modello di **servizio dati WCF** è disponibile in visual studio 2015, ma non in visual studio 2017 o versioni successive.

5. Specificare un nome per il servizio, quindi fare clic su **OK**.

     In Visual Studio verranno creati i file del markup XML e del codice per il nuovo servizio. Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice.

6. Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo che eredita dalla classe <xref:System.Data.Objects.ObjectContext> e che rappresenta il contenitore di entità del modello di dati annotato nel passaggio 2.

7. Nel codice per il servizio dati consentire ai client autorizzati di accedere ai set di entità esposti dal servizio dati. Per ulteriori informazioni, vedere [creazione del servizio dati](creating-the-data-service.md).

8. Per testare il servizio dati Northwind. svc utilizzando una Web browser, seguire le istruzioni riportate nell'argomento [accesso al servizio da un Web browser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).

## <a name="see-also"></a>Vedere anche

- [Definizione di WCF Data Services](defining-wcf-data-services.md)
- [Provider di servizi dati](data-services-providers-wcf-data-services.md)
- [Procedura: creare un servizio dati tramite il provider di reflection](create-a-data-service-using-rp-wcf-data-services.md)
- [Procedura: creare un servizio dati tramite un'origine dati LINQ to SQL](create-a-data-service-using-linq-to-sql-wcf.md)
