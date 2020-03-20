---
title: Provider di appartenenza e di ruoli
ms.date: 03/30/2017
ms.assetid: 0d11a31c-e75f-4fcf-9cf4-b7f26e056bcd
ms.openlocfilehash: 117be783c2d4a72ff9d1c4509566274b1043a43d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144461"
---
# <a name="membership-and-role-provider"></a><span data-ttu-id="d5b73-102">Provider di appartenenza e di ruoli</span><span class="sxs-lookup"><span data-stu-id="d5b73-102">Membership and Role Provider</span></span>
<span data-ttu-id="d5b73-103">Nell'esempio di provider di appartenenze e ruoli viene illustrato come un servizio può utilizzare i provider di appartenenze e ruoli ASP.NET per autenticare e autorizzare i client.</span><span class="sxs-lookup"><span data-stu-id="d5b73-103">The Membership and Role Provider sample demonstrates how a service can use the ASP.NET membership and role providers to authenticate and authorize clients.</span></span>  
  
 <span data-ttu-id="d5b73-104">In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="d5b73-104">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d5b73-105">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d5b73-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="d5b73-106">In questo esempio viene illustrato come eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="d5b73-106">The sample demonstrates how:</span></span>  
  
- <span data-ttu-id="d5b73-107">Un client può eseguire l'autenticazione utilizzando una combinazione nome utente-password.</span><span class="sxs-lookup"><span data-stu-id="d5b73-107">A client can authenticate by using the username-password combination.</span></span>  
  
- <span data-ttu-id="d5b73-108">Il server può convalidare le credenziali del client rispetto al provider di appartenenze ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d5b73-108">The server can validate the client credentials against the ASP.NET membership provider.</span></span>  
  
- <span data-ttu-id="d5b73-109">Il server può essere autenticato tramite il certificato X.509 del server.</span><span class="sxs-lookup"><span data-stu-id="d5b73-109">The server can be authenticated by using the server's X.509 certificate.</span></span>  
  
- <span data-ttu-id="d5b73-110">Il server può eseguire il mapping del client autenticato a un ruolo utilizzando il provider di ruoli ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d5b73-110">The server can map the authenticated client to a role by using the ASP.NET role provider.</span></span>  
  
- <span data-ttu-id="d5b73-111">Il server può utilizzare `PrincipalPermissionAttribute` per controllare l'accesso a determinati metodi esposti dal servizio.</span><span class="sxs-lookup"><span data-stu-id="d5b73-111">The server can use the `PrincipalPermissionAttribute` to control access to certain methods that are exposed by the service.</span></span>  
  
 <span data-ttu-id="d5b73-112">I provider di appartenenza e di ruoli sono configurati per utilizzare un archivio supportato da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d5b73-112">The membership and role providers are configured to use a store backed by SQL Server.</span></span> <span data-ttu-id="d5b73-113">Una stringa di connessione e varie opzioni sono specificate nel file di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="d5b73-113">A connection string and various options are specified in the service configuration file.</span></span> <span data-ttu-id="d5b73-114">Al provider di appartenenza viene assegnato il nome `SqlMembershipProvider` mentre al provider di ruoli viene assegnato il nome `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="d5b73-114">The membership provider is given the name `SqlMembershipProvider` while the role provider is given the name `SqlRoleProvider`.</span></span>  
  
```xml  
<!-- Set the connection string for SQL Server -->  
<connectionStrings>  
  <add name="SqlConn"
       connectionString="Data Source=localhost;Integrated Security=SSPI;Initial Catalog=aspnetdb;" />  
</connectionStrings>  
  
<system.web>  
  <!-- Configure the Sql Membership Provider -->  
  <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">  
    <providers>  
      <clear />  
      <add
        name="SqlMembershipProvider"
        type="System.Web.Security.SqlMembershipProvider"
        connectionStringName="SqlConn"  
        applicationName="MembershipAndRoleProviderSample"  
        enablePasswordRetrieval="false"  
        enablePasswordReset="false"  
        requiresQuestionAndAnswer="false"  
        requiresUniqueEmail="true"  
        passwordFormat="Hashed" />  
    </providers>  
  </membership>  
  
  <!-- Configure the Sql Role Provider -->  
  <roleManager enabled ="true"
               defaultProvider ="SqlRoleProvider" >  
    <providers>  
      <add name ="SqlRoleProvider"
           type="System.Web.Security.SqlRoleProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipAndRoleProviderSample"/>  
    </providers>  
  </roleManager>  
</system.web>  
```  
  
 <span data-ttu-id="d5b73-115">Il servizio espone un solo endpoint per la comunicazione con il servizio, che viene definito mediante il file di configurazione Web.config.</span><span class="sxs-lookup"><span data-stu-id="d5b73-115">The service exposes a single endpoint for communicating with the service, which is defined by using the Web.config configuration file.</span></span> <span data-ttu-id="d5b73-116">L'endpoint è costituito da un indirizzo, un'associazione e un contratto.</span><span class="sxs-lookup"><span data-stu-id="d5b73-116">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="d5b73-117">L'associazione viene configurata con una classe standard `wsHttpBinding`, per la quale è impostata l'autenticazione Windows come predefinita.</span><span class="sxs-lookup"><span data-stu-id="d5b73-117">The binding is configured with a standard `wsHttpBinding`, which defaults to using Windows authentication.</span></span> <span data-ttu-id="d5b73-118">In questo esempio viene impostata la classe `wsHttpBinding` standard per utilizzare l'autenticazione del nome utente.</span><span class="sxs-lookup"><span data-stu-id="d5b73-118">This sample sets the standard `wsHttpBinding` to use username authentication.</span></span> <span data-ttu-id="d5b73-119">Il comportamento specifica che il certificato server deve essere utilizzato per autenticare il servizio.</span><span class="sxs-lookup"><span data-stu-id="d5b73-119">The behavior specifies that the server certificate is to be used for service authentication.</span></span> <span data-ttu-id="d5b73-120">Il certificato server deve contenere `SubjectName` lo `findValue` stesso valore per l'attributo come nell'elemento [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) di configurazione serviceCertificate>.</span><span class="sxs-lookup"><span data-stu-id="d5b73-120">The server certificate must contain the same value for the `SubjectName` as the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) configuration element.</span></span> <span data-ttu-id="d5b73-121">Inoltre, il comportamento specifica che l'autenticazione delle coppie nome utente-password viene eseguita dal provider di appartenenze ASP.NET e il mapping dei ruoli viene eseguito dal provider di ruoli ASP.NET specificando i nomi definiti per i due provider.</span><span class="sxs-lookup"><span data-stu-id="d5b73-121">In addition the behavior specifies that authentication of username-password pairs is performed by the ASP.NET membership provider and role mapping is performed by the ASP.NET role provider by specifying the names defined for the two providers.</span></span>  
  
```xml  
<system.serviceModel>  
  
  <protocolMapping>  
    <add scheme="http" binding="wsHttpBinding" />  
  </protocolMapping>  
  
  <bindings>  
    <wsHttpBinding>  
      <!-- Set up a binding that uses Username as the client credential type -->  
      <binding>  
        <security mode ="Message">  
          <message clientCredentialType ="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <behaviors>  
    <serviceBehaviors>  
      <behavior>  
        <!-- Configure role based authorization to use the Role Provider -->  
        <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                              roleProviderName ="SqlRoleProvider" />  
        <serviceCredentials>  
          <!-- Configure user name authentication to use the Membership Provider -->  
          <userNameAuthentication userNamePasswordValidationMode ="MembershipProvider"
                                  membershipProviderName ="SqlMembershipProvider"/>  
          <!-- Configure the service certificate -->  
          <serviceCertificate storeLocation ="LocalMachine"
                              storeName ="My"
                              x509FindType ="FindBySubjectName"  
                              findValue ="localhost" />  
        </serviceCredentials>  
        <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
        <serviceDebug includeExceptionDetailInFaults="false" />  
        <serviceMetadata httpGetEnabled="true"/>  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="d5b73-122">Quando si esegue l'esempio, il client chiama le varie operazioni del servizio con tre account utente diversi: Alice, Bob e Charlie.</span><span class="sxs-lookup"><span data-stu-id="d5b73-122">When you run the sample, the client calls the various service operations under three different user accounts: Alice, Bob, and Charlie.</span></span> <span data-ttu-id="d5b73-123">Le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="d5b73-123">The operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="d5b73-124">Tutte le 4 chiamate eseguite con l'account utente "Alice" hanno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d5b73-124">All four calls made as user "Alice" should succeed.</span></span> <span data-ttu-id="d5b73-125">L'utente "Bob" ottiene un errore di accesso negato nel tentativo di chiamare il metodo Divide.</span><span class="sxs-lookup"><span data-stu-id="d5b73-125">User "Bob" should get an access denied error when trying to call the Divide method.</span></span> <span data-ttu-id="d5b73-126">L'utente "Charlie" ottiene un errore di accesso negato nel tentativo di chiamare il metodo Multiply.</span><span class="sxs-lookup"><span data-stu-id="d5b73-126">User "Charlie" should get an access denied error when trying to call the Multiply method.</span></span> <span data-ttu-id="d5b73-127">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="d5b73-127">Press ENTER in the client window to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d5b73-128">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="d5b73-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="d5b73-129">Per compilare l'edizione della soluzione in C,NET o Visual Basic .NET, seguire le istruzioni riportate in [Esecuzione di Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d5b73-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
2. <span data-ttu-id="d5b73-130">Assicurarsi di aver configurato il [ASP.NET Database di Application Services](https://go.microsoft.com/fwlink/?LinkId=94997).</span><span class="sxs-lookup"><span data-stu-id="d5b73-130">Ensure that you have configured the [ASP.NET Application Services Database](https://go.microsoft.com/fwlink/?LinkId=94997).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d5b73-131">Se si sta eseguendo SQL Server Express Edition, il nome del server è .\SQLEXPRESS.</span><span class="sxs-lookup"><span data-stu-id="d5b73-131">If you are running SQL Server Express Edition, your server name is .\SQLEXPRESS.</span></span> <span data-ttu-id="d5b73-132">Questo server deve essere utilizzato durante la configurazione del database di Application Services ASP.NET e nella stringa di connessione Web.config.</span><span class="sxs-lookup"><span data-stu-id="d5b73-132">This server should be used when configuring the ASP.NET Application Services Database as well as in the Web.config connection string.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d5b73-133">L'account del processo di lavoro ASP.NET deve disporre delle autorizzazioni per il database creato in questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="d5b73-133">The ASP.NET worker process account must have permissions on the database that is created in this step.</span></span> <span data-ttu-id="d5b73-134">Utilizzare l'utilità sqlcmd o SQL Server Management Studio per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="d5b73-134">Use the sqlcmd utility or SQL Server Management Studio to do this.</span></span>  
  
3. <span data-ttu-id="d5b73-135">Per eseguire l'esempio su un solo computer o tra computer diversi, seguire le istruzioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="d5b73-135">To run the sample in a single- or cross-computer configuration, use the following instructions.</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="d5b73-136">Per eseguire l'esempio nello stesso computer</span><span class="sxs-lookup"><span data-stu-id="d5b73-136">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="d5b73-137">Verificare che il percorso includa la cartella in cui si trova Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="d5b73-137">Make sure that the path includes the folder where Makecert.exe is located.</span></span>  
  
2. <span data-ttu-id="d5b73-138">Eseguire Setup.bat dalla cartella di installazione di esempio in un prompt dei comandi per sviluppatori per Visual Studio eseguire con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="d5b73-138">Run Setup.bat from the sample install folder in a Developer Command Prompt for Visual Studio run with administrator privileges.</span></span> <span data-ttu-id="d5b73-139">In questo modo vengono installati i certificati dei servizi necessari per l'esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="d5b73-139">This installs the service certificates required for running the sample.</span></span>  
  
3. <span data-ttu-id="d5b73-140">Avviare Client.exe da \client\bin.</span><span class="sxs-lookup"><span data-stu-id="d5b73-140">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="d5b73-141">L'attività del client viene visualizzata nella finestra dell'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="d5b73-141">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="d5b73-142">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="d5b73-142">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="d5b73-143">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="d5b73-143">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="d5b73-144">Creare una directory sul computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="d5b73-144">Create a directory on the service computer.</span></span> <span data-ttu-id="d5b73-145">Creare un'applicazione virtuale denominata servicemodelsamples per questa directory usando lo strumento di gestione di Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="d5b73-145">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2. <span data-ttu-id="d5b73-146">Copiare i file del programma del servizio da \inetpub\wwwroot\servicemodelsamples nella directory virtuale sul computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="d5b73-146">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="d5b73-147">Assicurarsi di copiare i file nella sottodirectory \bin</span><span class="sxs-lookup"><span data-stu-id="d5b73-147">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="d5b73-148">e i file Setup.bat, GetComputerName.vbs e Cleanup.bat nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="d5b73-148">Also copy the Setup.bat, GetComputerName.vbs, and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="d5b73-149">Creare una directory sul client del servizio per i file binari del client.</span><span class="sxs-lookup"><span data-stu-id="d5b73-149">Create a directory on the client computer for the client binaries.</span></span>  
  
4. <span data-ttu-id="d5b73-150">Copiare i file di programma del client nella directory del client sul computer relativo</span><span class="sxs-lookup"><span data-stu-id="d5b73-150">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="d5b73-151">e i file Setup.bat, Cleanup.bat e ImportServiceCert.bat nel client.</span><span class="sxs-lookup"><span data-stu-id="d5b73-151">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="d5b73-152">Sul server aprire un prompt dei comandi per sviluppatori `setup.bat service`per Visual Studio con privilegi amministrativi ed eseguire .</span><span class="sxs-lookup"><span data-stu-id="d5b73-152">On the server, open a Developer Command Prompt for Visual Studio with administrative privileges and run `setup.bat service`.</span></span> <span data-ttu-id="d5b73-153">In `setup.bat` esecuzione `service` con l'argomento crea un certificato del servizio con il nome di dominio completo del computer ed esporta il certificato del servizio in un file denominato Service.cer.</span><span class="sxs-lookup"><span data-stu-id="d5b73-153">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="d5b73-154">Modificare Web.config in modo che rifletta il nuovo nome del certificato (nell'attributo `findValue` nell'>[ \<serviceCertificate ](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), che corrisponde al nome di dominio completo del computer.</span><span class="sxs-lookup"><span data-stu-id="d5b73-154">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7. <span data-ttu-id="d5b73-155">Copiare il file Service.cer dalla directory del servizio nella directory del client sul computer relativo.</span><span class="sxs-lookup"><span data-stu-id="d5b73-155">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="d5b73-156">Nel file Client.exe.config presente nel computer client modificare il valore dell'indirizzo della definizione dell'endpoint in base al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="d5b73-156">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="d5b73-157">Nel client aprire un prompt dei comandi per sviluppatori per Visual Studio con privilegi amministrativi ed eseguire ImportServiceCert.bat.On the client, open a Developer Command Prompt for Visual Studio with administrative privileges and run ImportServiceCert.bat.</span><span class="sxs-lookup"><span data-stu-id="d5b73-157">On the client, open a Developer Command Prompt for Visual Studio with administrative privileges and run ImportServiceCert.bat.</span></span> <span data-ttu-id="d5b73-158">In questo modo viene importato il certificato del servizio dal file Service.cer nell'archivio CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="d5b73-158">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="d5b73-159">Sul computer client avviare Client.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="d5b73-159">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="d5b73-160">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="d5b73-160">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="d5b73-161">Per eseguire la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="d5b73-161">To clean up after the sample</span></span>  
  
- <span data-ttu-id="d5b73-162">Eseguire Cleanup.bat nella cartella degli esempi dopo che l'esempio è stato completato.</span><span class="sxs-lookup"><span data-stu-id="d5b73-162">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d5b73-163">Questo script non rimuove i certificati del servizio da un client quando si esegue l'esempio tra più computer.</span><span class="sxs-lookup"><span data-stu-id="d5b73-163">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="d5b73-164">Se sono stati eseguiti esempi di Windows Communication Foundation (WCF) che utilizzano certificati tra computer, assicurarsi di cancellare i certificati del servizio installati nell'archivio CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="d5b73-164">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="d5b73-165">Per eseguire questa operazione, usare il seguente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Ad esempio: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="d5b73-165">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
## <a name="the-setup-batch-file"></a><span data-ttu-id="d5b73-166">File batch di installazione</span><span class="sxs-lookup"><span data-stu-id="d5b73-166">The Setup Batch File</span></span>  
 <span data-ttu-id="d5b73-167">Il file batch Setup.bat incluso in questo esempio consente di configurare il server con i certificati attinenti per eseguire un'applicazione indipendente che richiede la sicurezza server basata su certificato.</span><span class="sxs-lookup"><span data-stu-id="d5b73-167">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="d5b73-168">Questo file batch deve essere modificato per funzionare tra computer diversi o nel caso in cui non sia ospitato.</span><span class="sxs-lookup"><span data-stu-id="d5b73-168">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>  
  
 <span data-ttu-id="d5b73-169">Di seguito viene fornita una breve panoramica delle varie sezioni dei file batch in modo che possano essere modificate per l'esecuzione nella configurazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="d5b73-169">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>  
  
- <span data-ttu-id="d5b73-170">Creazione del certificato server.</span><span class="sxs-lookup"><span data-stu-id="d5b73-170">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="d5b73-171">Le righe seguenti del file batch Setup.bat creano il certificato server da usare.</span><span class="sxs-lookup"><span data-stu-id="d5b73-171">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="d5b73-172">La variabile %SERVER_NAME% specifica il nome del server.</span><span class="sxs-lookup"><span data-stu-id="d5b73-172">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="d5b73-173">Modificare questa variabile per specificare nome del server.</span><span class="sxs-lookup"><span data-stu-id="d5b73-173">Change this variable to specify your own server name.</span></span> <span data-ttu-id="d5b73-174">Il valore predefinito di questo file batch è localhost.</span><span class="sxs-lookup"><span data-stu-id="d5b73-174">This batch file defaults it to localhost.</span></span>  
  
     <span data-ttu-id="d5b73-175">Il certificato viene memorizzato nell'archivio personale nel percorso di archivio LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="d5b73-175">The certificate is stored in My (Personal) store under the LocalMachine store location.</span></span>  
  
    ```console
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
- <span data-ttu-id="d5b73-176">Installazione del certificato server nell'archivio certificati attendibili del client.</span><span class="sxs-lookup"><span data-stu-id="d5b73-176">Installing the server certificate into the client's trusted certificate store.</span></span>  
  
     <span data-ttu-id="d5b73-177">Le righe seguenti nel file batch Setup.bat copiano il certificato server nell'archivio di persone attendibile del client.</span><span class="sxs-lookup"><span data-stu-id="d5b73-177">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="d5b73-178">Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client.</span><span class="sxs-lookup"><span data-stu-id="d5b73-178">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="d5b73-179">Se è già disponibile un certificato impostato come radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il popolamento dell'archivio certificati client con il certificato server non è necessario.</span><span class="sxs-lookup"><span data-stu-id="d5b73-179">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```bat  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
