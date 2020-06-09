---
title: Istruzioni di installazione certificato server IIS (Internet Information Services)
ms.date: 03/30/2017
ms.assetid: 11281490-d2ac-4324-8f33-e7714611a34b
ms.openlocfilehash: 301a10c615a13a42e1a6e1b89d2724476ca4fbae
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594660"
---
# <a name="internet-information-services-iis-server-certificate-installation-instructions"></a><span data-ttu-id="2ef19-102">Istruzioni di installazione certificato server IIS (Internet Information Services)</span><span class="sxs-lookup"><span data-stu-id="2ef19-102">Internet Information Services (IIS) Server Certificate Installation Instructions</span></span>
<span data-ttu-id="2ef19-103">Per eseguire gli esempi che comunicano in modo sicuro con IIS (Internet Information Services) è necessario creare e installare un certificato server.</span><span class="sxs-lookup"><span data-stu-id="2ef19-103">To run the samples that securely communicate with Internet Information Services (IIS), you must create and install a server certificate.</span></span>  
  
## <a name="step-1-creating-certificates"></a><span data-ttu-id="2ef19-104">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="2ef19-104">Step 1.</span></span> <span data-ttu-id="2ef19-105">Creazione di certificati</span><span class="sxs-lookup"><span data-stu-id="2ef19-105">Creating Certificates</span></span>  
 <span data-ttu-id="2ef19-106">Per creare un certificato per il computer, aprire un Prompt dei comandi per gli sviluppatori per Visual Studio con privilegi di amministratore ed eseguire il file Setup. bat incluso in tutti gli esempi che usano la comunicazione protetta con IIS.</span><span class="sxs-lookup"><span data-stu-id="2ef19-106">To create a certificate for your computer, open a Developer Command Prompt for Visual Studio with administrator privileges and run the Setup.bat that is included in each of the samples that use secure communication with IIS.</span></span> <span data-ttu-id="2ef19-107">Assicurarsi che il percorso includa la cartella contenente Makecert.exe prima di eseguire questo file batch.</span><span class="sxs-lookup"><span data-stu-id="2ef19-107">Ensure that the path includes the folder that contains Makecert.exe before you run this batch file.</span></span> <span data-ttu-id="2ef19-108">Il comando seguente viene utilizzato per creare il certificato nel file Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="2ef19-108">The following command is used to create the certificate in Setup.bat.</span></span>  
  
```console  
makecert -sr LocalMachine -ss My -n CN=ServiceModelSamples-HTTPS-Server -sky exchange -sk ServiceModelSamples-HTTPS-Key  
```  
  
## <a name="step-2-installing-certificates"></a><span data-ttu-id="2ef19-109">Passaggio 2:</span><span class="sxs-lookup"><span data-stu-id="2ef19-109">Step 2.</span></span> <span data-ttu-id="2ef19-110">Installazione dei certificati</span><span class="sxs-lookup"><span data-stu-id="2ef19-110">Installing Certificates</span></span>  
 <span data-ttu-id="2ef19-111">I passaggi necessari per installare i certificati appena creati dipendono dalla versione di IIS che si sta utilizzando.</span><span class="sxs-lookup"><span data-stu-id="2ef19-111">The steps required to install the certificates you just created depend on which version of IIS you are using.</span></span>  
  
#### <a name="to-install-iis-on-iis-51-windows-xp-and-iis-60-windows-server-2003"></a><span data-ttu-id="2ef19-112">Installazione di IIS su IIS 5.1 (Windows XP) e IIS 6.0 (Windows Server 2003)</span><span class="sxs-lookup"><span data-stu-id="2ef19-112">To install IIS on IIS 5.1 (Windows XP) and IIS 6.0 (Windows Server 2003)</span></span>  
  
1. <span data-ttu-id="2ef19-113">Aprire lo snap-in MMC della Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="2ef19-113">Open the Internet Information Services Manager MMC Snap-In.</span></span>  
  
2. <span data-ttu-id="2ef19-114">Fare clic con il pulsante destro del mouse sul sito Web predefinito e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="2ef19-114">Right-click the default Web site and select **Properties**.</span></span>  
  
3. <span data-ttu-id="2ef19-115">Selezionare la scheda **sicurezza directory** .</span><span class="sxs-lookup"><span data-stu-id="2ef19-115">Select the **Directory Security** tab.</span></span>  
  
4. <span data-ttu-id="2ef19-116">Fare clic sul pulsante **certificato server** .</span><span class="sxs-lookup"><span data-stu-id="2ef19-116">Click the **Server Certificate** button.</span></span> <span data-ttu-id="2ef19-117">Verrà avviata la Procedura guidata certificati server Web.</span><span class="sxs-lookup"><span data-stu-id="2ef19-117">The Web Server Certificate Wizard starts.</span></span>  
  
5. <span data-ttu-id="2ef19-118">Completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="2ef19-118">Complete the wizard.</span></span> <span data-ttu-id="2ef19-119">Selezionare l'opzione per assegnare un certificato.</span><span class="sxs-lookup"><span data-stu-id="2ef19-119">Select the option to assign a certificate.</span></span> <span data-ttu-id="2ef19-120">Selezionare il certificato server HTTPS ServiceModelSamples nell'elenco di certificati visualizzati.</span><span class="sxs-lookup"><span data-stu-id="2ef19-120">Select the ServiceModelSamples-HTTPS-Server certificate from the list of certificates that are displayed.</span></span>  
  
     <span data-ttu-id="2ef19-121">![Gestione guidata certificati IIS](media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span><span class="sxs-lookup"><span data-stu-id="2ef19-121">![IIS Certificate Wizard](media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span></span>  
  
6. <span data-ttu-id="2ef19-122">Testare l'accesso al servizio in un browser tramite l'indirizzo HTTPS `https://localhost/servicemodelsamples/service.svc` .</span><span class="sxs-lookup"><span data-stu-id="2ef19-122">Test access to the service in a browser by using the HTTPS address `https://localhost/servicemodelsamples/service.svc`.</span></span>  
  
#### <a name="if-ssl-was-previously-configured-by-using-httpcfgexe"></a><span data-ttu-id="2ef19-123">Se SSL è stato precedentemente configurato utilizzando Httpcfg.exe</span><span class="sxs-lookup"><span data-stu-id="2ef19-123">If SSL was previously configured by using Httpcfg.exe</span></span>  
  
1. <span data-ttu-id="2ef19-124">Utilizzare Makecert.exe (o eseguire Setup.bat) per creare il certificato server.</span><span class="sxs-lookup"><span data-stu-id="2ef19-124">Use Makecert.exe (or run Setup.bat) to create the server certificate.</span></span>  
  
2. <span data-ttu-id="2ef19-125">Eseguire la gestione IIS e installare il certificato secondo i passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="2ef19-125">Run the IIS manager and install the certificate according to the previous steps.</span></span>  
  
3. <span data-ttu-id="2ef19-126">Aggiungere le righe di codice seguenti al programma client.</span><span class="sxs-lookup"><span data-stu-id="2ef19-126">Add the following line of code to the client program.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2ef19-127">Questo codice è necessario solo per certificati di prova come ad esempio quelli creati da Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="2ef19-127">This code is only required for test certificates such as those created by Makecert.exe.</span></span> <span data-ttu-id="2ef19-128">Non è una pratica consigliabile per il codice di produzione.</span><span class="sxs-lookup"><span data-stu-id="2ef19-128">It is not recommended for production code.</span></span>  
  
```csharp  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
#### <a name="to-install-iis-on-iis-70-windows-vista-and-windows-server-2008"></a><span data-ttu-id="2ef19-129">Per installare IIS su IIS 7.0 (Windows Vista e Windows Server 2008)</span><span class="sxs-lookup"><span data-stu-id="2ef19-129">To install IIS on IIS 7.0 (Windows Vista and Windows Server 2008)</span></span>  
  
1. <span data-ttu-id="2ef19-130">Dal menu **Start** fare clic su **Esegui**, quindi digitare **inetmgr** per aprire lo snap-in MMC Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="2ef19-130">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="2ef19-131">Fare clic con il pulsante destro del mouse sul **sito Web predefinito** e scegliere **Modifica binding...**</span><span class="sxs-lookup"><span data-stu-id="2ef19-131">Right-click the **Default Web Site** and select **Edit Bindings…**</span></span>  
  
3. <span data-ttu-id="2ef19-132">Fare clic sul pulsante **Aggiungi** della finestra di dialogo **binding sito** .</span><span class="sxs-lookup"><span data-stu-id="2ef19-132">Click the **Add** button of the **Site Bindings** dialog box.</span></span>  
  
4. <span data-ttu-id="2ef19-133">Selezionare **https** dall'elenco a discesa **tipo** .</span><span class="sxs-lookup"><span data-stu-id="2ef19-133">Select **HTTPS** from the **Type** drop-down list.</span></span>  
  
5. <span data-ttu-id="2ef19-134">Selezionare **servicemodelsamples-https-server** dall'elenco a discesa **certificato SSL** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ef19-134">Select the **ServiceModelSamples-HTTPS-Server** from the **SSL certificate** drop-down list and click **OK**.</span></span>  
  
6. <span data-ttu-id="2ef19-135">Testare l'accesso al servizio in un browser tramite l'indirizzo HTTPS `https://localhost/servicemodelsamples/service.svc` .</span><span class="sxs-lookup"><span data-stu-id="2ef19-135">Test access to the service in a browser by using the HTTPS address `https://localhost/servicemodelsamples/service.svc`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ef19-136">Dato che il certificato di prova appena installato non è un certificato attendibile, possono essere visualizzati avvisi di sicurezza di Internet Explorer aggiuntivi quando si visitano indirizzi Web locali protetti da questo certificato.</span><span class="sxs-lookup"><span data-stu-id="2ef19-136">Because the test certificate you have just installed is not a trusted certificate, you may encounter additional Internet Explorer security warnings when browsing to local Web addresses secured with this certificate.</span></span>  
  
## <a name="removing-certificates"></a><span data-ttu-id="2ef19-137">Rimozione dei certificati</span><span class="sxs-lookup"><span data-stu-id="2ef19-137">Removing Certificates</span></span>  
  
- <span data-ttu-id="2ef19-138">Utilizzare Gestione Internet Information Services come illustrato in precedenza, ma rimuovere il certificato o l'associazione anziché aggiungerlo.</span><span class="sxs-lookup"><span data-stu-id="2ef19-138">Use the Internet Information Services Manager as previously directed, but remove the certificate or binding instead of adding it.</span></span>  
  
- <span data-ttu-id="2ef19-139">Rimuovere il certificato del computer utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="2ef19-139">Remove the computer certificate by using the following command.</span></span>  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:443  
    ```
