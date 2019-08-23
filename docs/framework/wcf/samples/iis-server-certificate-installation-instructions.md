---
title: Istruzioni di installazione certificato server IIS (Internet Information Services)
ms.date: 03/30/2017
ms.assetid: 11281490-d2ac-4324-8f33-e7714611a34b
ms.openlocfilehash: 50fa7f1094d4b05bcadb229072293da233a18a2b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931861"
---
# <a name="internet-information-services-iis-server-certificate-installation-instructions"></a><span data-ttu-id="6d5c6-102">Istruzioni di installazione certificato server IIS (Internet Information Services)</span><span class="sxs-lookup"><span data-stu-id="6d5c6-102">Internet Information Services (IIS) Server Certificate Installation Instructions</span></span>
<span data-ttu-id="6d5c6-103">Per eseguire gli esempi che comunicano in modo sicuro con IIS (Internet Information Services) è necessario creare e installare un certificato server.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-103">To run the samples that securely communicate with Internet Information Services (IIS), you must create and install a server certificate.</span></span>  
  
## <a name="step-1-creating-certificates"></a><span data-ttu-id="6d5c6-104">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-104">Step 1.</span></span> <span data-ttu-id="6d5c6-105">Creazione di certificati</span><span class="sxs-lookup"><span data-stu-id="6d5c6-105">Creating Certificates</span></span>  
 <span data-ttu-id="6d5c6-106">Per creare un certificato per il computer, aprire un Prompt dei comandi per gli sviluppatori per Visual Studio con privilegi di amministratore ed eseguire il file Setup. bat incluso in tutti gli esempi che usano la comunicazione protetta con IIS.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-106">To create a certificate for your computer, open a Developer Command Prompt for Visual Studio with administrator privileges and run the Setup.bat that is included in each of the samples that use secure communication with IIS.</span></span> <span data-ttu-id="6d5c6-107">Assicurarsi che il percorso includa la cartella contenente Makecert.exe prima di eseguire questo file batch.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-107">Ensure that the path includes the folder that contains Makecert.exe before you run this batch file.</span></span> <span data-ttu-id="6d5c6-108">Il comando seguente viene utilizzato per creare il certificato nel file Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-108">The following command is used to create the certificate in Setup.bat.</span></span>  
  
```  
makecert -sr LocalMachine -ss My -n CN=ServiceModelSamples-HTTPS-Server -sky exchange -sk ServiceModelSamples-HTTPS-Key  
```  
  
## <a name="step-2-installing-certificates"></a><span data-ttu-id="6d5c6-109">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-109">Step 2.</span></span> <span data-ttu-id="6d5c6-110">Installazione dei certificati</span><span class="sxs-lookup"><span data-stu-id="6d5c6-110">Installing Certificates</span></span>  
 <span data-ttu-id="6d5c6-111">I passaggi necessari per installare i certificati appena creati dipendono dalla versione di IIS che si sta utilizzando.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-111">The steps required to install the certificates you just created depend on which version of IIS you are using.</span></span>  
  
#### <a name="to-install-iis-on-iis-51-windows-xp-and-iis-60-windows-server-2003"></a><span data-ttu-id="6d5c6-112">Installazione di IIS su IIS 5.1 (Windows XP) e IIS 6.0 (Windows Server 2003)</span><span class="sxs-lookup"><span data-stu-id="6d5c6-112">To install IIS on IIS 5.1 (Windows XP) and IIS 6.0 (Windows Server 2003)</span></span>  
  
1. <span data-ttu-id="6d5c6-113">Aprire lo snap-in MMC della Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="6d5c6-113">Open the Internet Information Services Manager MMC Snap-In.</span></span>  
  
2. <span data-ttu-id="6d5c6-114">Fare clic con il pulsante destro del mouse sul sito Web predefinito e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-114">Right-click the default Web site and select **Properties**.</span></span>  
  
3. <span data-ttu-id="6d5c6-115">Selezionare la scheda **sicurezza directory** .</span><span class="sxs-lookup"><span data-stu-id="6d5c6-115">Select the **Directory Security** tab.</span></span>  
  
4. <span data-ttu-id="6d5c6-116">Fare clic sul pulsante **certificato server** .</span><span class="sxs-lookup"><span data-stu-id="6d5c6-116">Click the **Server Certificate** button.</span></span> <span data-ttu-id="6d5c6-117">Verrà avviata la Procedura guidata certificati server Web.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-117">The Web Server Certificate Wizard starts.</span></span>  
  
5. <span data-ttu-id="6d5c6-118">Completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-118">Complete the wizard.</span></span> <span data-ttu-id="6d5c6-119">Selezionare l'opzione per assegnare un certificato.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-119">Select the option to assign a certificate.</span></span> <span data-ttu-id="6d5c6-120">Selezionare il certificato server HTTPS ServiceModelSamples nell'elenco di certificati visualizzati.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-120">Select the ServiceModelSamples-HTTPS-Server certificate from the list of certificates that are displayed.</span></span>  
  
     <span data-ttu-id="6d5c6-121">![Creazione guidata certificato IIS](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span><span class="sxs-lookup"><span data-stu-id="6d5c6-121">![IIS Certificate Wizard](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span></span>  
  
6. <span data-ttu-id="6d5c6-122">Testare l'accesso al servizio in un browser tramite l'indirizzo `https://localhost/servicemodelsamples/service.svc`HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-122">Test access to the service in a browser by using the HTTPS address `https://localhost/servicemodelsamples/service.svc`.</span></span>  
  
#### <a name="if-ssl-was-previously-configured-by-using-httpcfgexe"></a><span data-ttu-id="6d5c6-123">Se SSL è stato precedentemente configurato utilizzando Httpcfg.exe</span><span class="sxs-lookup"><span data-stu-id="6d5c6-123">If SSL was previously configured by using Httpcfg.exe</span></span>  
  
1. <span data-ttu-id="6d5c6-124">Utilizzare Makecert.exe (o eseguire Setup.bat) per creare il certificato server.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-124">Use Makecert.exe (or run Setup.bat) to create the server certificate.</span></span>  
  
2. <span data-ttu-id="6d5c6-125">Eseguire la gestione IIS e installare il certificato secondo i passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-125">Run the IIS manager and install the certificate according to the previous steps.</span></span>  
  
3. <span data-ttu-id="6d5c6-126">Aggiungere le righe di codice seguenti al programma client.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-126">Add the following line of code to the client program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6d5c6-127">Questo codice è necessario solo per certificati di prova come ad esempio quelli creati da Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-127">This code is only required for test certificates such as those created by Makecert.exe.</span></span> <span data-ttu-id="6d5c6-128">Non è una pratica consigliabile per il codice di produzione.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-128">It is not recommended for production code.</span></span>  
  
```  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
#### <a name="to-install-iis-on-iis-70-windows-vista-and-windows-server-2008"></a><span data-ttu-id="6d5c6-129">Per installare IIS su IIS 7.0 (Windows Vista e Windows Server 2008)</span><span class="sxs-lookup"><span data-stu-id="6d5c6-129">To install IIS on IIS 7.0 (Windows Vista and Windows Server 2008)</span></span>  
  
1. <span data-ttu-id="6d5c6-130">Dal menu **Start** fare clic su **Esegui**, quindi digitare **inetmgr** per aprire lo snap-in MMC Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="6d5c6-130">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="6d5c6-131">Fare clic con il pulsante destro del mouse sul **sito Web predefinito** e scegliere **Modifica binding...**</span><span class="sxs-lookup"><span data-stu-id="6d5c6-131">Right-click the **Default Web Site** and select **Edit Bindings…**</span></span>  
  
3. <span data-ttu-id="6d5c6-132">Fare clic sul pulsante **Aggiungi** della finestra di dialogo **binding sito** .</span><span class="sxs-lookup"><span data-stu-id="6d5c6-132">Click the **Add** button of the **Site Bindings** dialog box.</span></span>  
  
4. <span data-ttu-id="6d5c6-133">Selezionare **https** dall'elenco a discesa **tipo** .</span><span class="sxs-lookup"><span data-stu-id="6d5c6-133">Select **HTTPS** from the **Type** drop-down list.</span></span>  
  
5. <span data-ttu-id="6d5c6-134">Selezionare **servicemodelsamples-https-server** dall'elenco a discesa **certificato SSL** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-134">Select the **ServiceModelSamples-HTTPS-Server** from the **SSL certificate** drop-down list and click **OK**.</span></span>  
  
6. <span data-ttu-id="6d5c6-135">Testare l'accesso al servizio in un browser tramite l'indirizzo `https://localhost/servicemodelsamples/service.svc`HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-135">Test access to the service in a browser by using the HTTPS address `https://localhost/servicemodelsamples/service.svc`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6d5c6-136">Dato che il certificato di prova appena installato non è un certificato attendibile, possono essere visualizzati avvisi di sicurezza di Internet Explorer aggiuntivi quando si visitano indirizzi Web locali protetti da questo certificato.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-136">Because the test certificate you have just installed is not a trusted certificate, you may encounter additional Internet Explorer security warnings when browsing to local Web addresses secured with this certificate.</span></span>  
  
## <a name="removing-certificates"></a><span data-ttu-id="6d5c6-137">Rimozione dei certificati</span><span class="sxs-lookup"><span data-stu-id="6d5c6-137">Removing Certificates</span></span>  
  
- <span data-ttu-id="6d5c6-138">Utilizzare Gestione Internet Information Services come illustrato in precedenza, ma rimuovere il certificato o l'associazione anziché aggiungerlo.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-138">Use the Internet Information Services Manager as previously directed, but remove the certificate or binding instead of adding it.</span></span>  
  
- <span data-ttu-id="6d5c6-139">Rimuovere il certificato del computer utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="6d5c6-139">Remove the computer certificate by using the following command.</span></span>  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:443  
    ```
