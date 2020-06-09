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
ms.openlocfilehash: e4f1aae021c4be49847b3b6dcd14b5a0a237c899
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597046"
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="319ef-102">Procedura: rendere accessibili a WCF i certificati X.509</span><span class="sxs-lookup"><span data-stu-id="319ef-102">How to: Make X.509 Certificates Accessible to WCF</span></span>
<span data-ttu-id="319ef-103">Per rendere accessibile un certificato X. 509 a Windows Communication Foundation (WCF), il codice dell'applicazione deve specificare il nome e il percorso dell'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="319ef-103">To make an X.509 certificate accessible to Windows Communication Foundation (WCF), application code must specify the certificate store name and location.</span></span> <span data-ttu-id="319ef-104">In alcuni casi l'identità del processo deve avere accesso al file contenente la chiave privata associata al certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="319ef-104">In certain circumstances, the process identity must have access to the file that contains the private key associated with the X.509 certificate.</span></span> <span data-ttu-id="319ef-105">Per ottenere la chiave privata associata a un certificato X. 509 in un archivio certificati, WCF deve disporre delle autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="319ef-105">To obtain the private key associated with an X.509 certificate in a certificate store, WCF must have permission to do so.</span></span> <span data-ttu-id="319ef-106">Per impostazione predefinita solo il proprietario e l'account di sistema possono accedere alla chiave privata di un certificato.</span><span class="sxs-lookup"><span data-stu-id="319ef-106">By default, only the owner and the System account can access the private key of a certificate.</span></span>  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="319ef-107">Per rendere accessibili a WCF i certificati X.509</span><span class="sxs-lookup"><span data-stu-id="319ef-107">To make X.509 certificates accessible to WCF</span></span>  
  
1. <span data-ttu-id="319ef-108">Assegnare all'account con cui WCF esegue l'accesso in lettura al file che contiene la chiave privata associata al certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="319ef-108">Give the account under which WCF is running read access to the file that contains the private key associated with the X.509 certificate.</span></span>  
  
    1. <span data-ttu-id="319ef-109">Determinare se WCF richiede l'accesso in lettura alla chiave privata per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="319ef-109">Determine whether WCF requires read access to the private key for the X.509 certificate.</span></span>  
  
         <span data-ttu-id="319ef-110">Nella tabella seguente viene indicato dettagliatamente se una chiave privata deve essere disponibile in caso di utilizzo di un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="319ef-110">The following table details whether a private key must be available when using an X.509 certificate.</span></span>  
  
        |<span data-ttu-id="319ef-111">Utilizzo di certificati X.509</span><span class="sxs-lookup"><span data-stu-id="319ef-111">X.509 certificate use</span></span>|<span data-ttu-id="319ef-112">Chiave privata</span><span class="sxs-lookup"><span data-stu-id="319ef-112">Private key</span></span>|  
        |---------------------------|-----------------|  
        |<span data-ttu-id="319ef-113">Firma digitale di un messaggio SOAP in uscita.</span><span class="sxs-lookup"><span data-stu-id="319ef-113">Digitally signing an outbound SOAP message.</span></span>|<span data-ttu-id="319ef-114">Sì</span><span class="sxs-lookup"><span data-stu-id="319ef-114">Yes</span></span>|  
        |<span data-ttu-id="319ef-115">Verifica della firma di un messaggio SOAP in arrivo.</span><span class="sxs-lookup"><span data-stu-id="319ef-115">Verifying the signature of an inbound SOAP message.</span></span>|<span data-ttu-id="319ef-116">No</span><span class="sxs-lookup"><span data-stu-id="319ef-116">No</span></span>|  
        |<span data-ttu-id="319ef-117">Crittografia di un messaggio SOAP in uscita.</span><span class="sxs-lookup"><span data-stu-id="319ef-117">Encrypting an outbound SOAP message.</span></span>|<span data-ttu-id="319ef-118">No</span><span class="sxs-lookup"><span data-stu-id="319ef-118">No</span></span>|  
        |<span data-ttu-id="319ef-119">Decrittografia di un messaggio SOAP in arrivo.</span><span class="sxs-lookup"><span data-stu-id="319ef-119">Decrypting an inbound SOAP message.</span></span>|<span data-ttu-id="319ef-120">Sì</span><span class="sxs-lookup"><span data-stu-id="319ef-120">Yes</span></span>|  
  
    2. <span data-ttu-id="319ef-121">Determinare il percorso e il nome dell'archivio certificati in cui è archiviato il certificato.</span><span class="sxs-lookup"><span data-stu-id="319ef-121">Determine the certificate store location and name in which the certificate is stored.</span></span>  
  
         <span data-ttu-id="319ef-122">L'archivio certificati nel quale il certificato è archiviato è specificato nel codice dell'applicazione o nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="319ef-122">The certificate store in which the certificate is stored is specified either in application code or in configuration.</span></span> <span data-ttu-id="319ef-123">Nel codice seguente, ad esempio, viene specificato che il certificato si trova nell'archivio certificati `CurrentUser` denominato `My`.</span><span class="sxs-lookup"><span data-stu-id="319ef-123">For example, the following example specifies that the certificate is located in the `CurrentUser` certificate store named `My`.</span></span>  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3. <span data-ttu-id="319ef-124">Determinare dove si trova la chiave privata per il certificato nel computer utilizzando lo strumento [FindPrivateKey](../samples/findprivatekey.md) .</span><span class="sxs-lookup"><span data-stu-id="319ef-124">Determine where the private key for the certificate is located on the computer by using the [FindPrivateKey](../samples/findprivatekey.md) tool.</span></span>  
  
         <span data-ttu-id="319ef-125">Lo strumento [FindPrivateKey](../samples/findprivatekey.md) richiede il nome dell'archivio certificati, il percorso dell'archivio certificati e un elemento che identifica in modo univoco il certificato.</span><span class="sxs-lookup"><span data-stu-id="319ef-125">The [FindPrivateKey](../samples/findprivatekey.md) tool requires the certificate store name, certificate store location, and something that uniquely identifies the certificate.</span></span> <span data-ttu-id="319ef-126">Lo strumento accetta il nome del soggetto del certificato o l'identificazione digitale come identificatore univoco.</span><span class="sxs-lookup"><span data-stu-id="319ef-126">The tool accepts either the certificate's subject name or its thumbprint as a unique identifier.</span></span> <span data-ttu-id="319ef-127">Per altre informazioni su come determinare l'identificazione personale per un certificato, vedere [procedura: recuperare l'identificazione personale di un certificato](how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="319ef-127">For more information about how to determine the thumbprint for a certificate, see [How to: Retrieve the Thumbprint of a Certificate](how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
         <span data-ttu-id="319ef-128">Nell'esempio di codice seguente viene usato lo strumento [FindPrivateKey](../samples/findprivatekey.md) per determinare il percorso della chiave privata per un certificato nell' `My` archivio in `CurrentUser` con un'identificazione personale di `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d` .</span><span class="sxs-lookup"><span data-stu-id="319ef-128">The following code example uses the [FindPrivateKey](../samples/findprivatekey.md) tool to determine the location of the private key for a certificate in the `My` store in `CurrentUser` with a thumbprint of `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span></span>  
  
        ```console
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4. <span data-ttu-id="319ef-129">Determinare l'account con cui viene eseguito WCF.</span><span class="sxs-lookup"><span data-stu-id="319ef-129">Determine the account that WCF is running under.</span></span>  
  
         <span data-ttu-id="319ef-130">La tabella seguente illustra in dettaglio l'account con cui viene eseguito WCF per uno scenario specifico.</span><span class="sxs-lookup"><span data-stu-id="319ef-130">The following table details the account under which WCF is running for a given scenario.</span></span>  
  
        |<span data-ttu-id="319ef-131">Scenario</span><span class="sxs-lookup"><span data-stu-id="319ef-131">Scenario</span></span>|<span data-ttu-id="319ef-132">Identità del processo</span><span class="sxs-lookup"><span data-stu-id="319ef-132">Process identity</span></span>|  
        |--------------|----------------------|  
        |<span data-ttu-id="319ef-133">Client (console o applicazione Windows Form).</span><span class="sxs-lookup"><span data-stu-id="319ef-133">Client (console or WinForms application).</span></span>|<span data-ttu-id="319ef-134">Utente attualmente connesso.</span><span class="sxs-lookup"><span data-stu-id="319ef-134">Currently logged in user.</span></span>|  
        |<span data-ttu-id="319ef-135">Servizio indipendente.</span><span class="sxs-lookup"><span data-stu-id="319ef-135">Service that is self-hosted.</span></span>|<span data-ttu-id="319ef-136">Utente attualmente connesso.</span><span class="sxs-lookup"><span data-stu-id="319ef-136">Currently logged in user.</span></span>|  
        |<span data-ttu-id="319ef-137">Servizio ospitato in IIS 6,0 (Windows Server 2003) o IIS 7,0 (Windows Vista).</span><span class="sxs-lookup"><span data-stu-id="319ef-137">Service that is hosted in IIS 6.0 (Windows Server 2003) or IIS 7.0 (Windows Vista).</span></span>|<span data-ttu-id="319ef-138">NETWORK SERVICE</span><span class="sxs-lookup"><span data-stu-id="319ef-138">NETWORK SERVICE</span></span>|  
        |<span data-ttu-id="319ef-139">Servizio ospitato in IIS 5. X (Windows XP).</span><span class="sxs-lookup"><span data-stu-id="319ef-139">Service that is hosted in IIS 5.X (Windows XP).</span></span>|<span data-ttu-id="319ef-140">Controllato dall'elemento `<processModel>` nel file Machine.config.</span><span class="sxs-lookup"><span data-stu-id="319ef-140">Controlled by the `<processModel>` element in the Machine.config file.</span></span> <span data-ttu-id="319ef-141">L'account predefinito è ASPNET.</span><span class="sxs-lookup"><span data-stu-id="319ef-141">The default account is ASPNET.</span></span>|  
  
    5. <span data-ttu-id="319ef-142">Concedere l'accesso in lettura al file che contiene la chiave privata all'account con cui viene eseguito WCF, utilizzando uno strumento come icacls. exe.</span><span class="sxs-lookup"><span data-stu-id="319ef-142">Grant read access to the file that contains the private key to the account that WCF is running under, using a tool such as icacls.exe.</span></span>  
  
         <span data-ttu-id="319ef-143">Nell'esempio di codice seguente viene modificato l'elenco di controllo di accesso discrezionale (DACL) per il file specificato per concedere all'account del servizio di rete l'accesso in lettura (: R) al file.</span><span class="sxs-lookup"><span data-stu-id="319ef-143">The following code example edits the discretionary access control list (DACL) for the specified file to grant the NETWORK SERVICE account read (:R) access to the file.</span></span>  
  
        ```console
        icacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /grant "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="319ef-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="319ef-144">See also</span></span>

- [<span data-ttu-id="319ef-145">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="319ef-145">FindPrivateKey</span></span>](../samples/findprivatekey.md)
- [<span data-ttu-id="319ef-146">Procedura: recuperare l'identificazione personale di un certificato</span><span class="sxs-lookup"><span data-stu-id="319ef-146">How to: Retrieve the Thumbprint of a Certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
- [<span data-ttu-id="319ef-147">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="319ef-147">Working with Certificates</span></span>](working-with-certificates.md)
