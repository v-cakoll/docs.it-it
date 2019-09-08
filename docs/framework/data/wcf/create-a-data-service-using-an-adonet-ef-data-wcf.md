---
title: "Procedura: Creazione di un servizio dati tramite un'origine dati ADO.NET Entity Framework (WCF Data Services)"
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
ms.openlocfilehash: ae4176fd986f870523e44a11eee48850e2dddd7c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791084"
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a>Procedura: Creazione di un servizio dati tramite un'origine dati ADO.NET Entity Framework (WCF Data Services)

WCF Data Services espone i dati di entità come servizio dati. I dati dell'entità vengono forniti da ADO.NET[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] quando l'origine dati è un database relazionale. In questo argomento viene illustrato come creare [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]un modello di dati basato su in un'applicazione Web di Visual Studio basata su un database esistente e utilizzare questo modello di dati per creare un nuovo servizio dati.

Fornisce inoltre uno strumento da riga di comando che può generare [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] un modello all'esterno di un progetto di Visual Studio. [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Per altre informazioni, vedere [Procedura: Utilizzare EdmGen. exe per generare i file](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)di modello e di mapping.

## <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a>Per aggiungere un modello di Entity Framework basato su un database esistente a un'applicazione Web esistente

1. Scegliere **Aggiungi** > **nuovo elemento**dal menu **progetto** .

2. Nel riquadro **modelli** fare clic sulla categoria di **dati** , quindi selezionare **ADO.NET Entity Data Model**.

3. Immettere il nome del modello e quindi fare clic su **Aggiungi**.

     Verrà visualizzata la prima pagina della procedura guidata Entity Data Model.

4. Nella finestra di dialogo **Scegli contenuto Model** selezionare **genera da database**. Scegliere quindi **Avanti**.

5. Fare clic sul pulsante **nuova connessione** .

6. Nella finestra di dialogo **Proprietà connessione** Digitare il nome del server, selezionare il metodo di autenticazione, digitare il nome del database, quindi fare clic su **OK**.

     La finestra di dialogo **scegliere la connessione dati** viene aggiornata con le impostazioni di connessione del database.

7. Verificare che la casella **di controllo Salva le impostazioni di connessione dell'entità in app. config come:** sia selezionata. Scegliere quindi **Avanti**.

8. Nella finestra di dialogo **Scegli oggetti di database** selezionare tutti gli oggetti di database che si intende esporre nel servizio dati.

    > [!NOTE]
    > Gli oggetti inclusi nel modello di dati non vengono esposti automaticamente dal servizio dati. Devono essere esposti in modo esplicito mediante il servizio stesso. Per ulteriori informazioni, vedere [configurazione del servizio dati](configuring-the-data-service-wcf-data-services.md).

9. Fare clic su **fine** per completare la procedura guidata.

     Verrà creato un modello di dati predefinito in base al database specifico. [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] consente di personalizzare il modello di dati. Per ulteriori informazioni, vedere [attività di Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).

## <a name="to-create-the-data-service-by-using-the-new-data-model"></a>Per creare il servizio dati usando il nuovo modello di dati

1. In Visual Studio aprire il file con estensione edmx che rappresenta il modello di dati.

2. In **browser modello**fare clic con il pulsante destro del mouse sul modello, scegliere **Proprietà**, quindi prendere nota del nome del contenitore di entità.

3. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nome del progetto ASP.NET, quindi scegliere **Aggiungi** > **nuovo elemento**.

4. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare il modello **WCF Data Services** nella categoria **Web** .

   ![Modello di elemento del servizio dati WCF in Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Il modello di **servizio dati WCF** è disponibile in visual studio 2015, ma non in visual studio 2017.

5. Specificare un nome per il servizio, quindi fare clic su **OK**.

     In Visual Studio verranno creati i file del markup XML e del codice per il nuovo servizio. Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice.

6. Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo che eredita dalla classe <xref:System.Data.Objects.ObjectContext> e che rappresenta il contenitore di entità del modello di dati annotato nel passaggio 2.

7. Nel codice per il servizio dati consentire ai client autorizzati di accedere ai set di entità esposti dal servizio dati. Per ulteriori informazioni, vedere [creazione del servizio dati](creating-the-data-service.md).

8. Per testare il servizio dati Northwind. svc utilizzando una Web browser, seguire le istruzioni riportate nell'argomento [accesso al servizio da un Web browser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).

## <a name="see-also"></a>Vedere anche

- [Definizione di WCF Data Services](defining-wcf-data-services.md)
- [Provider di servizi dati](data-services-providers-wcf-data-services.md)
- [Procedura: Creazione di un servizio dati tramite il provider di Reflection](create-a-data-service-using-rp-wcf-data-services.md)
- [Procedura: Creazione di un servizio dati tramite un'origine dati LINQ to SQL](create-a-data-service-using-linq-to-sql-wcf.md)
