---
title: 'Procedura: creare certificati temporanei da usare durante lo sviluppo'
description: Informazioni su come usare un cmdlet di PowerShell per creare due certificati X. 509 temporanei da usare per lo sviluppo di un servizio o un client WCF sicuro.
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: 0a21548386639a9f6a8c8572e5d7928ffdb270d6
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247039"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a><span data-ttu-id="d0238-103">Procedura: creare certificati temporanei da usare durante lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="d0238-103">How to: Create Temporary Certificates for Use During Development</span></span>

<span data-ttu-id="d0238-104">Quando si sviluppa un servizio o un client sicuro usando Windows Communication Foundation (WCF), spesso è necessario fornire un certificato X. 509 da usare come credenziale.</span><span class="sxs-lookup"><span data-stu-id="d0238-104">When developing a secure service or client using Windows Communication Foundation (WCF), it is often necessary to supply an X.509 certificate to be used as a credential.</span></span> <span data-ttu-id="d0238-105">Il certificato in genere fa parte di una catena di certificati con autorità radice contenuta nell'archivio Autorità di certificazione radice attendibile del computer.</span><span class="sxs-lookup"><span data-stu-id="d0238-105">The certificate typically is part of a chain of certificates with a root authority found in the Trusted Root Certification Authorities store of the computer.</span></span> <span data-ttu-id="d0238-106">La catena di certificati consente di definire l'ambito per un set di certificati quando in genere l'autorità radice è dell'organizzazione o dell'unità aziendale.</span><span class="sxs-lookup"><span data-stu-id="d0238-106">Having a certificate chain enables you to scope a set of certificates where typically the root authority is from your organization or business unit.</span></span> <span data-ttu-id="d0238-107">Per emulare questo comportamento in fase di sviluppo, è possibile creare due certificati per soddisfare i requisiti di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d0238-107">To emulate this at development time, you can create two certificates to satisfy the security requirements.</span></span> <span data-ttu-id="d0238-108">Il primo è un certificato autofirmato che si trova nell'archivio Autorità di certificazione radice attendibile, mentre il secondo certificato viene creato dal primo e si trova nell'archivio Personale del computer locale o dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="d0238-108">The first is a self-signed certificate that is placed in the Trusted Root Certification Authorities store, and the second certificate is created from the first and is placed in either the Personal store of the Local Machine location, or the Personal store of the Current User location.</span></span> <span data-ttu-id="d0238-109">Questo argomento illustra i passaggi per creare questi due certificati usando il cmdlet PowerShell [New-SelfSignedCertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) .</span><span class="sxs-lookup"><span data-stu-id="d0238-109">This topic walks through the steps to create these two certificates using the Powershell [New-SelfSignedCertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0238-110">I certificati generati dal cmdlet New-SelfSignedCertificate vengono forniti solo a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="d0238-110">The certificates that the New-SelfSignedCertificate cmdlet generates are provided for testing purposes only.</span></span> <span data-ttu-id="d0238-111">Quando si distribuisce un servizio o un client, assicurarsi di usare un certificato appropriato rilasciato da un'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="d0238-111">When deploying a service or client, be sure to use an appropriate certificate provided by a certification authority.</span></span> <span data-ttu-id="d0238-112">Questo può provenire da un server di certificazione Windows Server nell'organizzazione o da terze parti.</span><span class="sxs-lookup"><span data-stu-id="d0238-112">This could either be from a Windows Server certificate server in your organization or a third party.</span></span>
>
> <span data-ttu-id="d0238-113">Per impostazione predefinita, il cmdlet [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) crea certificati autofirmati e questi certificati non sono sicuri.</span><span class="sxs-lookup"><span data-stu-id="d0238-113">By default, the [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet creates certificates that are self-signed and these certificates are insecure.</span></span> <span data-ttu-id="d0238-114">Inserendo i certificati autofirmati nell'archivio Autorità di certificazione radice attendibili, è possibile creare un ambiente di sviluppo che simula in modo più accurato l'ambiente di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d0238-114">Placing the self-signed certificates in the Trusted Root Certification Authorities store enables you to create a development environment that more closely simulates your deployment environment.</span></span>

 <span data-ttu-id="d0238-115">Per ulteriori informazioni sulla creazione e sull'utilizzo di certificati, vedere [Working with Certificates](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="d0238-115">For more information about creating and using certificates, see [Working with Certificates](working-with-certificates.md).</span></span> <span data-ttu-id="d0238-116">Per ulteriori informazioni sull'utilizzo di un certificato come credenziale, vedere [protezione di servizi e client](securing-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="d0238-116">For more information about using a certificate as a credential, see [Securing Services and Clients](securing-services-and-clients.md).</span></span> <span data-ttu-id="d0238-117">Per un'esercitazione sull'uso della tecnologia Microsoft Authenticode, vedere [Panoramica di Authenticode ed esercitazioni](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537360(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="d0238-117">For a tutorial about using Microsoft Authenticode technology, see [Authenticode Overviews and Tutorials](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537360(v=vs.85)).</span></span>

## <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a><span data-ttu-id="d0238-118">Per creare un certificato dell'autorità radice autofirmato ed esportare la chiave privata</span><span class="sxs-lookup"><span data-stu-id="d0238-118">To create a self-signed root authority certificate and export the private key</span></span>

<span data-ttu-id="d0238-119">Il comando che segue crea un certificato autofirmato con un nome soggetto "RootCA" nell'archivio personale dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="d0238-119">The following command creates a self-signed certificate with a subject name of "RootCA" in the Current User Personal store.</span></span>

```powershell
$rootcert = New-SelfSignedCertificate -CertStoreLocation Cert:\CurrentUser\My -DnsName "RootCA" -TextExtension @("2.5.29.19={text}CA=true") -KeyUsage CertSign,CrlSign,DigitalSignature
```

<span data-ttu-id="d0238-120">È necessario esportare il certificato in un file PFX, in modo che possa essere importato nel punto in cui è necessario in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="d0238-120">We need to export the certificate to a PFX file so that it can be imported to where it's needed in a later step.</span></span> <span data-ttu-id="d0238-121">Quando si esporta un certificato con la chiave privata, per proteggerla è necessaria una password.</span><span class="sxs-lookup"><span data-stu-id="d0238-121">When exporting a certificate with the private key, a password is needed to protect it.</span></span> <span data-ttu-id="d0238-122">La password viene salvata in un `SecureString` e viene usato il cmdlet [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) per esportare il certificato con la chiave privata associata in un file PFX.</span><span class="sxs-lookup"><span data-stu-id="d0238-122">We save the password in a `SecureString` and use the [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) cmdlet to export the certificate with the associated private key to a PFX file.</span></span> <span data-ttu-id="d0238-123">Viene anche salvato solo il certificato pubblico in un file CRT usando il cmdlet [Export-Certificate](/powershell/module/pkiclient/export-certificate) .</span><span class="sxs-lookup"><span data-stu-id="d0238-123">We also save just the public certificate into a CRT file using the [Export-Certificate](/powershell/module/pkiclient/export-certificate) cmdlet.</span></span>

```powershell
[System.Security.SecureString]$rootcertPassword = ConvertTo-SecureString -String "password" -Force -AsPlainText
[String]$rootCertPath = Join-Path -Path 'cert:\CurrentUser\My\' -ChildPath "$($rootcert.Thumbprint)"
Export-PfxCertificate -Cert $rootCertPath -FilePath 'RootCA.pfx' -Password $rootcertPassword
Export-Certificate -Cert $rootCertPath -FilePath 'RootCA.crt'
```

## <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a><span data-ttu-id="d0238-124">Per creare un nuovo certificato firmato mediante un certificato dell'autorità radice</span><span class="sxs-lookup"><span data-stu-id="d0238-124">To create a new certificate signed by a root authority certificate</span></span>

<span data-ttu-id="d0238-125">Il comando che segue crea un certificato firmato da `RootCA` con un nome soggetto "SignedByRootCA" usando la chiave privata dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="d0238-125">The following command creates a certificate signed by the `RootCA` with a subject name of "SignedByRootCA" using the private key of the issuer.</span></span>

```powershell
$testCert = New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "SignedByRootCA" -KeyExportPolicy Exportable -KeyLength 2048 -KeyUsage DigitalSignature,KeyEncipherment -Signer $rootCert
```

<span data-ttu-id="d0238-126">Analogamente, si salva il certificato firmato con la chiave privata in un file PFX e solo la chiave pubblica in un file CRT.</span><span class="sxs-lookup"><span data-stu-id="d0238-126">Similarly, we save the signed certificate with private key into a PFX file and just the public key into a CRT file.</span></span>

```powershell
[String]$testCertPath = Join-Path -Path 'cert:\LocalMachine\My\' -ChildPath "$($testCert.Thumbprint)"
Export-PfxCertificate -Cert $testCertPath -FilePath testcert.pfx -Password $rootcertPassword
Export-Certificate -Cert $testCertPath -FilePath testcert.crt
```

## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="d0238-127">Installazione di un certificato nell'archivio dell'Autorità di certificazione radice attendibili</span><span class="sxs-lookup"><span data-stu-id="d0238-127">Installing a Certificate in the Trusted Root Certification Authorities Store</span></span>

<span data-ttu-id="d0238-128">Se è stato creato un certificato autofirmato, è possibile installarlo nell'archivio Autorità di certificazione radice attendibili.</span><span class="sxs-lookup"><span data-stu-id="d0238-128">Once a self-signed certificate is created, you can install it in the Trusted Root Certification Authorities store.</span></span> <span data-ttu-id="d0238-129">Qualsiasi certificato firmato con il certificato in questa fase viene considerato attendibile dal computer.</span><span class="sxs-lookup"><span data-stu-id="d0238-129">Any certificates that are signed with the certificate at this point are trusted by the computer.</span></span> <span data-ttu-id="d0238-130">Per questo motivo, eliminare il certificato dall'archivio quando non è più necessario.</span><span class="sxs-lookup"><span data-stu-id="d0238-130">For this reason, delete the certificate from the store as soon as you no longer need it.</span></span> <span data-ttu-id="d0238-131">Quando si elimina questo certificato dell'autorità radice, tutti gli altri certificati che sono stati firmati mediante tale certificato diventano non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="d0238-131">When you delete this root authority certificate, all other certificates that signed with it become unauthorized.</span></span> <span data-ttu-id="d0238-132">I certificati dell'autorità radice sono semplicemente un meccanismo che consente di definire come necessario un gruppo di certificati.</span><span class="sxs-lookup"><span data-stu-id="d0238-132">Root authority certificates are simply a mechanism whereby a group of certificates can be scoped as necessary.</span></span> <span data-ttu-id="d0238-133">Ad esempio, nelle applicazioni peer-to-peer in genere non è necessaria un'autorità radice perché l'identità di un individuo viene ritenuta attendibile semplicemente sulla base del certificato fornito.</span><span class="sxs-lookup"><span data-stu-id="d0238-133">For example, in peer-to-peer applications, there is typically no need for a root authority because you simply trust the identity of an individual by its supplied certificate.</span></span>

### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a><span data-ttu-id="d0238-134">Per installare un certificato autofirmato nell'Autorità di certificazione radice attendibili</span><span class="sxs-lookup"><span data-stu-id="d0238-134">To install a self-signed certificate in the Trusted Root Certification Authorities</span></span>

1. <span data-ttu-id="d0238-135">Aprire lo snap-in del certificato.</span><span class="sxs-lookup"><span data-stu-id="d0238-135">Open the certificate snap-in.</span></span> <span data-ttu-id="d0238-136">Per altre informazioni, vedere [Procedura: Visualizzare certificati con lo snap-in MMC](how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="d0238-136">For more information, see [How to: View Certificates with the MMC Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>

2. <span data-ttu-id="d0238-137">Aprire la cartella in cui archiviare il certificato, **Computer locale** o **Utente corrente**.</span><span class="sxs-lookup"><span data-stu-id="d0238-137">Open the folder to store the certificate, either the **Local Computer** or the **Current User**.</span></span>

3. <span data-ttu-id="d0238-138">Aprire la cartella **Autorità di certificazione radice attendibili** .</span><span class="sxs-lookup"><span data-stu-id="d0238-138">Open the **Trusted Root Certification Authorities** folder.</span></span>

4. <span data-ttu-id="d0238-139">Fare clic con il pulsante destro del mouse sulla cartella **Certificati** , scegliere **Tutte le attività**, quindi fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="d0238-139">Right-click the **Certificates** folder and click **All Tasks**, then click **Import**.</span></span>

5. <span data-ttu-id="d0238-140">Seguire le istruzioni visualizzate nella procedura guidata per importare il file RootCA. pfx nell'archivio.</span><span class="sxs-lookup"><span data-stu-id="d0238-140">Follow the on-screen wizard instructions to import the RootCA.pfx into the store.</span></span>

## <a name="using-certificates-with-wcf"></a><span data-ttu-id="d0238-141">Utilizzo di certificati con WCF</span><span class="sxs-lookup"><span data-stu-id="d0238-141">Using certificates With WCF</span></span>

<span data-ttu-id="d0238-142">Dopo avere impostato i certificati temporanei, è possibile usarli per sviluppare soluzioni WCF che specifichino i certificati come tipo di credenziali client.</span><span class="sxs-lookup"><span data-stu-id="d0238-142">Once you have set up the temporary certificates, you can use them to develop WCF solutions that specify certificates as a client credential type.</span></span> <span data-ttu-id="d0238-143">Nella configurazione XML seguente, ad esempio, vengono specificati la sicurezza dei messaggi e un certificato come tipo di credenziali client.</span><span class="sxs-lookup"><span data-stu-id="d0238-143">For example, the following XML configuration specifies message security and a certificate as the client credential type.</span></span>

### <a name="to-specify-a-certificate-as-the-client-credential-type"></a><span data-ttu-id="d0238-144">Per specificare un certificato come tipo di credenziali client</span><span class="sxs-lookup"><span data-stu-id="d0238-144">To specify a certificate as the client credential type</span></span>

1. <span data-ttu-id="d0238-145">Nel file di configurazione di un servizio usare l'XML seguente per impostare la modalità di sicurezza su messaggio e il tipo di credenziali client su certificato.</span><span class="sxs-lookup"><span data-stu-id="d0238-145">In the configuration file for a service, use the following XML to set the security mode to message, and the client credential type to certificate.</span></span>

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

2. <span data-ttu-id="d0238-146">Nel file di configurazione per un client, usare il codice XML seguente per specificare che il certificato si trova nell'archivio dell'utente e può essere trovato cercando il valore "CohoWinery" nel campo SubjectName.</span><span class="sxs-lookup"><span data-stu-id="d0238-146">In the configuration file for a client, use the following XML to specify that the certificate is found in the user’s store, and can be found by searching the SubjectName field for the value "CohoWinery."</span></span>

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

<span data-ttu-id="d0238-147">Per altre informazioni sull'uso di certificati in WCF, vedere [Working with Certificates](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="d0238-147">For more information about using certificates in WCF, see [Working with Certificates](working-with-certificates.md).</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="d0238-148">.NET Framework (sicurezza)</span><span class="sxs-lookup"><span data-stu-id="d0238-148">.NET Framework security</span></span>

<span data-ttu-id="d0238-149">Assicurarsi di eliminare qualsiasi certificato temporaneo dell'autorità di radice dalle cartelle **Autorità di certificazione radice attendibili** e **Personale** facendo clic con il pulsante destro del mouse sul certificato e scegliendo **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="d0238-149">Be sure to delete any temporary root authority certificates from the **Trusted Root Certification Authorities** and **Personal** folders by right-clicking the certificate, then clicking **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0238-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0238-150">See also</span></span>

- [<span data-ttu-id="d0238-151">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="d0238-151">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="d0238-152">Procedura: visualizzare certificati con lo snap-in MMC</span><span class="sxs-lookup"><span data-stu-id="d0238-152">How to: View Certificates with the MMC Snap-in</span></span>](how-to-view-certificates-with-the-mmc-snap-in.md)
- [<span data-ttu-id="d0238-153">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="d0238-153">Securing Services and Clients</span></span>](securing-services-and-clients.md)
