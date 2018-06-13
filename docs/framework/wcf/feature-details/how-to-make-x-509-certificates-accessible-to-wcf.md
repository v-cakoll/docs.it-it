---
title: 'Procedura: rendere accessibili a WCF i certificati X.509'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- X.509 certificates [WCF]
- certificates [WCF], making X.509 certificates accessible to WCF
- X.509 certificates [WCF], making accessible to WCF
ms.assetid: a54e407c-c2b5-4319-a648-60e43413664b
ms.openlocfilehash: cd13eae0a72ceaf5abfb93dfe84a53cfc3c8dec4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493706"
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="391e3-102">Procedura: rendere accessibili a WCF i certificati X.509</span><span class="sxs-lookup"><span data-stu-id="391e3-102">How to: Make X.509 Certificates Accessible to WCF</span></span>
<span data-ttu-id="391e3-103">Per rendere accessibile da Windows Communication Foundation (WCF) un certificato X.509, il codice dell'applicazione deve specificare il nome dell'archivio certificati e il percorso.</span><span class="sxs-lookup"><span data-stu-id="391e3-103">To make an X.509 certificate accessible to Windows Communication Foundation (WCF), application code must specify the certificate store name and location.</span></span> <span data-ttu-id="391e3-104">In alcuni casi l'identità del processo deve avere accesso al file contenente la chiave privata associata al certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="391e3-104">In certain circumstances, the process identity must have access to the file that contains the private key associated with the X.509 certificate.</span></span> <span data-ttu-id="391e3-105">Per ottenere la chiave privata associata a un certificato X.509 in un archivio certificati, WCF deve disporre dell'autorizzazione per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="391e3-105">To obtain the private key associated with an X.509 certificate in a certificate store, WCF must have permission to do so.</span></span> <span data-ttu-id="391e3-106">Per impostazione predefinita solo il proprietario e l'account di sistema possono accedere alla chiave privata di un certificato.</span><span class="sxs-lookup"><span data-stu-id="391e3-106">By default, only the owner and the System account can access the private key of a certificate.</span></span>  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="391e3-107">Per rendere accessibili a WCF i certificati X.509</span><span class="sxs-lookup"><span data-stu-id="391e3-107">To make X.509 certificates accessible to WCF</span></span>  
  
1.  <span data-ttu-id="391e3-108">Assegnare all'account con cui WCF viene eseguito l'accesso in lettura al file che contiene la chiave privata associata al certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="391e3-108">Give the account under which WCF is running read access to the file that contains the private key associated with the X.509 certificate.</span></span>  
  
    1.  <span data-ttu-id="391e3-109">Stabilire se WCF richiede l'accesso in lettura alla chiave privata del certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="391e3-109">Determine whether WCF requires read access to the private key for the X.509 certificate.</span></span>  
  
         <span data-ttu-id="391e3-110">Nella tabella seguente viene indicato dettagliatamente se una chiave privata deve essere disponibile in caso di utilizzo di un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="391e3-110">The following table details whether a private key must be available when using an X.509 certificate.</span></span>  
  
        |<span data-ttu-id="391e3-111">Utilizzo di certificati X.509</span><span class="sxs-lookup"><span data-stu-id="391e3-111">X.509 certificate use</span></span>|<span data-ttu-id="391e3-112">Chiave privata</span><span class="sxs-lookup"><span data-stu-id="391e3-112">Private key</span></span>|  
        |---------------------------|-----------------|  
        |<span data-ttu-id="391e3-113">Firma digitale di un messaggio SOAP in uscita.</span><span class="sxs-lookup"><span data-stu-id="391e3-113">Digitally signing an outbound SOAP message.</span></span>|<span data-ttu-id="391e3-114">Yes</span><span class="sxs-lookup"><span data-stu-id="391e3-114">Yes</span></span>|  
        |<span data-ttu-id="391e3-115">Verifica della firma di un messaggio SOAP in arrivo.</span><span class="sxs-lookup"><span data-stu-id="391e3-115">Verifying the signature of an inbound SOAP message.</span></span>|<span data-ttu-id="391e3-116">No</span><span class="sxs-lookup"><span data-stu-id="391e3-116">No</span></span>|  
        |<span data-ttu-id="391e3-117">Crittografia di un messaggio SOAP in uscita.</span><span class="sxs-lookup"><span data-stu-id="391e3-117">Encrypting an outbound SOAP message.</span></span>|<span data-ttu-id="391e3-118">No</span><span class="sxs-lookup"><span data-stu-id="391e3-118">No</span></span>|  
        |<span data-ttu-id="391e3-119">Decrittografia di un messaggio SOAP in arrivo.</span><span class="sxs-lookup"><span data-stu-id="391e3-119">Decrypting an inbound SOAP message.</span></span>|<span data-ttu-id="391e3-120">Yes</span><span class="sxs-lookup"><span data-stu-id="391e3-120">Yes</span></span>|  
  
    2.  <span data-ttu-id="391e3-121">Determinare il percorso e il nome dell'archivio certificati in cui è archiviato il certificato.</span><span class="sxs-lookup"><span data-stu-id="391e3-121">Determine the certificate store location and name in which the certificate is stored.</span></span>  
  
         <span data-ttu-id="391e3-122">L'archivio certificati nel quale il certificato è archiviato è specificato nel codice dell'applicazione o nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="391e3-122">The certificate store in which the certificate is stored is specified either in application code or in configuration.</span></span> <span data-ttu-id="391e3-123">Nel codice seguente, ad esempio, viene specificato che il certificato si trova nell'archivio certificati `CurrentUser` denominato `My`.</span><span class="sxs-lookup"><span data-stu-id="391e3-123">For example, the following example specifies that the certificate is located in the `CurrentUser` certificate store named `My`.</span></span>  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3.  <span data-ttu-id="391e3-124">Determinare dove la chiave privata per il certificato si trova nel computer utilizzando il [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) strumento.</span><span class="sxs-lookup"><span data-stu-id="391e3-124">Determine where the private key for the certificate is located on the computer by using the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool.</span></span>  
  
         <span data-ttu-id="391e3-125">Il [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) strumento richiede il nome dell'archivio certificati, percorso dell'archivio certificati e un valore che identifica in modo univoco il certificato.</span><span class="sxs-lookup"><span data-stu-id="391e3-125">The [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool requires the certificate store name, certificate store location, and something that uniquely identifies the certificate.</span></span> <span data-ttu-id="391e3-126">Lo strumento accetta il nome del soggetto del certificato o l'identificazione digitale come identificatore univoco.</span><span class="sxs-lookup"><span data-stu-id="391e3-126">The tool accepts either the certificate's subject name or its thumbprint as a unique identifier.</span></span> <span data-ttu-id="391e3-127">Per ulteriori informazioni su come determinare l'identificazione personale per un certificato, vedere [procedura: recuperare l'identificazione personale del certificato](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="391e3-127">For more information about how to determine the thumbprint for a certificate, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
         <span data-ttu-id="391e3-128">Nell'esempio di codice viene illustrato come utilizzare il [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) strumento per determinare la posizione della chiave privata di un certificato nella `My` archiviare in `CurrentUser` con un'identificazione digitale di `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span><span class="sxs-lookup"><span data-stu-id="391e3-128">The following code example uses the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool to determine the location of the private key for a certificate in the `My` store in `CurrentUser` with a thumbprint of `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span></span>  
  
        ```  
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4.  <span data-ttu-id="391e3-129">Determinare l'account cui WCF è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="391e3-129">Determine the account that WCF is running under.</span></span>  
  
         <span data-ttu-id="391e3-130">Nella tabella seguente illustra in dettaglio l'account con cui WCF è in esecuzione per un determinato scenario.</span><span class="sxs-lookup"><span data-stu-id="391e3-130">The following table details the account under which WCF is running for a given scenario.</span></span>  
  
        |<span data-ttu-id="391e3-131">Scenario</span><span class="sxs-lookup"><span data-stu-id="391e3-131">Scenario</span></span>|<span data-ttu-id="391e3-132">Identità del processo</span><span class="sxs-lookup"><span data-stu-id="391e3-132">Process identity</span></span>|  
        |--------------|----------------------|  
        |<span data-ttu-id="391e3-133">Client (console o applicazione Windows Form).</span><span class="sxs-lookup"><span data-stu-id="391e3-133">Client (console or WinForms application).</span></span>|<span data-ttu-id="391e3-134">Utente attualmente connesso.</span><span class="sxs-lookup"><span data-stu-id="391e3-134">Currently logged in user.</span></span>|  
        |<span data-ttu-id="391e3-135">Servizio indipendente.</span><span class="sxs-lookup"><span data-stu-id="391e3-135">Service that is self-hosted.</span></span>|<span data-ttu-id="391e3-136">Utente attualmente connesso.</span><span class="sxs-lookup"><span data-stu-id="391e3-136">Currently logged in user.</span></span>|  
        |<span data-ttu-id="391e3-137">Servizio ospitato in IIS 6.0 ([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) o IIS 7.0 ([!INCLUDE[wv](../../../../includes/wv-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="391e3-137">Service that is hosted in IIS 6.0 ([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) or IIS 7.0 ([!INCLUDE[wv](../../../../includes/wv-md.md)]).</span></span>|<span data-ttu-id="391e3-138">SERVIZIO DI RETE</span><span class="sxs-lookup"><span data-stu-id="391e3-138">NETWORK SERVICE</span></span>|  
        |<span data-ttu-id="391e3-139">Servizio ospitato in IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="391e3-139">Service that is hosted in IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]).</span></span>|<span data-ttu-id="391e3-140">Controllato dall'elemento `<processModel>` nel file Machine.config.</span><span class="sxs-lookup"><span data-stu-id="391e3-140">Controlled by the `<processModel>` element in the Machine.config file.</span></span> <span data-ttu-id="391e3-141">L'account predefinito è ASPNET.</span><span class="sxs-lookup"><span data-stu-id="391e3-141">The default account is ASPNET.</span></span>|  
  
    5.  <span data-ttu-id="391e3-142">Concedere l'accesso in lettura al file che contiene la chiave privata per l'account di cui WCF è in esecuzione, mediante uno strumento quale cacls.exe.</span><span class="sxs-lookup"><span data-stu-id="391e3-142">Grant read access to the file that contains the private key to the account that WCF is running under, using a tool such as cacls.exe.</span></span>  
  
         <span data-ttu-id="391e3-143">Nell'esempio di codice seguente viene modificato (/E) l'elenco di controllo di accesso (ACL) per il file specificato per concedere (/G) all'account NETWORK SERVICE l'accesso in lettura (:R) al file.</span><span class="sxs-lookup"><span data-stu-id="391e3-143">The following code example edits (/E) the access control list (ACL) for the specified file to grant (/G) the NETWORK SERVICE account read (:R) access to the file.</span></span>  
  
        ```  
        cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="391e3-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="391e3-144">See Also</span></span>  
 [<span data-ttu-id="391e3-145">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="391e3-145">FindPrivateKey</span></span>](../../../../docs/framework/wcf/samples/findprivatekey.md)  
 [<span data-ttu-id="391e3-146">Procedura: Recuperare l'identificazione personale di un certificato</span><span class="sxs-lookup"><span data-stu-id="391e3-146">How to: Retrieve the Thumbprint of a Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)  
 [<span data-ttu-id="391e3-147">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="391e3-147">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
