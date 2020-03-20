---
title: 'Procedura: configurare una porta con un certificato SSL'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
ms.openlocfilehash: 90d5424e12bb770dc3da85e1b2738206f4777c0c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185102"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a><span data-ttu-id="d5335-102">Procedura: configurare una porta con un certificato SSL</span><span class="sxs-lookup"><span data-stu-id="d5335-102">How to: Configure a Port with an SSL Certificate</span></span>

<span data-ttu-id="d5335-103">Quando si crea un servizio Windows Communication Foundation <xref:System.ServiceModel.WSHttpBinding> (WCF) self-hosted con la classe che utilizza la sicurezza del trasporto, è inoltre necessario configurare una porta con un certificato X.509.When creating a self-hosted Windows Communication Foundation (WCF) service with the class that uses transport security, you must also configure a port with an X.509 certificate.</span><span class="sxs-lookup"><span data-stu-id="d5335-103">When creating a self-hosted Windows Communication Foundation (WCF) service with the <xref:System.ServiceModel.WSHttpBinding> class that uses transport security, you must also configure a port with an X.509 certificate.</span></span> <span data-ttu-id="d5335-104">Se non si intende creare un servizio indipendente, è possibile ospitare il servizio in Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="d5335-104">If you are not creating a self-hosted service, you can host your service on Internet Information Services (IIS).</span></span> <span data-ttu-id="d5335-105">Per ulteriori informazioni, vedere [Protezione del trasporto HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="d5335-105">For more information, see [HTTP Transport Security](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span></span>  
  
 <span data-ttu-id="d5335-106">Per configurare una porta, lo strumento da usare dipende dal sistema operativo eseguito nel computer.</span><span class="sxs-lookup"><span data-stu-id="d5335-106">To configure a port, the tool you use depends on the operating system that is running on your machine.</span></span>  
  
 <span data-ttu-id="d5335-107">Se si esegue Windows Server 2003, utilizzare lo strumento HttpCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="d5335-107">If you are running Windows Server 2003, use the HttpCfg.exe tool.</span></span> <span data-ttu-id="d5335-108">In Windows Server 2003, questo strumento è installato.</span><span class="sxs-lookup"><span data-stu-id="d5335-108">On Windows Server 2003, this tool is installed.</span></span> <span data-ttu-id="d5335-109">Per ulteriori informazioni, vedere [Cenni preliminari su Httpcfg](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="d5335-109">For more information, see [Httpcfg Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)).</span></span> <span data-ttu-id="d5335-110">Nella [documentazione relativa](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) agli Strumenti di supporto di Windows viene illustrata la sintassi dello strumento Httpcfg.exe.</span><span class="sxs-lookup"><span data-stu-id="d5335-110">The [Windows Support Tools documentation](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) explains the syntax for the Httpcfg.exe tool.</span></span>  
  
 <span data-ttu-id="d5335-111">Se si esegue Windows Vista, utilizzare lo strumento Netsh.exe già installato.</span><span class="sxs-lookup"><span data-stu-id="d5335-111">If you are running Windows Vista, use the Netsh.exe tool that is already installed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d5335-112">La modifica dei certificati archiviati nel computer richiede privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="d5335-112">Modifying certificates stored on the computer requires administrative privileges.</span></span>  
  
## <a name="determine-how-ports-are-configured"></a><span data-ttu-id="d5335-113">Determinare la modalità di configurazione delle porte</span><span class="sxs-lookup"><span data-stu-id="d5335-113">Determine how ports are configured</span></span>  
  
1. <span data-ttu-id="d5335-114">In Windows Server 2003 o Windows XP, utilizzare lo strumento HttpCfg.exe per visualizzare la configurazione della porta corrente, utilizzando le opzioni **query** e **ssl,** come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d5335-114">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool to view the current port configuration, using the **query** and **ssl** switches, as shown in the following example.</span></span>  
  
    ```console
    httpcfg query ssl  
    ```  
  
2. <span data-ttu-id="d5335-115">In Windows Vista, utilizzare lo strumento Netsh.exe per visualizzare la configurazione della porta corrente, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d5335-115">In Windows Vista, use the Netsh.exe tool to view the current port configuration, as shown in the following example.</span></span>  
  
    ```console  
    netsh http show sslcert  
    ```  
  
## <a name="get-a-certificates-thumbprint"></a><span data-ttu-id="d5335-116">Ottenere l'identificazione personale di un certificatoGet a certificate's thumbprint</span><span class="sxs-lookup"><span data-stu-id="d5335-116">Get a certificate's thumbprint</span></span>  
  
1. <span data-ttu-id="d5335-117">Usare lo snap-in MMC Certificati per individuare un certificato X.509 che abbia come scopo previsto l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="d5335-117">Use the Certificates MMC snap-in to find an X.509 certificate that has an intended purpose of client authentication.</span></span> <span data-ttu-id="d5335-118">Per altre informazioni, vedere [Procedura: Visualizzare certificati con lo snap-in MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="d5335-118">For more information, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2. <span data-ttu-id="d5335-119">Accedere all'identificazione personale del certificato.</span><span class="sxs-lookup"><span data-stu-id="d5335-119">Access the certificate's thumbprint.</span></span> <span data-ttu-id="d5335-120">Per altre informazioni, vedere [Procedura: recuperare l'identificazione personale di un certificato](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="d5335-120">For more information, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
3. <span data-ttu-id="d5335-121">Copiare l'identificazione personale del certificato in un editor di testo, ad esempio Blocco note.</span><span class="sxs-lookup"><span data-stu-id="d5335-121">Copy the thumbprint of the certificate into a text editor, such as Notepad.</span></span>  
  
4. <span data-ttu-id="d5335-122">Rimuovere tutti gli spazi tra i caratteri esadecimali.</span><span class="sxs-lookup"><span data-stu-id="d5335-122">Remove all spaces between the hexadecimal characters.</span></span> <span data-ttu-id="d5335-123">Per eseguire questa operazione, è possibile usare la funzionalità Trova e sostituisci dell'editor di testo per sostituire ogni spazio con un carattere null.</span><span class="sxs-lookup"><span data-stu-id="d5335-123">One way to accomplish this is to use the text editor's find-and-replace feature and replace each space with a null character.</span></span>  
  
## <a name="bind-an-ssl-certificate-to-a-port-number"></a><span data-ttu-id="d5335-124">Associare un certificato SSL a un numero di portaBind an SSL certificate to a port number</span><span class="sxs-lookup"><span data-stu-id="d5335-124">Bind an SSL certificate to a port number</span></span>  
  
1. <span data-ttu-id="d5335-125">In Windows Server 2003 o Windows XP, utilizzare lo strumento HttpCfg.exe in modalità "set" nell'archivio SSL (Secure Sockets Layer) per associare il certificato a un numero di porta.</span><span class="sxs-lookup"><span data-stu-id="d5335-125">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool in "set" mode on the Secure Sockets Layer (SSL) store to bind the certificate to a port number.</span></span> <span data-ttu-id="d5335-126">Lo strumento usa l'identificazione personale per identificare il certificato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d5335-126">The tool uses the thumbprint to identify the certificate, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - <span data-ttu-id="d5335-127">L'opzione **-i** ha `IP``port` la sintassi di : e indica allo strumento di impostare il certificato sulla porta 8012 del computer.</span><span class="sxs-lookup"><span data-stu-id="d5335-127">The **-i** switch has the syntax of `IP`:`port` and instructs the tool to set the certificate to port 8012 of the computer.</span></span> <span data-ttu-id="d5335-128">I quattro zero che precedono il numero possono essere anche sostituiti dall'indirizzo IP effettivo del computer.</span><span class="sxs-lookup"><span data-stu-id="d5335-128">Optionally, the four zeroes that precede the number can also be replaced by the actual IP address of the computer.</span></span>  
  
    - <span data-ttu-id="d5335-129">L'opzione **-h** specifica l'identificazione personale del certificato.</span><span class="sxs-lookup"><span data-stu-id="d5335-129">The **-h** switch specifies the thumbprint of the certificate.</span></span>  
  
2. <span data-ttu-id="d5335-130">In Windows Vista, utilizzare lo strumento Netsh.exe, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d5335-130">In Windows Vista, use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}
    ```  
  
    - <span data-ttu-id="d5335-131">Il parametro **certhash** consente di specificare l'identificazione personale del certificato.</span><span class="sxs-lookup"><span data-stu-id="d5335-131">The **certhash** parameter specifies the thumbprint of the certificate.</span></span>  
  
    - <span data-ttu-id="d5335-132">Il parametro **ipport** consente di specificare l'indirizzo IP e la porta e funziona come l'opzione **-i** dello strumento Httpcfg.exe descritto.</span><span class="sxs-lookup"><span data-stu-id="d5335-132">The **ipport** parameter specifies the IP address and port, and functions just like the **-i** switch of the Httpcfg.exe tool described.</span></span>  
  
    - <span data-ttu-id="d5335-133">Il parametro **appid** è un GUID che può essere utilizzato per identificare l'applicazione proprietaria.</span><span class="sxs-lookup"><span data-stu-id="d5335-133">The **appid** parameter is a GUID that can be used to identify the owning application.</span></span>  
  
## <a name="bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a><span data-ttu-id="d5335-134">Associare un certificato SSL a un numero di porta e supportare i certificati clientBind an SSL certificate to a port number and support client certificates</span><span class="sxs-lookup"><span data-stu-id="d5335-134">Bind an SSL certificate to a port number and support client certificates</span></span>  
  
1. <span data-ttu-id="d5335-135">In Windows Server 2003 o Windows XP, per supportare i client che eseguono l'autenticazione con certificati X.509 a livello di trasporto, seguire la procedura precedente ma passare un parametro della riga di comando aggiuntivo a HttpCfg.exe, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d5335-135">In Windows Server 2003 or Windows XP, to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure but pass an additional command-line parameter to HttpCfg.exe, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     <span data-ttu-id="d5335-136">L'opzione **-f** ha `n` la sintassi di dove n è un numero compreso tra 1 e 7.</span><span class="sxs-lookup"><span data-stu-id="d5335-136">The **-f** switch has the syntax of `n` where n is a number between 1 and 7.</span></span> <span data-ttu-id="d5335-137">Un valore di 2, come mostrato nell'esempio precedente, abilita certificati client a livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="d5335-137">A value of 2, as shown in the preceding example, enables client certificates at the transport layer.</span></span> <span data-ttu-id="d5335-138">Il valore 3 attiva i certificati client e associa tali certificati a un account Windows.</span><span class="sxs-lookup"><span data-stu-id="d5335-138">A value of 3 enables client certificates and maps those certificates to a Windows account.</span></span> <span data-ttu-id="d5335-139">Per il comportamento di altri valori, vedere la Guida di HttpCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="d5335-139">See HttpCfg.exe Help for the behavior of other values.</span></span>  
  
2. <span data-ttu-id="d5335-140">In Windows Vista, per supportare i client che eseguono l'autenticazione con certificati X.509 a livello di trasporto, seguire la procedura precedente, ma con un parametro aggiuntivo, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d5335-140">In Windows Vista, to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure, but with an additional parameter, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
## <a name="delete-an-ssl-certificate-from-a-port-number"></a><span data-ttu-id="d5335-141">Eliminare un certificato SSL da un numero di portaDelete an SSL certificate from a port number</span><span class="sxs-lookup"><span data-stu-id="d5335-141">Delete an SSL certificate from a port number</span></span>  
  
1. <span data-ttu-id="d5335-142">Usare lo strumento HttpCfg.exe o Netsh.exe per visualizzare le porte e le identificazioni personali di tutti i binding nel computer.</span><span class="sxs-lookup"><span data-stu-id="d5335-142">Use the HttpCfg.exe or Netsh.exe tool to see the ports and thumbprints of all bindings on the computer.</span></span> <span data-ttu-id="d5335-143">Per stampare le informazioni su disco, utilizzare il carattere di reindirizzamento ">", come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d5335-143">To print the information to disk, use the redirection character ">", as shown in the following example.</span></span>  
  
    ```console  
    httpcfg query ssl>myMachinePorts.txt  
    ```
  
2. <span data-ttu-id="d5335-144">In Windows Server 2003 o Windows XP, utilizzare lo strumento HttpCfg.exe con le parole chiave **delete** e **ssl.**</span><span class="sxs-lookup"><span data-stu-id="d5335-144">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool with the **delete** and **ssl** keywords.</span></span> <span data-ttu-id="d5335-145">Utilizzare l'opzione **-i** per specificare il `IP`numero :`port` e l'opzione **-h** per specificare l'identificazione personale.</span><span class="sxs-lookup"><span data-stu-id="d5335-145">Use the **-i** switch to specify the `IP`:`port` number, and the **-h** switch to specify the thumbprint.</span></span>  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. <span data-ttu-id="d5335-146">In Windows Vista, utilizzare lo strumento Netsh.exe, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d5335-146">In Windows Vista, use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a><span data-ttu-id="d5335-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="d5335-147">Example</span></span>  

 <span data-ttu-id="d5335-148">Nel codice seguente viene illustrato come creare un servizio indipendente usando la classe <xref:System.ServiceModel.WSHttpBinding> per la protezione del trasporto.</span><span class="sxs-lookup"><span data-stu-id="d5335-148">The following code shows how to create a self-hosted service using the <xref:System.ServiceModel.WSHttpBinding> class set to transport security.</span></span> <span data-ttu-id="d5335-149">Quando si crea un'applicazione, specificare il numero di porta nell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="d5335-149">When creating an application, specify the port number in the address.</span></span>  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="d5335-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5335-150">See also</span></span>

- [<span data-ttu-id="d5335-151">Protezione del trasporto HTTP</span><span class="sxs-lookup"><span data-stu-id="d5335-151">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
