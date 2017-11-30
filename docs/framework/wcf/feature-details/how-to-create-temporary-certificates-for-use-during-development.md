---
title: 'Procedura: creare certificati temporanei da usare durante lo sviluppo'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a1b386906c1d493a23d8a58f3540758d3ae0d26e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a><span data-ttu-id="2c40e-102">Procedura: creare certificati temporanei da usare durante lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="2c40e-102">How to: Create Temporary Certificates for Use During Development</span></span>
<span data-ttu-id="2c40e-103">Quando si sviluppa un servizio o un client protetto usando [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], è spesso necessario fornire un certificato X.509 da usare come credenziale.</span><span class="sxs-lookup"><span data-stu-id="2c40e-103">When developing a secure service or client using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], it is often necessary to supply an X.509 certificate to be used as a credential.</span></span> <span data-ttu-id="2c40e-104">Il certificato in genere fa parte di una catena di certificati con autorità radice contenuta nell'archivio Autorità di certificazione radice attendibile del computer.</span><span class="sxs-lookup"><span data-stu-id="2c40e-104">The certificate typically is part of a chain of certificates with a root authority found in the Trusted Root Certification Authorities store of the computer.</span></span> <span data-ttu-id="2c40e-105">La catena di certificati consente di definire l'ambito per un set di certificati quando in genere l'autorità radice è dell'organizzazione o dell'unità aziendale.</span><span class="sxs-lookup"><span data-stu-id="2c40e-105">Having a certificate chain enables you to scope a set of certificates where typically the root authority is from your organization or business unit.</span></span> <span data-ttu-id="2c40e-106">Per emulare questo comportamento in fase di sviluppo, è possibile creare due certificati per soddisfare i requisiti di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2c40e-106">To emulate this at development time, you can create two certificates to satisfy the security requirements.</span></span> <span data-ttu-id="2c40e-107">Il primo è un certificato autofirmato che si trova nell'archivio Autorità di certificazione radice attendibile, mentre il secondo certificato viene creato dal primo e si trova nell'archivio Personale del computer locale o dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="2c40e-107">The first is a self-signed certificate that is placed in the Trusted Root Certification Authorities store, and the second certificate is created from the first and is placed in either the Personal store of the Local Machine location, or the Personal store of the Current User location.</span></span> <span data-ttu-id="2c40e-108">Questo argomento descrive i passaggi per la creazione di questi due certificati mediante lo [strumento di creazione certificati (MakeCert.exe)](http://go.microsoft.com/fwlink/?LinkId=248185), fornito da [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="2c40e-108">This topic walks through the steps to create these two certificates using the [Certificate Creation Tool (MakeCert.exe)](http://go.microsoft.com/fwlink/?LinkId=248185), which is provided by the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2c40e-109">I certificati generati dallo strumento di creazione certificati sono forniti solo a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="2c40e-109">The certificates the Certification Creation tool generates are provided for testing purposes only.</span></span> <span data-ttu-id="2c40e-110">Quando si distribuisce un servizio o un client, assicurarsi di usare un certificato appropriato rilasciato da un'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="2c40e-110">When deploying a service or client, be sure to use an appropriate certificate provided by a certification authority.</span></span> <span data-ttu-id="2c40e-111">Tale certificato può essere fornito da un server dei certificati di [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] dell'organizzazione o da terze parti.</span><span class="sxs-lookup"><span data-stu-id="2c40e-111">This could either be from a [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] certificate server in your organization or a third party.</span></span>  
>   
>  <span data-ttu-id="2c40e-112">Per impostazione predefinita, il [Makecert.exe (strumento di creazione certificati)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) crea certificati la cui autorità radice è denominata "agenzia radice**."**</span><span class="sxs-lookup"><span data-stu-id="2c40e-112">By default, the [Makecert.exe (Certificate Creation Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) creates certificates whose root authority is called "Root Agency**."**</span></span> <span data-ttu-id="2c40e-113">Poiché l'Agenzia radice non è inclusa nell'archivio Autorità di certificazione radice attendibili, i certificati non sono protetti.</span><span class="sxs-lookup"><span data-stu-id="2c40e-113">Because the "Root Agency" is not in the Trusted Root Certification Authorities store, this makes these certificates insecure.</span></span> <span data-ttu-id="2c40e-114">La creazione di un certificato autofirmato posizionato nell'archivio di Autorità di certificazione radice attendibili consente di creare un ambiente di sviluppo che simula in modo più accurato l'ambiente di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2c40e-114">Creating a self-signed certificate that is placed in the Trusted Root Certification Authorities store enables you to create a development environment that more closely simulates your deployment environment.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="2c40e-115"> lla creazione e sull'uso di certificati, vedere [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="2c40e-115"> creating and using certificates, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="2c40e-116"> ll'uso di un certificato come credenziale, vedere [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="2c40e-116"> using a certificate as a credential, see [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span></span> <span data-ttu-id="2c40e-117">Per un'esercitazione sull'uso della tecnologia Microsoft Authenticode, vedere [Panoramica di Authenticode ed esercitazioni](http://go.microsoft.com/fwlink/?LinkId=88919).</span><span class="sxs-lookup"><span data-stu-id="2c40e-117">For a tutorial about using Microsoft Authenticode technology, see [Authenticode Overviews and Tutorials](http://go.microsoft.com/fwlink/?LinkId=88919).</span></span>  
  
### <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a><span data-ttu-id="2c40e-118">Per creare un certificato dell'autorità radice autofirmato ed esportare la chiave privata</span><span class="sxs-lookup"><span data-stu-id="2c40e-118">To create a self-signed root authority certificate and export the private key</span></span>  
  
1.  <span data-ttu-id="2c40e-119">Usare lo strumento MakeCert.exe con le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c40e-119">Use the MakeCert.exe tool with the following switches:</span></span>  
  
    1.  <span data-ttu-id="2c40e-120">`-n` `subjectName`.</span><span class="sxs-lookup"><span data-stu-id="2c40e-120">`-n` `subjectName`.</span></span> <span data-ttu-id="2c40e-121">Specifica il nome del soggetto.</span><span class="sxs-lookup"><span data-stu-id="2c40e-121">Specifies the subject name.</span></span> <span data-ttu-id="2c40e-122">La convenzione prevede l'inserimento del prefisso "CN = " per "Nome comune" prima del nome del soggetto.</span><span class="sxs-lookup"><span data-stu-id="2c40e-122">The convention is to prefix the subject name with "CN = " for "Common Name".</span></span>  
  
    2.  <span data-ttu-id="2c40e-123">`-r`.</span><span class="sxs-lookup"><span data-stu-id="2c40e-123">`-r`.</span></span> <span data-ttu-id="2c40e-124">Specifica che il certificato sarà autofirmato.</span><span class="sxs-lookup"><span data-stu-id="2c40e-124">Specifies that the certificate will be self-signed.</span></span>  
  
    3.  <span data-ttu-id="2c40e-125">`-sv` `privateKeyFile`.</span><span class="sxs-lookup"><span data-stu-id="2c40e-125">`-sv` `privateKeyFile`.</span></span> <span data-ttu-id="2c40e-126">Specifica il file che contiene il contenitore della chiave privata.</span><span class="sxs-lookup"><span data-stu-id="2c40e-126">Specifies the file that contains the private key container.</span></span>  
  
     <span data-ttu-id="2c40e-127">Ad esempio, nel comando seguente viene creato un certificato autofirmato con il nome del soggetto "CN=TempCA".</span><span class="sxs-lookup"><span data-stu-id="2c40e-127">For example, the following command creates a self-signed certificate with a subject name of "CN=TempCA."</span></span>  
  
    ```  
    makecert -n "CN=TempCA" -r -sv TempCA.pvk TempCA.cer  
    ```  
  
     <span data-ttu-id="2c40e-128">Verrà richiesto di fornire una password per proteggere la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="2c40e-128">You will be prompted to provide a password to protect the private key.</span></span> <span data-ttu-id="2c40e-129">Questa password è richiesta quando si crea un certificato firmato mediante questo certificato radice.</span><span class="sxs-lookup"><span data-stu-id="2c40e-129">This password is required when creating a certificate signed by this root certificate.</span></span>  
  
### <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a><span data-ttu-id="2c40e-130">Per creare un nuovo certificato firmato mediante un certificato dell'autorità radice</span><span class="sxs-lookup"><span data-stu-id="2c40e-130">To create a new certificate signed by a root authority certificate</span></span>  
  
1.  <span data-ttu-id="2c40e-131">Usare lo strumento MakeCert.exe con le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c40e-131">Use the MakeCert.exe tool with the following switches:</span></span>  
  
    1.  <span data-ttu-id="2c40e-132">`-sk` `subjectKey`.</span><span class="sxs-lookup"><span data-stu-id="2c40e-132">`-sk` `subjectKey`.</span></span> <span data-ttu-id="2c40e-133">La posizione del contenitore di chiavi del soggetto che contiene la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="2c40e-133">The location of the subject's key container that holds the private key.</span></span> <span data-ttu-id="2c40e-134">Se non esiste alcun contenitore di chiavi, ne viene creato uno.</span><span class="sxs-lookup"><span data-stu-id="2c40e-134">If a key container does not exist, one is created.</span></span> <span data-ttu-id="2c40e-135">Per impostazione predefinita, se le opzioni -sk o -sv non vengono usate, viene creato un contenitore di chiavi denominato JoeSoft.</span><span class="sxs-lookup"><span data-stu-id="2c40e-135">If neither of the -sk or -sv options is used, a key container called JoeSoft is created by default.</span></span>  
  
    2.  <span data-ttu-id="2c40e-136">`-n` `subjectName`.</span><span class="sxs-lookup"><span data-stu-id="2c40e-136">`-n` `subjectName`.</span></span> <span data-ttu-id="2c40e-137">Specifica il nome del soggetto.</span><span class="sxs-lookup"><span data-stu-id="2c40e-137">Specifies the subject name.</span></span> <span data-ttu-id="2c40e-138">La convenzione prevede l'inserimento del prefisso "CN = " per "Nome comune" prima del nome del soggetto.</span><span class="sxs-lookup"><span data-stu-id="2c40e-138">The convention is to prefix the subject name with "CN = " for "Common Name".</span></span>  
  
    3.  <span data-ttu-id="2c40e-139">`-iv` `issuerKeyFile`.</span><span class="sxs-lookup"><span data-stu-id="2c40e-139">`-iv` `issuerKeyFile`.</span></span> <span data-ttu-id="2c40e-140">Specifica il file della chiave privata dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="2c40e-140">Specifies the issuer's private key file.</span></span>  
  
    4.  <span data-ttu-id="2c40e-141">`-ic` `issuerCertFile`.</span><span class="sxs-lookup"><span data-stu-id="2c40e-141">`-ic` `issuerCertFile`.</span></span> <span data-ttu-id="2c40e-142">Specifica la posizione del certificato dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="2c40e-142">Specifies the location of the issuer's certificate.</span></span>  
  
     <span data-ttu-id="2c40e-143">Ad esempio, nel comando seguente viene creato un certificato firmato mediante il certificato dell'autorità radice `TempCA` con il nome del soggetto `"CN=SignedByCA"` usando la chiave privata dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="2c40e-143">For example, the following command creates a certificate signed by the `TempCA` root authority certificate with a subject name of `"CN=SignedByCA"` using the private key of the issuer.</span></span>  
  
    ```  
    makecert -sk SignedByCA -iv TempCA.pvk -n "CN=SignedByCA" -ic TempCA.cer SignedByCA.cer -sr currentuser -ss My  
    ```  
  
## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="2c40e-144">Installazione di un certificato nell'archivio dell'Autorità di certificazione radice attendibili</span><span class="sxs-lookup"><span data-stu-id="2c40e-144">Installing a Certificate in the Trusted Root Certification Authorities Store</span></span>  
 <span data-ttu-id="2c40e-145">Se è stato creato un certificato autofirmato, è possibile installarlo nell'archivio Autorità di certificazione radice attendibili.</span><span class="sxs-lookup"><span data-stu-id="2c40e-145">Once a self-signed certificate is created, you can install it in the Trusted Root Certification Authorities store.</span></span> <span data-ttu-id="2c40e-146">Qualsiasi certificato firmato con il certificato in questa fase viene considerato attendibile dal computer.</span><span class="sxs-lookup"><span data-stu-id="2c40e-146">Any certificates that are signed with the certificate at this point are trusted by the computer.</span></span> <span data-ttu-id="2c40e-147">Per questo motivo, eliminare il certificato dall'archivio quando non è più necessario.</span><span class="sxs-lookup"><span data-stu-id="2c40e-147">For this reason, delete the certificate from the store as soon as you no longer need it.</span></span> <span data-ttu-id="2c40e-148">Quando si elimina questo certificato dell'autorità radice, tutti gli altri certificati che sono stati firmati mediante tale certificato diventano non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="2c40e-148">When you delete this root authority certificate, all other certificates that signed with it become unauthorized.</span></span> <span data-ttu-id="2c40e-149">I certificati dell'autorità radice sono semplicemente un meccanismo che consente di definire come necessario un gruppo di certificati.</span><span class="sxs-lookup"><span data-stu-id="2c40e-149">Root authority certificates are simply a mechanism whereby a group of certificates can be scoped as necessary.</span></span> <span data-ttu-id="2c40e-150">Ad esempio, nelle applicazioni peer-to-peer in genere non è necessaria un'autorità radice perché l'identità di un individuo viene ritenuta attendibile semplicemente sulla base del certificato fornito.</span><span class="sxs-lookup"><span data-stu-id="2c40e-150">For example, in peer-to-peer applications, there is typically no need for a root authority because you simply trust the identity of an individual by its supplied certificate.</span></span>  
  
#### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a><span data-ttu-id="2c40e-151">Per installare un certificato autofirmato nell'Autorità di certificazione radice attendibili</span><span class="sxs-lookup"><span data-stu-id="2c40e-151">To install a self-signed certificate in the Trusted Root Certification Authorities</span></span>  
  
1.  <span data-ttu-id="2c40e-152">Aprire lo snap-in del certificato.</span><span class="sxs-lookup"><span data-stu-id="2c40e-152">Open the certificate snap-in.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="2c40e-153">[Procedura: visualizzare certificati con lo Snap-in MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="2c40e-153"> [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2.  <span data-ttu-id="2c40e-154">Aprire la cartella in cui archiviare il certificato, **Computer locale** o **Utente corrente**.</span><span class="sxs-lookup"><span data-stu-id="2c40e-154">Open the folder to store the certificate, either the **Local Computer** or the **Current User**.</span></span>  
  
3.  <span data-ttu-id="2c40e-155">Aprire la cartella **Autorità di certificazione radice attendibili** .</span><span class="sxs-lookup"><span data-stu-id="2c40e-155">Open the **Trusted Root Certification Authorities** folder.</span></span>  
  
4.  <span data-ttu-id="2c40e-156">Fare clic con il pulsante destro del mouse sulla cartella **Certificati** , scegliere **Tutte le attività**, quindi fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="2c40e-156">Right-click the **Certificates** folder and click **All Tasks**, then click **Import**.</span></span>  
  
5.  <span data-ttu-id="2c40e-157">Seguire le istruzioni della procedura guidata per importare TempCa.cer nell'archivio.</span><span class="sxs-lookup"><span data-stu-id="2c40e-157">Follow the on-screen wizard instructions to import the TempCa.cer into the store.</span></span>  
  
## <a name="using-certificates-with-wcf"></a><span data-ttu-id="2c40e-158">Uso dei certificati con WCF</span><span class="sxs-lookup"><span data-stu-id="2c40e-158">Using Certificates With WCF</span></span>  
 <span data-ttu-id="2c40e-159">Dopo avere impostato i certificati temporanei, è possibile usarli per sviluppare soluzioni WCF che specifichino i certificati come tipo di credenziali client.</span><span class="sxs-lookup"><span data-stu-id="2c40e-159">Once you have set up the temporary certificates, you can use them to develop WCF solutions that specify certificates as a client credential type.</span></span> <span data-ttu-id="2c40e-160">Nella configurazione XML seguente, ad esempio, vengono specificati la sicurezza dei messaggi e un certificato come tipo di credenziali client.</span><span class="sxs-lookup"><span data-stu-id="2c40e-160">For example, the following XML configuration specifies message security and a certificate as the client credential type.</span></span>  
  
#### <a name="to-specify-a-certificate-as-the-client-credential-type"></a><span data-ttu-id="2c40e-161">Per specificare un certificato come tipo di credenziali client</span><span class="sxs-lookup"><span data-stu-id="2c40e-161">To specify a certificate as the client credential type</span></span>  
  
-   <span data-ttu-id="2c40e-162">Nel file di configurazione di un servizio usare l'XML seguente per impostare la modalità di sicurezza su messaggio e il tipo di credenziali client su certificato.</span><span class="sxs-lookup"><span data-stu-id="2c40e-162">In the configuration file for a service, use the following XML to set the security mode to message, and the client credential type to certificate.</span></span>  
  
    ```xml  
    <bindings>       
      <wsHttpBinding>  
        <binding name="CertificateForClient">  
          <security>  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    ```  
  
 <span data-ttu-id="2c40e-163">Nel file di configurazione per un client, utilizzare il seguente codice XML per specificare che il certificato è disponibile nell'archivio dell'utente e può essere trovato cercando nel campo SubjectName per il valore "CohoWinery".</span><span class="sxs-lookup"><span data-stu-id="2c40e-163">In the configuration file for a client, use the following XML to specify that the certificate is found in the user’s store, and can be found by searching the SubjectName field for the value "CohoWinery."</span></span>  
  
```xml  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="CertForClient">  
      <clientCredentials>  
        <clientCertificate findValue="CohoWinery" x509FindType="FindBySubjectName" />  
       </clientCredentials>  
     </behavior>  
   </endpointBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="2c40e-164">Per altre informazioni sull'uso di certificati in WCF, vedere [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="2c40e-164">For more information about using certificates in WCF, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="2c40e-165">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2c40e-165">.NET Framework Security</span></span>  
 <span data-ttu-id="2c40e-166">Assicurarsi di eliminare qualsiasi certificato temporaneo dell'autorità di radice dalle cartelle **Autorità di certificazione radice attendibili** e **Personale** facendo clic con il pulsante destro del mouse sul certificato e scegliendo **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="2c40e-166">Be sure to delete any temporary root authority certificates from the **Trusted Root Certification Authorities** and **Personal** folders by right-clicking the certificate, then clicking **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c40e-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c40e-167">See Also</span></span>  
 [<span data-ttu-id="2c40e-168">Utilizzo dei certificati</span><span class="sxs-lookup"><span data-stu-id="2c40e-168">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="2c40e-169">Procedura: visualizzare certificati con lo Snap-in MMC</span><span class="sxs-lookup"><span data-stu-id="2c40e-169">How to: View Certificates with the MMC Snap-in</span></span>](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)  
 [<span data-ttu-id="2c40e-170">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="2c40e-170">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
