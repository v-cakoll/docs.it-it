---
title: 'Procedura: sviluppare un servizio WCF in esecuzione in IIS'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f9df38d200be864ab24efdb0d002fe7b75cfc3e4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a><span data-ttu-id="60bb2-102">Procedura: sviluppare un servizio WCF in esecuzione in IIS</span><span class="sxs-lookup"><span data-stu-id="60bb2-102">How to: Develop a WCF Data Service Running on IIS</span></span>
<span data-ttu-id="60bb2-103">In questo argomento viene illustrato come utilizzare [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] per creare un servizio dati basato sul database di esempio Northwind ospitato da un'applicazione Web ASP.NET che è in esecuzione in Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="60bb2-103">This topic shows how to use [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] to create a data service that is based on the Northwind sample database that is hosted by an ASP.NET Web application that is running on Internet Information Services (IIS).</span></span> <span data-ttu-id="60bb2-104">Per un esempio di come creare lo stesso servizio dati Northwind come applicazione Web ASP.NET in esecuzione sul Server di sviluppo ASP.NET, vedere il [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="60bb2-104">For an example of how to create the same Northwind data service as an ASP.NET Web application that runs on the ASP.NET Development Server, see the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60bb2-105">Per creare il servizio dati Northwind, è necessario installare il database di esempio Northwind nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="60bb2-105">To create the Northwind data service, you must have installed the Northwind sample database on the local computer.</span></span> <span data-ttu-id="60bb2-106">Per scaricare questo database di esempio, vedere la pagina di download dei [database di esempio per SQL Server](http://go.microsoft.com/fwlink/?linkid=24758).</span><span class="sxs-lookup"><span data-stu-id="60bb2-106">To download this sample database, see the download page, [Sample Databases for SQL Server](http://go.microsoft.com/fwlink/?linkid=24758).</span></span>  
  
 <span data-ttu-id="60bb2-107">In questo argomento viene illustrato come creare un servizio dati tramite il provider di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="60bb2-107">This topic shows how to create a data service by using the Entity Framework provider.</span></span> <span data-ttu-id="60bb2-108">Sono disponibili altri provider di servizi dati.</span><span class="sxs-lookup"><span data-stu-id="60bb2-108">Other data services providers are available.</span></span> <span data-ttu-id="60bb2-109">Per ulteriori informazioni, vedere [provider di servizi dati](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="60bb2-109">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="60bb2-110">Dopo aver creato il servizio, è necessario fornire in modo esplicito l'accesso alle risorse del servizio dati.</span><span class="sxs-lookup"><span data-stu-id="60bb2-110">After you create the service, you must explicitly provide access to data service resources.</span></span> <span data-ttu-id="60bb2-111">Per ulteriori informazioni, vedere [come: abilita l'accesso al servizio dati](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="60bb2-111">For more information, see [How to: Enable Access to the Data Service](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).</span></span>  
  
### <a name="to-create-the-aspnet-web-application-that-runs-on-iis"></a><span data-ttu-id="60bb2-112">Per creare l'applicazione Web ASP.NET in esecuzione in IIS</span><span class="sxs-lookup"><span data-stu-id="60bb2-112">To create the ASP.NET Web application that runs on IIS</span></span>  
  
1.  <span data-ttu-id="60bb2-113">In Visual Studio, sul **File** dal menu **New**, quindi selezionare **progetto**.</span><span class="sxs-lookup"><span data-stu-id="60bb2-113">In Visual Studio, on the **File** menu, select **New**, and then select **Project**.</span></span>  
  
2.  <span data-ttu-id="60bb2-114">Nel **nuovo progetto** finestra di dialogo, selezionare Visual Basic o Visual c# come linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="60bb2-114">In the **New Project** dialog box, select either Visual Basic or Visual C# as the programming language.</span></span>  
  
3.  <span data-ttu-id="60bb2-115">Nel **modelli** riquadro, selezionare **applicazione Web ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="60bb2-115">In the **Templates** pane, select **ASP.NET Web Application**.</span></span> <span data-ttu-id="60bb2-116">Nota: se si usa Visual Studio Web Developer, sarà necessario creare un nuovo sito Web anziché una nuova applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="60bb2-116">Note: If you use Visual Studio Web Developer, you must create a new Web site instead of a new Web application.</span></span>  
  
4.  <span data-ttu-id="60bb2-117">Tipo `NorthwindService` come il nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="60bb2-117">Type `NorthwindService` as the name of the project.</span></span>  
  
5.  <span data-ttu-id="60bb2-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="60bb2-118">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="60bb2-119">Nel **progetto** dal menu **proprietà NorthwindService**.</span><span class="sxs-lookup"><span data-stu-id="60bb2-119">On the **Project** menu, select **NorthwindService Properties**.</span></span>  
  
7.  <span data-ttu-id="60bb2-120">Selezionare il **Web** scheda e quindi selezionare **Usa Server Web IIS locale**.</span><span class="sxs-lookup"><span data-stu-id="60bb2-120">Select the **Web** tab, and then select **Use Local IIS Web Server**.</span></span>  
  
8.  <span data-ttu-id="60bb2-121">Fare clic su **crea Directory virtuale** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="60bb2-121">Click **Create Virtual Directory** and then click **OK**.</span></span>  
  
9. <span data-ttu-id="60bb2-122">Dal prompt dei comandi aperto con privilegi di amministratore, eseguire uno dei comandi seguenti (a seconda del sistema operativo):</span><span class="sxs-lookup"><span data-stu-id="60bb2-122">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>  
  
    -   <span data-ttu-id="60bb2-123">sistemi a 32 bit:</span><span class="sxs-lookup"><span data-stu-id="60bb2-123">32-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
    -   <span data-ttu-id="60bb2-124">sistemi a 64 bit:</span><span class="sxs-lookup"><span data-stu-id="60bb2-124">64-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
     <span data-ttu-id="60bb2-125">In questo modo viene effettuata la registrazione di Windows Communication Foundation (WCF) nel computer.</span><span class="sxs-lookup"><span data-stu-id="60bb2-125">This makes sure that Windows Communication Foundation (WCF) is registered on the computer.</span></span>  
  
10. <span data-ttu-id="60bb2-126">Dal prompt dei comandi aperto con privilegi di amministratore, eseguire uno dei comandi seguenti (a seconda del sistema operativo):</span><span class="sxs-lookup"><span data-stu-id="60bb2-126">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>  
  
    -   <span data-ttu-id="60bb2-127">sistemi a 32 bit:</span><span class="sxs-lookup"><span data-stu-id="60bb2-127">32-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
    -   <span data-ttu-id="60bb2-128">sistemi a 64 bit:</span><span class="sxs-lookup"><span data-stu-id="60bb2-128">64-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
     <span data-ttu-id="60bb2-129">In questo modo viene verificato che l'esecuzione di IIS dopo che WCF è stato installato nel computer sia corretta.</span><span class="sxs-lookup"><span data-stu-id="60bb2-129">This makes sure that IIS runs correctly after WCF has been installed on the computer.</span></span> <span data-ttu-id="60bb2-130">Può essere necessario inoltre riavviare IIS.</span><span class="sxs-lookup"><span data-stu-id="60bb2-130">You might have to also restart IIS.</span></span>  
  
11. <span data-ttu-id="60bb2-131">Quando l'applicazione ASP.NET è in esecuzione in IIS7, è necessario eseguire inoltre i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="60bb2-131">When the ASP.NET application runs on IIS7, you must also perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="60bb2-132">Aprire Gestione IIS e passare all'applicazione PhotoService in **sito Web predefinito**.</span><span class="sxs-lookup"><span data-stu-id="60bb2-132">Open IIS Manager and navigate to the PhotoService application under **Default Web Site**.</span></span>  
  
    2.  <span data-ttu-id="60bb2-133">In **visualizzazione funzionalità**, fare doppio clic su **autenticazione**.</span><span class="sxs-lookup"><span data-stu-id="60bb2-133">In **Features View**, double-click **Authentication**.</span></span>  
  
    3.  <span data-ttu-id="60bb2-134">Nel **autenticazione** selezionare **l'autenticazione anonima**.</span><span class="sxs-lookup"><span data-stu-id="60bb2-134">On the **Authentication** page, select **Anonymous Authentication**.</span></span>  
  
    4.  <span data-ttu-id="60bb2-135">Nel **azioni** riquadro, fare clic su **modifica** impostare la sicurezza dell'entità in cui gli utenti anonimi si connetteranno al sito.</span><span class="sxs-lookup"><span data-stu-id="60bb2-135">In the **Actions** pane, click **Edit** to set the security principal under which anonymous users will connect to the site.</span></span>  
  
    5.  <span data-ttu-id="60bb2-136">Nel **Modifica credenziali di autenticazione anonima** nella finestra di dialogo **identità pool di applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="60bb2-136">In the **Edit Anonymous Authentication Credentials** dialog box, select **Application pool identity**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="60bb2-137">Quando si usa l'account Servizio di rete, agli utenti anonimi viene concesso l'accesso completo alla rete interna associato a tale account.</span><span class="sxs-lookup"><span data-stu-id="60bb2-137">When you use the Network Service account, you grant anonymous users all the internal network access associated with that account.</span></span>  
  
12. <span data-ttu-id="60bb2-138">Tramite SQL Server Management Studio, l'utilità sqlcmd.exe o l'Editor Transact-SQL eseguire il comando Transact-SQL seguente sull'istanza di SQL Server cui è collegato il database Northwind:</span><span class="sxs-lookup"><span data-stu-id="60bb2-138">By using SQL Server Management Studio, the sqlcmd.exe utility, or the Transact-SQL Editor in Visual Studio, execute the following Transact-SQL command against the instance of SQL Server that has the Northwind database attached:</span></span>  
  
    ```sql  
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;  
    GO   
    ```  
  
     <span data-ttu-id="60bb2-139">In questo modo nell'istanza di SQL Server viene creato un account di accesso per l'account di Windows usato per eseguire IIS.</span><span class="sxs-lookup"><span data-stu-id="60bb2-139">This creates a login in the SQL Server instance for the Windows account used to run IIS.</span></span> <span data-ttu-id="60bb2-140">Ciò rende possibile la connessione di IIS all'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="60bb2-140">This enables IIS to connect to the SQL Server instance.</span></span>  
  
13. <span data-ttu-id="60bb2-141">Con il database Northwind collegato eseguire i comandi Transact-SQL seguenti:</span><span class="sxs-lookup"><span data-stu-id="60bb2-141">With the Northwind database attached, execute the following Transact-SQL commands:</span></span>  
  
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
  
     <span data-ttu-id="60bb2-142">Vengono concessi i diritti al nuovo account di accesso per consentire a IIS la lettura e la scrittura dei dati nel database Northwind.</span><span class="sxs-lookup"><span data-stu-id="60bb2-142">This grants rights to the new login, which enables IIS to read data from and write data to the Northwind database.</span></span>  
  
### <a name="to-define-the-data-model"></a><span data-ttu-id="60bb2-143">Per definire il modello di dati</span><span class="sxs-lookup"><span data-stu-id="60bb2-143">To define the data model</span></span>  
  
1.  <span data-ttu-id="60bb2-144">In **Esplora soluzioni**destro del mouse sul nome del progetto ASP.NET e quindi fare clic su **Aggiungi nuovo elemento.**</span><span class="sxs-lookup"><span data-stu-id="60bb2-144">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add New Item.**</span></span>  
  
2.  <span data-ttu-id="60bb2-145">Nel **Aggiungi nuovo elemento** nella finestra di dialogo **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="60bb2-145">In the **Add New Item** dialog box, select **ADO.NET Entity Data Model**.</span></span>  
  
3.  <span data-ttu-id="60bb2-146">Per il nome del modello di dati, digitare `Northwind.edmx`.</span><span class="sxs-lookup"><span data-stu-id="60bb2-146">For the name of the data model, type `Northwind.edmx`.</span></span>  
  
4.  <span data-ttu-id="60bb2-147">Nella procedura guidata Entity Data Model, selezionare **genera da Database**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="60bb2-147">In the Entity Data Model Wizard, select **Generate from Database**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="60bb2-148">Connettere il modello di dati per il database eseguendo una delle operazioni seguenti e quindi fare clic su **Avanti**:</span><span class="sxs-lookup"><span data-stu-id="60bb2-148">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>  
  
    -   <span data-ttu-id="60bb2-149">Se non si dispone di una connessione al database già configurata, fare clic su **nuova connessione** e creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="60bb2-149">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="60bb2-150">Per ulteriori informazioni, vedere [procedura: creare connessioni ai database di SQL Server](http://go.microsoft.com/fwlink/?LinkId=123631).</span><span class="sxs-lookup"><span data-stu-id="60bb2-150">For more information, see [How to: Create Connections to SQL Server Databases](http://go.microsoft.com/fwlink/?LinkId=123631).</span></span> <span data-ttu-id="60bb2-151">A questa istanza di SQL Server deve essere collegato il database Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="60bb2-151">This SQL Server instance must have the Northwind sample database attached.</span></span>  
  
         <span data-ttu-id="60bb2-152">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="60bb2-152">\- or -</span></span>  
  
    -   <span data-ttu-id="60bb2-153">Se si dispone di una connessione al database già configurata per connettersi al database Northwind, selezionarla dall'elenco delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="60bb2-153">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>  
  
6.  <span data-ttu-id="60bb2-154">Nella pagina finale della procedura guidata, selezionare le caselle di controllo relative a tutte le tabelle nel database e deselezionare le caselle di controllo relative a visualizzazioni e stored procedure.</span><span class="sxs-lookup"><span data-stu-id="60bb2-154">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>  
  
7.  <span data-ttu-id="60bb2-155">Fare clic su **fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="60bb2-155">Click **Finish** to close the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="60bb2-156">Questo modello di dati generato espone le proprietà della chiave esterna sui tipi di entità.</span><span class="sxs-lookup"><span data-stu-id="60bb2-156">This generated data model exposes foreign key properties on entity types.</span></span> <span data-ttu-id="60bb2-157">I modelli di dati creati usando Visual Studio 2008 non includono tali proprietà della chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="60bb2-157">Data models created using Visual Studio 2008 do not include these foreign key properties.</span></span> <span data-ttu-id="60bb2-158">Per questo motivo è necessario aggiornare le classi del servizio dati client di qualsiasi applicazione client creata per accedere al servizio dati Northwind creato usando Visual Studio 2008 prima di tentare di accedere alla versione corrente del servizio dati Northwind.</span><span class="sxs-lookup"><span data-stu-id="60bb2-158">Because of this, you must update the client data service classes of any client applications that were created to access the Northwind data service that was created using Visual Studio 2008 before attempting to access this version of the Northwind data service.</span></span>  
  
### <a name="to-create-the-data-service"></a><span data-ttu-id="60bb2-159">Per creare il servizio dati</span><span class="sxs-lookup"><span data-stu-id="60bb2-159">To create the data service</span></span>  
  
1.  <span data-ttu-id="60bb2-160">In **Esplora**, il nome del progetto ASP.NET destro e quindi fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="60bb2-160">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="60bb2-161">Nel **Aggiungi nuovo elemento** nella finestra di dialogo **ADO.NET Data Services**.</span><span class="sxs-lookup"><span data-stu-id="60bb2-161">In the **Add New Item** dialog box, select **ADO.NET Data Service**.</span></span>  
  
3.  <span data-ttu-id="60bb2-162">Per il nome del servizio, digitare `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="60bb2-162">For the name of the service, type `Northwind`.</span></span>  
  
     <span data-ttu-id="60bb2-163">In Visual Studio verranno creati i file del markup XML e del codice per il nuovo servizio.</span><span class="sxs-lookup"><span data-stu-id="60bb2-163">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="60bb2-164">Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="60bb2-164">By default, the code-editor window opens.</span></span> <span data-ttu-id="60bb2-165">In **Esplora**, il servizio risulterà denominato Northwind con estensione. svc.cs o. svc.</span><span class="sxs-lookup"><span data-stu-id="60bb2-165">In **Solution Explorer**, the service will have the name, Northwind, with the extension .svc.cs or .svc.vb.</span></span>  
  
4.  <span data-ttu-id="60bb2-166">Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo del contenitore di entità del modello di dati, che in questo caso corrisponde a `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="60bb2-166">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="60bb2-167">La definizione di classe dovrà essere analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="60bb2-167">The class definition should look this the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
## <a name="see-also"></a><span data-ttu-id="60bb2-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60bb2-168">See Also</span></span>  
 [<span data-ttu-id="60bb2-169">Esposizione dei dati come un servizio</span><span class="sxs-lookup"><span data-stu-id="60bb2-169">Exposing Your Data as a Service</span></span>](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
