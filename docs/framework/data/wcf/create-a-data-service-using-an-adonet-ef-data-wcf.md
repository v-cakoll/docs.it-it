---
title: "Procedura: creare un servizio dati tramite un'origine dati ADO.NET Entity Framework (WCF Data Services)"
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
ms.openlocfilehash: 4bccd1e4655786ae24166cdc32619b420c4a54d3
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48780037"
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a>Procedura: creare un servizio dati tramite un'origine dati ADO.NET Entity Framework (WCF Data Services)

WCF Data Services espone i dati di entità come un servizio dati. Questi dati di entità avviene tramite il [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] quando l'origine dati è un database relazionale. In questo argomento viene illustrato come creare un [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-basato sul modello di dati in un'applicazione Web di Visual Studio che si basa su un database esistente e Usa questo modello di dati per creare un nuovo servizio dati.

Il [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] fornisce anche uno strumento da riga di comando che può generare un [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] modello all'esterno di un progetto di Visual Studio. Per altre informazioni, vedere [procedura: usare EdmGen.exe per generare il file di modello e di Mapping](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).

## <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a>Per aggiungere un modello di Entity Framework basato su un database esistente a un'applicazione Web esistente

1. Nel **Project** menu, fare clic su **Add** > **nuovo elemento**.

2. Nel **modelli** riquadro, fare clic sul **Data** categoria e quindi selezionare **ADO.NET Entity Data Model**.

3. Immettere il nome del modello e quindi fare clic su **Add**.

     Verrà visualizzata la prima pagina della Procedura guidata [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].

4. Nel **Scegli contenuto Model** finestra di dialogo **genera da database**. Scegliere quindi **Avanti**.

5. Scegliere il **nuova connessione** pulsante.

6. Nel **proprietà connessione** della finestra di dialogo digitare il nome del server, selezionare il metodo di autenticazione, digitare il nome del database e quindi fare clic su **OK**.

     Il **Seleziona connessione dati** nella finestra di dialogo viene aggiornata con le impostazioni di connessione di database.

7. Verificare che il **Salva impostazioni di connessione entity in App. config come:** casella di controllo è selezionata. Scegliere quindi **Avanti**.

8. Nel **Scegli oggetti di Database** nella finestra di dialogo database selezionare tutti gli oggetti che si intende esporre nel servizio dati.

    > [!NOTE]
    > Gli oggetti inclusi nel modello di dati non vengono esposti automaticamente dal servizio dati. Devono essere esposti in modo esplicito mediante il servizio stesso. Per altre informazioni, vedere [configurazione del servizio dati](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).

9. Fare clic su **fine** per completare la procedura guidata.

     Verrà creato un modello di dati predefinito in base al database specifico. [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] consente di personalizzare il modello di dati. Per altre informazioni, vedere [Tasks](https://msdn.microsoft.com/library/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb) (Attività).

## <a name="to-create-the-data-service-by-using-the-new-data-model"></a>Per creare il servizio dati usando il nuovo modello di dati

1. In Visual Studio aprire il file con estensione edmx che rappresenta il modello di dati.

2. Nel **Visualizzatore modelli**, fare clic sul modello, fare clic su **proprietà**e quindi prendere nota del nome del contenitore di entità.

3. Nella **Esplora soluzioni**, fare doppio clic il nome delle [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] del progetto e quindi fare clic su **Add** > **nuovo elemento**.

4. Nel **Aggiungi nuovo elemento** finestra di dialogo, seleziona la **WCF Data Services** modello nel **Web** categoria.

   ![Modello di elemento di WCF Data Services in Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Il **di WCF Data Services** modello è disponibile in Visual Studio 2015, ma non in Visual Studio 2017.

5. Specificare un nome per il servizio e quindi fare clic su **OK**.

     In Visual Studio verranno creati i file del markup XML e del codice per il nuovo servizio. Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice.

6. Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo che eredita dalla classe <xref:System.Data.Objects.ObjectContext> e che rappresenta il contenitore di entità del modello di dati annotato nel passaggio 2.

7. Nel codice per il servizio dati consentire ai client autorizzati di accedere ai set di entità esposti dal servizio dati. Per altre informazioni, vedere [creazione del servizio dati](../../../../docs/framework/data/wcf/creating-the-data-service.md).

8. Per testare il servizio dati Northwind. svc tramite un Web browser, seguire le istruzioni nell'argomento [accesso al servizio da un Web Browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).

## <a name="see-also"></a>Vedere anche

- [Definizione di WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
- [Provider di servizi dati](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [Procedura: creare un servizio dati tramite il provider di reflection](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)
- [Procedura: creare un servizio dati tramite un'origine dati LINQ to SQL](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)