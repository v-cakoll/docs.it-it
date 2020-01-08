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
ms.openlocfilehash: 5c75425783d3468ac42ef7cb32cd9c93e812192a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338342"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a><span data-ttu-id="860c4-102">Procedura: sviluppare un servizio dati WCF in esecuzione in IIS</span><span class="sxs-lookup"><span data-stu-id="860c4-102">How to: Develop a WCF data service running on IIS</span></span>

<span data-ttu-id="860c4-103">In questo argomento viene illustrato come utilizzare WCF Data Services per creare un servizio dati basato sul database di esempio Northwind ospitato da un'applicazione Web ASP.NET in esecuzione in Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="860c4-103">This topic shows how to use WCF Data Services to create a data service that is based on the Northwind sample database that is hosted by an ASP.NET Web application that is running on Internet Information Services (IIS).</span></span> <span data-ttu-id="860c4-104">Per un esempio di come creare lo stesso servizio dati Northwind di un'applicazione Web ASP.NET che viene eseguita nel Server di sviluppo ASP.NET, vedere la [Guida introduttiva di WCF Data Services](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="860c4-104">For an example of how to create the same Northwind data service as an ASP.NET Web application that runs on the ASP.NET Development Server, see the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>

> [!NOTE]
> <span data-ttu-id="860c4-105">Per creare il servizio dati Northwind, è necessario installare il database di esempio Northwind nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="860c4-105">To create the Northwind data service, you must have installed the Northwind sample database on the local computer.</span></span> <span data-ttu-id="860c4-106">Per scaricare questo database di esempio, vedere la pagina di download dei [database di esempio per SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span><span class="sxs-lookup"><span data-stu-id="860c4-106">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

<span data-ttu-id="860c4-107">In questo argomento viene illustrato come creare un servizio dati tramite il provider di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="860c4-107">This topic shows how to create a data service by using the Entity Framework provider.</span></span> <span data-ttu-id="860c4-108">Sono disponibili altri provider di servizi dati.</span><span class="sxs-lookup"><span data-stu-id="860c4-108">Other data services providers are available.</span></span> <span data-ttu-id="860c4-109">Per ulteriori informazioni, vedere [provider di servizi dati](data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="860c4-109">For more information, see [Data Services Providers](data-services-providers-wcf-data-services.md).</span></span>

<span data-ttu-id="860c4-110">Dopo aver creato il servizio, è necessario fornire in modo esplicito l'accesso alle risorse del servizio dati.</span><span class="sxs-lookup"><span data-stu-id="860c4-110">After you create the service, you must explicitly provide access to data service resources.</span></span> <span data-ttu-id="860c4-111">Per altre informazioni, vedere [procedura: abilitare l'accesso al servizio dati](how-to-enable-access-to-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="860c4-111">For more information, see [How to: Enable Access to the Data Service](how-to-enable-access-to-the-data-service-wcf-data-services.md).</span></span>

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a><span data-ttu-id="860c4-112">Creare l'applicazione Web ASP.NET che viene eseguita in IIS</span><span class="sxs-lookup"><span data-stu-id="860c4-112">Create the ASP.NET web application that runs on IIS</span></span>

1. <span data-ttu-id="860c4-113">Nel menu **File** in Visual Studio selezionare **Nuovo** > **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="860c4-113">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

2. <span data-ttu-id="860c4-114">Nella finestra di dialogo **nuovo progetto** selezionare la categoria > **installato** [**Visual C#**  o **Visual Basic**] > **Web** .</span><span class="sxs-lookup"><span data-stu-id="860c4-114">In the **New Project** dialog box, select the **Installed** > [**Visual C#** or **Visual Basic**] > **Web** category.</span></span>

3. <span data-ttu-id="860c4-115">Selezionare il modello **Applicazione Web ASP.NET** .</span><span class="sxs-lookup"><span data-stu-id="860c4-115">Select the **ASP.NET Web Application** template.</span></span>

4. <span data-ttu-id="860c4-116">Immettere `NorthwindService` come nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="860c4-116">Enter `NorthwindService` as the name of the project.</span></span>

5. <span data-ttu-id="860c4-117">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="860c4-117">Click **OK**.</span></span>

6. <span data-ttu-id="860c4-118">Scegliere **Proprietà NorthwindService**dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="860c4-118">On the **Project** menu, select **NorthwindService Properties**.</span></span>

7. <span data-ttu-id="860c4-119">Selezionare la scheda **Web** , quindi selezionare **Usa server Web IIS locale**.</span><span class="sxs-lookup"><span data-stu-id="860c4-119">Select the **Web** tab, and then select **Use Local IIS Web Server**.</span></span>

8. <span data-ttu-id="860c4-120">Fare clic su **Crea directory virtuale** e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="860c4-120">Click **Create Virtual Directory** and then click **OK**.</span></span>

9. <span data-ttu-id="860c4-121">Dal prompt dei comandi aperto con privilegi di amministratore, eseguire uno dei comandi seguenti (a seconda del sistema operativo):</span><span class="sxs-lookup"><span data-stu-id="860c4-121">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    - <span data-ttu-id="860c4-122">Sistemi a 32 bit:</span><span class="sxs-lookup"><span data-stu-id="860c4-122">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    - <span data-ttu-id="860c4-123">sistemi a 64 bit:</span><span class="sxs-lookup"><span data-stu-id="860c4-123">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     <span data-ttu-id="860c4-124">In questo modo viene effettuata la registrazione di Windows Communication Foundation (WCF) nel computer.</span><span class="sxs-lookup"><span data-stu-id="860c4-124">This makes sure that Windows Communication Foundation (WCF) is registered on the computer.</span></span>

10. <span data-ttu-id="860c4-125">Dal prompt dei comandi aperto con privilegi di amministratore, eseguire uno dei comandi seguenti (a seconda del sistema operativo):</span><span class="sxs-lookup"><span data-stu-id="860c4-125">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    - <span data-ttu-id="860c4-126">Sistemi a 32 bit:</span><span class="sxs-lookup"><span data-stu-id="860c4-126">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    - <span data-ttu-id="860c4-127">sistemi a 64 bit:</span><span class="sxs-lookup"><span data-stu-id="860c4-127">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     <span data-ttu-id="860c4-128">In questo modo viene verificato che l'esecuzione di IIS dopo che WCF è stato installato nel computer sia corretta.</span><span class="sxs-lookup"><span data-stu-id="860c4-128">This makes sure that IIS runs correctly after WCF has been installed on the computer.</span></span> <span data-ttu-id="860c4-129">Può essere necessario inoltre riavviare IIS.</span><span class="sxs-lookup"><span data-stu-id="860c4-129">You might have to also restart IIS.</span></span>

11. <span data-ttu-id="860c4-130">Quando l'applicazione ASP.NET è in esecuzione in IIS7, è necessario eseguire inoltre i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="860c4-130">When the ASP.NET application runs on IIS7, you must also perform the following steps:</span></span>

    1. <span data-ttu-id="860c4-131">Aprire Gestione IIS e passare all'applicazione Fotoservizio in **sito Web predefinito**.</span><span class="sxs-lookup"><span data-stu-id="860c4-131">Open IIS Manager and navigate to the PhotoService application under **Default Web Site**.</span></span>

    2. <span data-ttu-id="860c4-132">In **Visualizzazione funzionalità** fare doppio clic su **Autenticazione**.</span><span class="sxs-lookup"><span data-stu-id="860c4-132">In **Features View**, double-click **Authentication**.</span></span>

    3. <span data-ttu-id="860c4-133">Nella pagina **Autenticazione** selezionare **Autenticazione anonima**.</span><span class="sxs-lookup"><span data-stu-id="860c4-133">On the **Authentication** page, select **Anonymous Authentication**.</span></span>

    4. <span data-ttu-id="860c4-134">Nel riquadro **azioni** fare clic su **modifica** per impostare l'entità di sicurezza con cui gli utenti anonimi si connetteranno al sito.</span><span class="sxs-lookup"><span data-stu-id="860c4-134">In the **Actions** pane, click **Edit** to set the security principal under which anonymous users will connect to the site.</span></span>

    5. <span data-ttu-id="860c4-135">Nella finestra di dialogo **Modifica credenziali di autenticazione anonima** selezionare **identità del pool di applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="860c4-135">In the **Edit Anonymous Authentication Credentials** dialog box, select **Application pool identity**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="860c4-136">Quando si usa l'account Servizio di rete, agli utenti anonimi viene concesso l'accesso completo alla rete interna associato a tale account.</span><span class="sxs-lookup"><span data-stu-id="860c4-136">When you use the Network Service account, you grant anonymous users all the internal network access associated with that account.</span></span>

12. <span data-ttu-id="860c4-137">Tramite SQL Server Management Studio, l'utilità sqlcmd.exe o l'Editor Transact-SQL eseguire il comando Transact-SQL seguente sull'istanza di SQL Server cui è collegato il database Northwind:</span><span class="sxs-lookup"><span data-stu-id="860c4-137">By using SQL Server Management Studio, the sqlcmd.exe utility, or the Transact-SQL Editor in Visual Studio, execute the following Transact-SQL command against the instance of SQL Server that has the Northwind database attached:</span></span>

    ```sql
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;
    GO
    ```

    <span data-ttu-id="860c4-138">In questo modo nell'istanza di SQL Server viene creato un account di accesso per l'account di Windows usato per eseguire IIS.</span><span class="sxs-lookup"><span data-stu-id="860c4-138">This creates a login in the SQL Server instance for the Windows account used to run IIS.</span></span> <span data-ttu-id="860c4-139">Ciò rende possibile la connessione di IIS all'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="860c4-139">This enables IIS to connect to the SQL Server instance.</span></span>

13. <span data-ttu-id="860c4-140">Con il database Northwind collegato eseguire i comandi Transact-SQL seguenti:</span><span class="sxs-lookup"><span data-stu-id="860c4-140">With the Northwind database attached, execute the following Transact-SQL commands:</span></span>

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

    <span data-ttu-id="860c4-141">Vengono concessi i diritti al nuovo account di accesso per consentire a IIS la lettura e la scrittura dei dati nel database Northwind.</span><span class="sxs-lookup"><span data-stu-id="860c4-141">This grants rights to the new login, which enables IIS to read data from and write data to the Northwind database.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="860c4-142">Definizione del modello di dati</span><span class="sxs-lookup"><span data-stu-id="860c4-142">Define the data model</span></span>

1. <span data-ttu-id="860c4-143">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nome del progetto ASP.NET, quindi scegliere **Aggiungi** > **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="860c4-143">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="860c4-144">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="860c4-144">In the **Add New Item** dialog box, select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="860c4-145">Per il nome del modello di dati, digitare `Northwind.edmx`.</span><span class="sxs-lookup"><span data-stu-id="860c4-145">For the name of the data model, type `Northwind.edmx`.</span></span>

4. <span data-ttu-id="860c4-146">Nella procedura guidata Entity Data Model selezionare **genera da database**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="860c4-146">In the Entity Data Model Wizard, select **Generate from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="860c4-147">Connettere il modello di dati al database effettuando una delle operazioni seguenti, quindi fare clic su **Avanti**:</span><span class="sxs-lookup"><span data-stu-id="860c4-147">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    - <span data-ttu-id="860c4-148">Se non è già stata configurata una connessione di database, fare clic su **nuova connessione** e creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="860c4-148">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="860c4-149">Per altre informazioni, vedere [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="860c4-149">For more information, see [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="860c4-150">A questa istanza di SQL Server deve essere collegato il database Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="860c4-150">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="860c4-151">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="860c4-151">\- or -</span></span>

    - <span data-ttu-id="860c4-152">Se si dispone di una connessione al database già configurata per connettersi al database Northwind, selezionarla dall'elenco delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="860c4-152">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="860c4-153">Nella pagina finale della procedura guidata, selezionare le caselle di controllo relative a tutte le tabelle nel database e deselezionare le caselle di controllo relative a visualizzazioni e stored procedure.</span><span class="sxs-lookup"><span data-stu-id="860c4-153">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="860c4-154">Fare clic su **Fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="860c4-154">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-data-service"></a><span data-ttu-id="860c4-155">Creazione del servizio dati</span><span class="sxs-lookup"><span data-stu-id="860c4-155">Create the data service</span></span>

1. <span data-ttu-id="860c4-156">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nome del progetto ASP.NET, quindi scegliere **Aggiungi** > **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="860c4-156">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="860c4-157">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **WCF Data Service**.</span><span class="sxs-lookup"><span data-stu-id="860c4-157">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>

   ![Modello di elemento del servizio dati WCF in Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="860c4-159">Il modello di **servizio dati WCF** è disponibile in visual studio 2015, ma non in visual studio 2017 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="860c4-159">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

3. <span data-ttu-id="860c4-160">Per il nome del servizio, immettere `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="860c4-160">For the name of the service, enter `Northwind`.</span></span>

     <span data-ttu-id="860c4-161">In Visual Studio verranno creati i file del markup XML e del codice per il nuovo servizio.</span><span class="sxs-lookup"><span data-stu-id="860c4-161">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="860c4-162">Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="860c4-162">By default, the code-editor window opens.</span></span> <span data-ttu-id="860c4-163">In **Esplora soluzioni**, il servizio ha il nome Northwind e l'estensione svc.cs o SVC. vb.</span><span class="sxs-lookup"><span data-stu-id="860c4-163">In **Solution Explorer**, the service has the name, Northwind, and the extension .svc.cs or .svc.vb.</span></span>

4. <span data-ttu-id="860c4-164">Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo del contenitore di entità del modello di dati, che in questo caso corrisponde a `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="860c4-164">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="860c4-165">La definizione di classe dovrà essere analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="860c4-165">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a><span data-ttu-id="860c4-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="860c4-166">See also</span></span>

- [<span data-ttu-id="860c4-167">Esposizione dei dati come un servizio</span><span class="sxs-lookup"><span data-stu-id="860c4-167">Exposing Your Data as a Service</span></span>](exposing-your-data-as-a-service-wcf-data-services.md)
