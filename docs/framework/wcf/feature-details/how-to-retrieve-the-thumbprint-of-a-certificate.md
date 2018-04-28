---
title: "Procedura: recuperare l'identificazione personale di un certificato"
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates [WCF], retrieving thumbprint
ms.assetid: da3101aa-78cd-4c34-9652-d1f24777eeab
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0fe3635b73e17123e410f43efc8d382e0df85641
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-retrieve-the-thumbprint-of-a-certificate"></a><span data-ttu-id="e7584-102">Procedura: recuperare l'identificazione personale di un certificato</span><span class="sxs-lookup"><span data-stu-id="e7584-102">How to: Retrieve the Thumbprint of a Certificate</span></span>
<span data-ttu-id="e7584-103">Quando si scrive un'applicazione [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] che usa un certificato X.509 per l'autenticazione, è spesso necessario specificare le attestazioni trovate nel certificato.</span><span class="sxs-lookup"><span data-stu-id="e7584-103">When writing a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application that uses an X.509 certificate for authentication, it is often necessary to specify claims found in the certificate.</span></span> <span data-ttu-id="e7584-104">È, ad esempio, necessario fornire un'attestazione di identificazione personale in caso di utilizzo dell'enumerazione <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> nel metodo <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> .</span><span class="sxs-lookup"><span data-stu-id="e7584-104">For example, you must supply a thumbprint claim when using the <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> enumeration in the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method.</span></span> <span data-ttu-id="e7584-105">La ricerca del valore dell'attestazione richiede due passaggi.</span><span class="sxs-lookup"><span data-stu-id="e7584-105">Finding the claim value requires two steps.</span></span> <span data-ttu-id="e7584-106">Aprire innanzitutto lo snap-in MMC (Microsoft Management Console) per i certificati.</span><span class="sxs-lookup"><span data-stu-id="e7584-106">First, open the Microsoft Management Console (MMC) snap-in for certificates.</span></span> <span data-ttu-id="e7584-107">Per informazioni, vedere [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md). Quindi, come descritto qui, cercare un certificato appropriato e copiarne l'identificazione personale o gli altri valori di attestazione.</span><span class="sxs-lookup"><span data-stu-id="e7584-107">(See [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).) Second, as described here, find an appropriate certificate and copy its thumbprint (or other claim values).</span></span>  
  
 <span data-ttu-id="e7584-108">Se si sta usando un certificato per l'autenticazione del servizio, è importante notare il valore della colonna **Rilasciato a** (la prima colonna nella console).</span><span class="sxs-lookup"><span data-stu-id="e7584-108">If you are using a certificate for service authentication, it is important to note the value of the **Issued To** column (the first column in the console).</span></span> <span data-ttu-id="e7584-109">Quando si usa SSL (Secure Sockets Layer) come protezione del trasporto, una dei primi controlli eseguiti consiste nel confrontare l'URI (Uniform Resource Identifier) dell'indirizzo di base di un servizio con il valore **Rilasciato a** .</span><span class="sxs-lookup"><span data-stu-id="e7584-109">When using Secure Sockets Layer (SSL) as a transport security, one of the first checks done is to compare the base address Uniform Resource Identifier (URI) of a service to the **Issued To** value.</span></span> <span data-ttu-id="e7584-110">I valori devono corrispondere o il processo di autenticazione viene interrotto.</span><span class="sxs-lookup"><span data-stu-id="e7584-110">The values must match or the authentication process is halted.</span></span>  
  
 <span data-ttu-id="e7584-111">È inoltre possibile usare lo strumento Makecert.exe di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] SDK per creare certificati temporanei da usare solo durante lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="e7584-111">You can also use the Makecert.exe tool from the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] SDK to create temporary certificates for use only during development.</span></span> <span data-ttu-id="e7584-112">Per impostazione predefinita, tale certificato non viene tuttavia emesso da un'autorità di certificazione e non può essere usato a scopo di produzione.</span><span class="sxs-lookup"><span data-stu-id="e7584-112">By default, however, such a certificate is not issued by a certification authority, and is unusable for production purposes.</span></span> <span data-ttu-id="e7584-113">Per altre informazioni, vedere [procedura: creazione di certificati temporanei da usare durante lo sviluppo](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md).</span><span class="sxs-lookup"><span data-stu-id="e7584-113">For more information, see [How to: Create Temporary Certificates for Use During Development](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md).</span></span>  
  
### <a name="to-retrieve-a-certificates-thumbprint"></a><span data-ttu-id="e7584-114">Per recuperare l'identificazione personale di un certificato</span><span class="sxs-lookup"><span data-stu-id="e7584-114">To retrieve a certificate's thumbprint</span></span>  
  
1.  <span data-ttu-id="e7584-115">Aprire lo snap-in MMC (Microsoft Management Console) per i certificati.</span><span class="sxs-lookup"><span data-stu-id="e7584-115">Open the Microsoft Management Console (MMC) snap-in for certificates.</span></span> <span data-ttu-id="e7584-116">Per informazioni, vedere [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="e7584-116">(See [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).)</span></span>  
  
2.  <span data-ttu-id="e7584-117">Nel riquadro sinistro della finestra **Radice console** fare clic su **Certificati (computer locale)**.</span><span class="sxs-lookup"><span data-stu-id="e7584-117">In the **Console Root** window's left pane, click **Certificates (Local Computer)**.</span></span>  
  
3.  <span data-ttu-id="e7584-118">Fare clic sulla cartella **Personale** per espanderla.</span><span class="sxs-lookup"><span data-stu-id="e7584-118">Click the **Personal** folder to expand it.</span></span>  
  
4.  <span data-ttu-id="e7584-119">Fare clic sulla cartella **Certificati** per espanderla.</span><span class="sxs-lookup"><span data-stu-id="e7584-119">Click the **Certificates** folder to expand it.</span></span>  
  
5.  <span data-ttu-id="e7584-120">Nell'elenco dei certificati notare l'intestazione **Scopi designati** .</span><span class="sxs-lookup"><span data-stu-id="e7584-120">In the list of certificates, note the **Intended Purposes** heading.</span></span> <span data-ttu-id="e7584-121">Cercare un certificato che riporti **Autenticazione client** come scopo designato.</span><span class="sxs-lookup"><span data-stu-id="e7584-121">Find a certificate that lists **Client Authentication** as an intended purpose.</span></span>  
  
6.  <span data-ttu-id="e7584-122">Fare doppio clic sul certificato.</span><span class="sxs-lookup"><span data-stu-id="e7584-122">Double-click the certificate.</span></span>  
  
7.  <span data-ttu-id="e7584-123">Nella finestra di dialogo **Certificati** fare clic sulla scheda **Dettagli** .</span><span class="sxs-lookup"><span data-stu-id="e7584-123">In the **Certificate** dialog box, click the **Details** tab.</span></span>  
  
8.  <span data-ttu-id="e7584-124">Scorrere l'elenco di campi e fare clic su **Identificazione personale**.</span><span class="sxs-lookup"><span data-stu-id="e7584-124">Scroll through the list of fields and click **Thumbprint**.</span></span>  
  
9. <span data-ttu-id="e7584-125">Copiare i caratteri esadecimali dalla casella.</span><span class="sxs-lookup"><span data-stu-id="e7584-125">Copy the hexadecimal characters from the box.</span></span> <span data-ttu-id="e7584-126">Se questa identificazione personale viene usata nel codice per `X509FindType`, rimuovere gli spazi tra i numeri esadecimali.</span><span class="sxs-lookup"><span data-stu-id="e7584-126">If this thumbprint is used in code for the `X509FindType`, remove the spaces between the hexadecimal numbers.</span></span> <span data-ttu-id="e7584-127">Ad esempio, l'identificazione personale "a9 09 50 2d d8 2a e4 14 33 e6 f8 38 86 b0 0d che 42 77 a3 2a 7b" nel codice deve essere specificata come "a909502dd82ae41433e6f83886b00d4277a32a7b".</span><span class="sxs-lookup"><span data-stu-id="e7584-127">For example, the thumbprint "a9 09 50 2d d8 2a e4 14 33 e6 f8 38 86 b0 0d 42 77 a3 2a 7b" should be specified as "a909502dd82ae41433e6f83886b00d4277a32a7b" in code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7584-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7584-128">See Also</span></span>  
 <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>  
 [<span data-ttu-id="e7584-129">Procedura: Configurare una porta con un certificato SSL</span><span class="sxs-lookup"><span data-stu-id="e7584-129">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 [<span data-ttu-id="e7584-130">Procedura: Visualizzare certificati con lo snap-in MMC</span><span class="sxs-lookup"><span data-stu-id="e7584-130">How to: View Certificates with the MMC Snap-in</span></span>](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)  
 [<span data-ttu-id="e7584-131">Procedura: Creare certificati temporanei da usare durante lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="e7584-131">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
