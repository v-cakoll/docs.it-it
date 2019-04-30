---
title: 'Procedura: Configurare una porta con un certificato SSL'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
ms.openlocfilehash: d709123895f361c1d2268a218b4163c8d195e1b4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62047962"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a><span data-ttu-id="ff699-102">Procedura: Configurare una porta con un certificato SSL</span><span class="sxs-lookup"><span data-stu-id="ff699-102">How to: Configure a Port with an SSL Certificate</span></span>
<span data-ttu-id="ff699-103">Quando si crea un servizio Windows Communication Foundation (WCF) self-hosted con la <xref:System.ServiceModel.WSHttpBinding> che usa la protezione del trasporto di classi, è anche necessario configurare una porta con un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="ff699-103">When creating a self-hosted Windows Communication Foundation (WCF) service with the <xref:System.ServiceModel.WSHttpBinding> class that uses transport security, you must also configure a port with an X.509 certificate.</span></span> <span data-ttu-id="ff699-104">Se non si intende creare un servizio indipendente, è possibile ospitare il servizio in Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="ff699-104">If you are not creating a self-hosted service, you can host your service on Internet Information Services (IIS).</span></span> <span data-ttu-id="ff699-105">Per altre informazioni, vedere [protezione del trasporto HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="ff699-105">For more information, see [HTTP Transport Security](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span></span>  
  
 <span data-ttu-id="ff699-106">Per configurare una porta, lo strumento da usare dipende dal sistema operativo eseguito nel computer.</span><span class="sxs-lookup"><span data-stu-id="ff699-106">To configure a port, the tool you use depends on the operating system that is running on your machine.</span></span>  
  
 <span data-ttu-id="ff699-107">Se viene eseguito [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)], usare lo strumento HttpCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="ff699-107">If you are running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool.</span></span> <span data-ttu-id="ff699-108">Con [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], questo strumento è installato.</span><span class="sxs-lookup"><span data-stu-id="ff699-108">With [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] this tool is installed.</span></span> <span data-ttu-id="ff699-109">Con [!INCLUDE[wxp](../../../../includes/wxp-md.md)], è possibile scaricare lo strumento [strumenti di supporto di Windows XP Service Pack 2](https://go.microsoft.com/fwlink/?LinkId=88606).</span><span class="sxs-lookup"><span data-stu-id="ff699-109">With [!INCLUDE[wxp](../../../../includes/wxp-md.md)], you can download the tool at [Windows XP Service Pack 2 Support Tools](https://go.microsoft.com/fwlink/?LinkId=88606).</span></span> <span data-ttu-id="ff699-110">Per altre informazioni, vedere [Panoramica di Httpcfg](https://go.microsoft.com/fwlink/?LinkId=88605).</span><span class="sxs-lookup"><span data-stu-id="ff699-110">For more information, see [Httpcfg Overview](https://go.microsoft.com/fwlink/?LinkId=88605).</span></span> <span data-ttu-id="ff699-111">Il [documentazione di Windows Support Tools](https://go.microsoft.com/fwlink/?LinkId=94840) viene illustrata la sintassi per lo strumento Httpcfg.exe.</span><span class="sxs-lookup"><span data-stu-id="ff699-111">The [Windows Support Tools documentation](https://go.microsoft.com/fwlink/?LinkId=94840) explains the syntax for the Httpcfg.exe tool.</span></span>  
  
 <span data-ttu-id="ff699-112">Se viene eseguito [!INCLUDE[wv](../../../../includes/wv-md.md)], usare lo strumento Netsh.exe già installato.</span><span class="sxs-lookup"><span data-stu-id="ff699-112">If you are running [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool that is already installed.</span></span>  
  
 <span data-ttu-id="ff699-113">In questo argomento viene descritto come eseguire diverse procedure:</span><span class="sxs-lookup"><span data-stu-id="ff699-113">This topic describes how to accomplish several procedures:</span></span>  
  
- <span data-ttu-id="ff699-114">Determinazione della configurazione corrente delle porte di un computer</span><span class="sxs-lookup"><span data-stu-id="ff699-114">Determining a computer's current port configuration.</span></span>  
  
- <span data-ttu-id="ff699-115">Acquisizione dell'identificazione personale (necessaria per le due procedure seguenti) di un certificato</span><span class="sxs-lookup"><span data-stu-id="ff699-115">Getting a certificate's thumbprint (necessary for the following two procedures).</span></span>  
  
- <span data-ttu-id="ff699-116">Binding di un certificato SSL alla configurazione di una porta</span><span class="sxs-lookup"><span data-stu-id="ff699-116">Binding an SSL certificate to a port configuration.</span></span>  
  
- <span data-ttu-id="ff699-117">Binding di un certificato SSL alla configurazione di una porta e supporto di certificati client</span><span class="sxs-lookup"><span data-stu-id="ff699-117">Binding an SSL certificate to a port configuration and supporting client certificates.</span></span>  
  
- <span data-ttu-id="ff699-118">Eliminazione di un certificato SSL da un numero di porta</span><span class="sxs-lookup"><span data-stu-id="ff699-118">Deleting an SSL certificate from a port number.</span></span>  
  
 <span data-ttu-id="ff699-119">Si noti che la modifica dei certificati archiviati nel computer richiede privilegi di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="ff699-119">Note that modifying certificates stored on the computer requires administrative privileges.</span></span>  
  
### <a name="to-determine-how-ports-are-configured"></a><span data-ttu-id="ff699-120">Per determinare la configurazione delle porte</span><span class="sxs-lookup"><span data-stu-id="ff699-120">To determine how ports are configured</span></span>  
  
1. <span data-ttu-id="ff699-121">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oppure [!INCLUDE[wxp](../../../../includes/wxp-md.md)], usare lo strumento HttpCfg.exe per visualizzare la configurazione corrente delle porte, usando la **query** e **ssl** attiva, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ff699-121">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool to view the current port configuration, using the **query** and **ssl** switches, as shown in the following example.</span></span>  
  
    ```  
    httpcfg query ssl  
    ```  
  
2. <span data-ttu-id="ff699-122">In [!INCLUDE[wv](../../../../includes/wv-md.md)] usare lo strumento Netsh.exe per visualizzare la configurazione corrente delle porte, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ff699-122">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool to view the current port configuration, as shown in the following example.</span></span>  
  
    ```  
    netsh http show sslcert  
    ```  
  
### <a name="to-get-a-certificates-thumbprint"></a><span data-ttu-id="ff699-123">Per ottenere l'identificazione personale di un certificato</span><span class="sxs-lookup"><span data-stu-id="ff699-123">To get a certificate's thumbprint</span></span>  
  
1. <span data-ttu-id="ff699-124">Usare lo snap-in MMC Certificati per individuare un certificato X.509 che abbia come scopo previsto l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="ff699-124">Use the Certificates MMC snap-in to find an X.509 certificate that has an intended purpose of client authentication.</span></span> <span data-ttu-id="ff699-125">Per altre informazioni, vedere [Procedura: Visualizzare i certificati con lo Snap-in MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="ff699-125">For more information, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2. <span data-ttu-id="ff699-126">Accedere all'identificazione personale del certificato.</span><span class="sxs-lookup"><span data-stu-id="ff699-126">Access the certificate's thumbprint.</span></span> <span data-ttu-id="ff699-127">Per altre informazioni, vedere [Procedura: Recuperare l'identificazione personale di un certificato](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="ff699-127">For more information, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
3. <span data-ttu-id="ff699-128">Copiare l'identificazione personale del certificato in un editor di testo, ad esempio Blocco note.</span><span class="sxs-lookup"><span data-stu-id="ff699-128">Copy the thumbprint of the certificate into a text editor, such as Notepad.</span></span>  
  
4. <span data-ttu-id="ff699-129">Rimuovere tutti gli spazi tra i caratteri esadecimali.</span><span class="sxs-lookup"><span data-stu-id="ff699-129">Remove all spaces between the hexadecimal characters.</span></span> <span data-ttu-id="ff699-130">Per eseguire questa operazione, è possibile usare la funzionalità Trova e sostituisci dell'editor di testo per sostituire ogni spazio con un carattere null.</span><span class="sxs-lookup"><span data-stu-id="ff699-130">One way to accomplish this is to use the text editor's find-and-replace feature and replace each space with a null character.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number"></a><span data-ttu-id="ff699-131">Per associare un certificato SSL a un numero di porta</span><span class="sxs-lookup"><span data-stu-id="ff699-131">To bind an SSL certificate to a port number</span></span>  
  
1. <span data-ttu-id="ff699-132">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)] usare lo strumento HttpCfg.exe in modalità "impostazione" nell'archivio SSL (Secure Sockets Layer) per associare il certificato a un numero di porta.</span><span class="sxs-lookup"><span data-stu-id="ff699-132">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool in "set" mode on the Secure Sockets Layer (SSL) store to bind the certificate to a port number.</span></span> <span data-ttu-id="ff699-133">Lo strumento usa l'identificazione personale per identificare il certificato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ff699-133">The tool uses the thumbprint to identify the certificate, as shown in the following example.</span></span>  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - <span data-ttu-id="ff699-134">Il **-i** commutatore presenta la sintassi `IP`:`port` e indica allo strumento di impostare il certificato sulla porta 8012 del computer.</span><span class="sxs-lookup"><span data-stu-id="ff699-134">The **-i** switch has the syntax of `IP`:`port` and instructs the tool to set the certificate to port 8012 of the computer.</span></span> <span data-ttu-id="ff699-135">I quattro zero che precedono il numero possono essere anche sostituiti dall'indirizzo IP effettivo del computer.</span><span class="sxs-lookup"><span data-stu-id="ff699-135">Optionally, the four zeroes that precede the number can also be replaced by the actual IP address of the computer.</span></span>  
  
    - <span data-ttu-id="ff699-136">Il **-h** consente di specificare l'identificazione personale del certificato.</span><span class="sxs-lookup"><span data-stu-id="ff699-136">The **-h** switch specifies the thumbprint of the certificate.</span></span>  
  
2. <span data-ttu-id="ff699-137">In [!INCLUDE[wv](../../../../includes/wv-md.md)] usare lo strumento Netsh.exe come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ff699-137">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    - <span data-ttu-id="ff699-138">Il **certhash** parametro specifica l'identificazione personale del certificato.</span><span class="sxs-lookup"><span data-stu-id="ff699-138">The **certhash** parameter specifies the thumbprint of the certificate.</span></span>  
  
    - <span data-ttu-id="ff699-139">Il **ipport** parametro specifica l'indirizzo IP e la porta e funziona come il **-i** dello strumento Httpcfg.exe descritto.</span><span class="sxs-lookup"><span data-stu-id="ff699-139">The **ipport** parameter specifies the IP address and port, and functions just like the **-i** switch of the Httpcfg.exe tool described.</span></span>  
  
    - <span data-ttu-id="ff699-140">Il **appid** parametro è un GUID che può essere utilizzato per identificare l'applicazione proprietaria.</span><span class="sxs-lookup"><span data-stu-id="ff699-140">The **appid** parameter is a GUID that can be used to identify the owning application.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a><span data-ttu-id="ff699-141">Per associare un certificato SSL a un numero di porta e ai certificati client supportati</span><span class="sxs-lookup"><span data-stu-id="ff699-141">To bind an SSL certificate to a port number and support client certificates</span></span>  
  
1. <span data-ttu-id="ff699-142">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)] per supportare client che eseguono l'autenticazione con i certificati X.509 a livello di trasporto, eseguire la procedura precedente passando a HttpCfg.exe un parametro aggiuntivo della riga di comando, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ff699-142">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure but pass an additional command-line parameter to HttpCfg.exe, as shown in the following example.</span></span>  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     <span data-ttu-id="ff699-143">Il **-f** commutatore ha la sintassi di `n` dove n è un numero compreso tra 1 e 7.</span><span class="sxs-lookup"><span data-stu-id="ff699-143">The **-f** switch has the syntax of `n` where n is a number between 1 and 7.</span></span> <span data-ttu-id="ff699-144">Un valore di 2, come mostrato nell'esempio precedente, abilita certificati client a livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="ff699-144">A value of 2, as shown in the preceding example, enables client certificates at the transport layer.</span></span> <span data-ttu-id="ff699-145">Il valore 3 attiva i certificati client e associa tali certificati a un account Windows.</span><span class="sxs-lookup"><span data-stu-id="ff699-145">A value of 3 enables client certificates and maps those certificates to a Windows account.</span></span> <span data-ttu-id="ff699-146">Per il comportamento di altri valori, vedere la Guida di HttpCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="ff699-146">See HttpCfg.exe Help for the behavior of other values.</span></span>  
  
2. <span data-ttu-id="ff699-147">In [!INCLUDE[wv](../../../../includes/wv-md.md)] per supportare i client che eseguono l'autenticazione con i certificati X.509 a livello di trasporto, eseguire la procedura precedente, ma con un parametro aggiuntivo, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ff699-147">In [!INCLUDE[wv](../../../../includes/wv-md.md)], to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure, but with an additional parameter, as shown in the following example.</span></span>  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
### <a name="to-delete-an-ssl-certificate-from-a-port-number"></a><span data-ttu-id="ff699-148">Per eliminare un certificato SSL da un numero di porta</span><span class="sxs-lookup"><span data-stu-id="ff699-148">To delete an SSL certificate from a port number</span></span>  
  
1. <span data-ttu-id="ff699-149">Usare lo strumento HttpCfg.exe o Netsh.exe per visualizzare le porte e le identificazioni personali di tutti i binding nel computer.</span><span class="sxs-lookup"><span data-stu-id="ff699-149">Use the HttpCfg.exe or Netsh.exe tool to see the ports and thumbprints of all bindings on the computer.</span></span> <span data-ttu-id="ff699-150">Per stampare le informazioni su disco, usare il carattere di reindirizzamento ">", come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ff699-150">To print the information to disk, use the redirection character ">", as shown in the following example.</span></span>  
  
    ```  
    httpcfg query ssl>myMachinePorts.txt  
    ```  
  
2. <span data-ttu-id="ff699-151">Nella [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oppure [!INCLUDE[wxp](../../../../includes/wxp-md.md)], utilizzare lo strumento HttpCfg.exe con la **eliminare** e **ssl** parole chiave.</span><span class="sxs-lookup"><span data-stu-id="ff699-151">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool with the **delete** and **ssl** keywords.</span></span> <span data-ttu-id="ff699-152">Usare la **-i** per specificare le `IP`:`port` numero e il **-h** per specificare l'identificazione personale.</span><span class="sxs-lookup"><span data-stu-id="ff699-152">Use the **-i** switch to specify the `IP`:`port` number, and the **-h** switch to specify the thumbprint.</span></span>  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. <span data-ttu-id="ff699-153">In [!INCLUDE[wv](../../../../includes/wv-md.md)] usare lo strumento Netsh.exe come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ff699-153">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a><span data-ttu-id="ff699-154">Esempio</span><span class="sxs-lookup"><span data-stu-id="ff699-154">Example</span></span>  
 <span data-ttu-id="ff699-155">Nel codice seguente viene illustrato come creare un servizio indipendente usando la classe <xref:System.ServiceModel.WSHttpBinding> per la protezione del trasporto.</span><span class="sxs-lookup"><span data-stu-id="ff699-155">The following code shows how to create a self-hosted service using the <xref:System.ServiceModel.WSHttpBinding> class set to transport security.</span></span> <span data-ttu-id="ff699-156">Quando si crea un'applicazione, specificare il numero di porta nell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="ff699-156">When creating an application, specify the port number in the address.</span></span>  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="ff699-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff699-157">See also</span></span>

- [<span data-ttu-id="ff699-158">Sicurezza del trasporto HTTP</span><span class="sxs-lookup"><span data-stu-id="ff699-158">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
