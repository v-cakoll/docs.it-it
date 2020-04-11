---
title: 'Procedura: sviluppare un servizio WCF in esecuzione in IIS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
ms.openlocfilehash: 8a1a0c2c55267940463e2c9ab82bb52345269260
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121606"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a>Procedura: sviluppare un servizio dati WCF in esecuzione in IISHow to: Develop a WCF data service running on IIS

In questo articolo viene illustrato come utilizzare WCF Data ServicesWCF Data Services per creare un servizio dati basato sul database di esempio Northwind ospitato da un'applicazione Web ASP.NET in esecuzione su Internet Information Services (IIS). Per un esempio di creazione dello stesso servizio dati Northwind di un'app Web ASP.NET eseguita nel server di sviluppo ASP.NET, vedere la [guida introduttiva](quickstart-wcf-data-services.md)di WCF Data Services .

> [!NOTE]
> Per creare il servizio dati Northwind, installare innanzitutto il database di esempio Northwind nel computer locale. Per installare il database, eseguire lo script Transact-SQL da [Northwind e pubs database di esempio per Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).

In questo articolo viene illustrato come creare un servizio dati utilizzando il provider Entity Framework. Sono disponibili altri provider di servizi dati. Per ulteriori informazioni, vedere [Provider di servizi dati](data-services-providers-wcf-data-services.md).

Dopo aver creato il servizio, è necessario fornire in modo esplicito l'accesso alle risorse del servizio dati. Per ulteriori informazioni, vedere [Procedura: abilitare l'accesso al servizio dati](how-to-enable-access-to-the-data-service-wcf-data-services.md).

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a>Creare l'applicazione Web ASP.NET in esecuzione in IIS

1. Nel menu **File** in Visual Studio selezionare **Nuovo** > **Progetto**.

2. Nella finestra di dialogo **Nuovo progetto** , selezionare la categoria di > **Web** **> installata** [**Visual Cè** o **Visual Basic**] > .

3. Selezionare il modello **Applicazione Web ASP.NET** .

4. Immettere `NorthwindService` il nome del progetto.

5. Fare clic su **OK**.

6. Scegliere **Proprietà NorthwindService**dal menu **Progetto** .

7. Selezionare la scheda **Web** e quindi **selezionare Usa server Web IIS locale**.

8. Fare clic su **Crea directory virtuale** e quindi su **OK**.

9. Dal prompt dei comandi aperto con privilegi di amministratore, eseguire uno dei comandi seguenti (a seconda del sistema operativo):

    - sistemi a 32 bit:

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    - sistemi a 64 bit:

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     In questo modo viene effettuata la registrazione di Windows Communication Foundation (WCF) nel computer.

10. Dal prompt dei comandi aperto con privilegi di amministratore, eseguire uno dei comandi seguenti (a seconda del sistema operativo):

    - sistemi a 32 bit:

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    - sistemi a 64 bit:

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     In questo modo viene verificato che l'esecuzione di IIS dopo che WCF è stato installato nel computer sia corretta. Può essere necessario inoltre riavviare IIS.

11. Quando l'applicazione ASP.NET è in esecuzione in IIS7, è necessario eseguire inoltre i passaggi seguenti:

    1. Aprire Gestione IIS e passare all'applicazione PhotoService in **Sito Web predefinito**.

    2. In **Visualizzazione funzionalità** fare doppio clic su **Autenticazione**.

    3. Nella pagina **Autenticazione** selezionare **Autenticazione anonima**.

    4. Nel riquadro **Azioni** fare clic su **Modifica** per impostare l'entità di sicurezza con cui gli utenti anonimi si connetteranno al sito.

    5. Nella finestra di dialogo **Modifica credenziali di autenticazione anonima** selezionare **Identità pool**di applicazioni .

    > [!IMPORTANT]
    > Quando si usa l'account Servizio di rete, agli utenti anonimi viene concesso l'accesso completo alla rete interna associato a tale account.

12. Tramite SQL Server Management Studio, l'utilità sqlcmd.exe o l'Editor Transact-SQL eseguire il comando Transact-SQL seguente sull'istanza di SQL Server cui è collegato il database Northwind:

    ```sql
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;
    GO
    ```

    In questo modo nell'istanza di SQL Server viene creato un account di accesso per l'account di Windows usato per eseguire IIS. Ciò rende possibile la connessione di IIS all'istanza di SQL Server.

13. Con il database Northwind collegato eseguire i comandi Transact-SQL seguenti:

    ```sql
    USE Northwind
    GO
    CREATE USER [NT AUTHORITY\NETWORK SERVICE]
    FOR LOGIN [NT AUTHORITY\NETWORK SERVICE] WITH DEFAULT_SCHEMA=[dbo];
    GO
    ALTER LOGIN [NT AUTHORITY\NETWORK SERVICE]
    WITH DEFAULT_DATABASE=[Northwind];
    GO
    EXEC sp_addrolemember 'db_datareader', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    EXEC sp_addrolemember 'db_datawriter', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    ```

    Vengono concessi i diritti al nuovo account di accesso per consentire a IIS la lettura e la scrittura dei dati nel database Northwind.

## <a name="define-the-data-model"></a>Definizione del modello di dati

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nome del progetto ASP.NET , quindi **scegliere Aggiungi** > **nuovo elemento**.

2. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare ADO.NET Entity Data **Model**.

3. Per il nome del modello `Northwind.edmx`di dati, digitare .

4. Nella procedura guidata Entity Data Model selezionare **Genera da database**e quindi fare clic su **Avanti**.

5. Connettere il modello di dati al database eseguendo una delle operazioni seguenti e quindi fare clic su **Avanti:**

    - Se non si dispone di una connessione al database già configurata, fare clic su **Nuova connessione** e creare una nuova connessione. Per altre informazioni, vedere [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)). A questa istanza di SQL Server deve essere collegato il database Northwind di esempio.

         \- - oppure -

    - Se si dispone di una connessione al database già configurata per connettersi al database Northwind, selezionarla dall'elenco delle connessioni.

6. Nella pagina finale della procedura guidata, selezionare le caselle di controllo relative a tutte le tabelle nel database e deselezionare le caselle di controllo relative a visualizzazioni e stored procedure.

7. Fare clic su **Fine** per chiudere la procedura guidata.

## <a name="create-the-data-service"></a>Creazione del servizio dati

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nome del progetto ASP.NET, quindi **scegliere Aggiungi** > **nuovo elemento**.

2. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare Servizio dati **WCF**.

   ![Modello di elemento servizio dati WCF in Visual Studio 2015WCF Data Service item template in Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Il modello **WCF Data Service** è disponibile in Visual Studio 2015, ma non in Visual Studio 2017 o versione successiva.

3. Per il nome del `Northwind`servizio, immettere .

     In Visual Studio verranno creati i file del markup XML e del codice per il nuovo servizio. Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice. In **Esplora soluzioni**il servizio contiene il nome Northwind e l'estensione svc.cs o svc.vb.

4. Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo del contenitore di entità del modello di dati, che in questo caso corrisponde a `NorthwindEntities`. La definizione di classe dovrà essere analoga alla seguente:

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a>Vedere anche

- [Esposizione di dati come servizio](exposing-your-data-as-a-service-wcf-data-services.md)
