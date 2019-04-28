---
title: 'Procedura: Creare certificati temporanei da usare durante lo sviluppo'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: d45f18b0b8fe4e0cc9667091e166c80691faa2d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773295"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a><span data-ttu-id="43aff-102">Procedura: Creare certificati temporanei da usare durante lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="43aff-102">How to: Create Temporary Certificates for Use During Development</span></span>

<span data-ttu-id="43aff-103">Quando si sviluppa un servizio sicuro o un client che utilizza Windows Communication Foundation (WCF), è spesso necessario fornire un certificato X.509 da usare come credenziali.</span><span class="sxs-lookup"><span data-stu-id="43aff-103">When developing a secure service or client using Windows Communication Foundation (WCF), it is often necessary to supply an X.509 certificate to be used as a credential.</span></span> <span data-ttu-id="43aff-104">Il certificato in genere fa parte di una catena di certificati con autorità radice contenuta nell'archivio Autorità di certificazione radice attendibile del computer.</span><span class="sxs-lookup"><span data-stu-id="43aff-104">The certificate typically is part of a chain of certificates with a root authority found in the Trusted Root Certification Authorities store of the computer.</span></span> <span data-ttu-id="43aff-105">La catena di certificati consente di definire l'ambito per un set di certificati quando in genere l'autorità radice è dell'organizzazione o dell'unità aziendale.</span><span class="sxs-lookup"><span data-stu-id="43aff-105">Having a certificate chain enables you to scope a set of certificates where typically the root authority is from your organization or business unit.</span></span> <span data-ttu-id="43aff-106">Per emulare questo comportamento in fase di sviluppo, è possibile creare due certificati per soddisfare i requisiti di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="43aff-106">To emulate this at development time, you can create two certificates to satisfy the security requirements.</span></span> <span data-ttu-id="43aff-107">Il primo è un certificato autofirmato che si trova nell'archivio Autorità di certificazione radice attendibile, mentre il secondo certificato viene creato dal primo e si trova nell'archivio Personale del computer locale o dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="43aff-107">The first is a self-signed certificate that is placed in the Trusted Root Certification Authorities store, and the second certificate is created from the first and is placed in either the Personal store of the Local Machine location, or the Personal store of the Current User location.</span></span> <span data-ttu-id="43aff-108">In questo argomento descrive i passaggi per creare questi due certificati mediante Powershell [New-SelfSignedCertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="43aff-108">This topic walks through the steps to create these two certificates using the Powershell [New-SelfSignedCertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="43aff-109">I certificati che il cmdlet New-SelfSignedCertificate genera vengono forniti solo a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="43aff-109">The certificates that the New-SelfSignedCertificate cmdlet generates are provided for testing purposes only.</span></span> <span data-ttu-id="43aff-110">Quando si distribuisce un servizio o un client, assicurarsi di usare un certificato appropriato rilasciato da un'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="43aff-110">When deploying a service or client, be sure to use an appropriate certificate provided by a certification authority.</span></span> <span data-ttu-id="43aff-111">Ciò potrebbe provenire da un server di certificazione di Windows Server all'interno dell'organizzazione o di terze parti.</span><span class="sxs-lookup"><span data-stu-id="43aff-111">This could either be from a Windows Server certificate server in your organization or a third party.</span></span>
>
> <span data-ttu-id="43aff-112">Per impostazione predefinita, il [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet consente di creare certificati autofirmati e questi certificati sono non sicuri.</span><span class="sxs-lookup"><span data-stu-id="43aff-112">By default, the [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet creates certificates that are self-signed and these certificates are insecure.</span></span> <span data-ttu-id="43aff-113">Inserire i certificati autofirmati in Autorità di certificazione radice attendibili store consente di creare un ambiente di sviluppo che simula più da vicino l'ambiente di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="43aff-113">Placing the self-signed certificates in the Trusted Root Certification Authorities store enables you to create a development environment that more closely simulates your deployment environment.</span></span>

 <span data-ttu-id="43aff-114">Per altre informazioni sulla creazione e utilizzo dei certificati, vedere [Working with Certificates](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="43aff-114">For more information about creating and using certificates, see [Working with Certificates](working-with-certificates.md).</span></span> <span data-ttu-id="43aff-115">Per altre informazioni sull'uso di un certificato come credenziale, vedere [Securing Services and Clients](securing-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="43aff-115">For more information about using a certificate as a credential, see [Securing Services and Clients](securing-services-and-clients.md).</span></span> <span data-ttu-id="43aff-116">Per un'esercitazione sull'uso della tecnologia Microsoft Authenticode, vedere [Panoramica di Authenticode ed esercitazioni](https://go.microsoft.com/fwlink/?LinkId=88919).</span><span class="sxs-lookup"><span data-stu-id="43aff-116">For a tutorial about using Microsoft Authenticode technology, see [Authenticode Overviews and Tutorials](https://go.microsoft.com/fwlink/?LinkId=88919).</span></span>

## <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a><span data-ttu-id="43aff-117">Per creare un certificato dell'autorità radice autofirmato ed esportare la chiave privata</span><span class="sxs-lookup"><span data-stu-id="43aff-117">To create a self-signed root authority certificate and export the private key</span></span>

<span data-ttu-id="43aff-118">Il comando seguente crea un certificato autofirmato con un nome soggetto "RootCA" nell'archivio utente corrente personale.</span><span class="sxs-lookup"><span data-stu-id="43aff-118">The following command creates a self-signed certificate with a subject name of "RootCA" in the Current User Personal store.</span></span>

```powershell
PS $rootCert = New-SelfSignedCertificate -CertStoreLocation cert:\CurrentUser\My -DnsName "RootCA" -TextExtension @("1.3.6.1.4.1.311.21.10={text}1.3.6.1.5.5.7.3.1,1.3.6.1.5.5.7.3.2")
```

<span data-ttu-id="43aff-119">È necessario esportare il certificato in un file PFX in modo che possa essere importato da dove è necessario in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="43aff-119">We need to export the certificate to a PFX file so that it can be imported to where it's needed in a later step.</span></span> <span data-ttu-id="43aff-120">Quando si esporta un certificato con la chiave privata, è necessaria una password per proteggerla.</span><span class="sxs-lookup"><span data-stu-id="43aff-120">When exporting a certificate with the private key, a password is needed to protect it.</span></span> <span data-ttu-id="43aff-121">Si salva la password in un `SecureString` e usare il [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) cmdlet per esportare il certificato con la chiave privata associata a un file PFX.</span><span class="sxs-lookup"><span data-stu-id="43aff-121">We save the password in a `SecureString` and use the [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) cmdlet to export the certificate with the associated private key to a PFX file.</span></span> <span data-ttu-id="43aff-122">È inoltre salvare solo il certificato pubblico in un file CRT usando il [Export-Certificate](/powershell/module/pkiclient/export-certificate) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="43aff-122">We also save just the public certificate into a CRT file using the [Export-Certificate](/powershell/module/pkiclient/export-certificate) cmdlet.</span></span>

```powershell
PS [System.Security.SecureString]$rootcertPassword = ConvertTo-SecureString -String "password" -Force -AsPlainText
PS [String]$rootCertPath = Join-Path -Path 'cert:\CurrentUser\My\' -ChildPath "$($rootcert.Thumbprint)"
PS Export-PfxCertificate -Cert $rootCertPath -FilePath 'RootCA.pfx' -Password $rootcertPassword
PS Export-Certificate -Cert $rootCertPath -FilePath 'RootCA.crt'
```

## <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a><span data-ttu-id="43aff-123">Per creare un nuovo certificato firmato mediante un certificato dell'autorità radice</span><span class="sxs-lookup"><span data-stu-id="43aff-123">To create a new certificate signed by a root authority certificate</span></span>

<span data-ttu-id="43aff-124">Il comando seguente crea un certificato firmato mediante il `RootCA` con un nome soggetto "SignedByRootCA" usando la chiave privata dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="43aff-124">The following command creates a certificate signed by the `RootCA` with a subject name of "SignedByRootCA" using the private key of the issuer.</span></span>

```powershell
PS $testCert = New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "SignedByRootCA" -KeyExportPolicy Exportable -KeyLength 2048 -KeyUsage DigitalSignature,KeyEncipherment -Signer $rootCert
```

<span data-ttu-id="43aff-125">Allo stesso modo, si salva il certificato firmato con la chiave privata in un file PFX e solo la chiave pubblica in un file CRT.</span><span class="sxs-lookup"><span data-stu-id="43aff-125">Similarly, we save the signed certificate with private key into a PFX file and just the public key into a CRT file.</span></span>

```powershell
PS [String]$testCertPath = Join-Path -Path 'cert:\LocalMachine\My\' -ChildPath "$($testCert.Thumbprint)"
PS Export-PfxCertificate -Cert $testCertPath -FilePath testcert.pfx -Password $rootcertPassword
PS Export-Certificate -Cert $testCertPath -FilePath testcert.crt
```

## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="43aff-126">Installazione di un certificato nell'archivio dell'Autorità di certificazione radice attendibili</span><span class="sxs-lookup"><span data-stu-id="43aff-126">Installing a Certificate in the Trusted Root Certification Authorities Store</span></span>

<span data-ttu-id="43aff-127">Se è stato creato un certificato autofirmato, è possibile installarlo nell'archivio Autorità di certificazione radice attendibili.</span><span class="sxs-lookup"><span data-stu-id="43aff-127">Once a self-signed certificate is created, you can install it in the Trusted Root Certification Authorities store.</span></span> <span data-ttu-id="43aff-128">Qualsiasi certificato firmato con il certificato in questa fase viene considerato attendibile dal computer.</span><span class="sxs-lookup"><span data-stu-id="43aff-128">Any certificates that are signed with the certificate at this point are trusted by the computer.</span></span> <span data-ttu-id="43aff-129">Per questo motivo, eliminare il certificato dall'archivio quando non è più necessario.</span><span class="sxs-lookup"><span data-stu-id="43aff-129">For this reason, delete the certificate from the store as soon as you no longer need it.</span></span> <span data-ttu-id="43aff-130">Quando si elimina questo certificato dell'autorità radice, tutti gli altri certificati che sono stati firmati mediante tale certificato diventano non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="43aff-130">When you delete this root authority certificate, all other certificates that signed with it become unauthorized.</span></span> <span data-ttu-id="43aff-131">I certificati dell'autorità radice sono semplicemente un meccanismo che consente di definire come necessario un gruppo di certificati.</span><span class="sxs-lookup"><span data-stu-id="43aff-131">Root authority certificates are simply a mechanism whereby a group of certificates can be scoped as necessary.</span></span> <span data-ttu-id="43aff-132">Ad esempio, nelle applicazioni peer-to-peer in genere non è necessaria un'autorità radice perché l'identità di un individuo viene ritenuta attendibile semplicemente sulla base del certificato fornito.</span><span class="sxs-lookup"><span data-stu-id="43aff-132">For example, in peer-to-peer applications, there is typically no need for a root authority because you simply trust the identity of an individual by its supplied certificate.</span></span>

### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a><span data-ttu-id="43aff-133">Per installare un certificato autofirmato nell'Autorità di certificazione radice attendibili</span><span class="sxs-lookup"><span data-stu-id="43aff-133">To install a self-signed certificate in the Trusted Root Certification Authorities</span></span>

1. <span data-ttu-id="43aff-134">Aprire lo snap-in del certificato.</span><span class="sxs-lookup"><span data-stu-id="43aff-134">Open the certificate snap-in.</span></span> <span data-ttu-id="43aff-135">Per altre informazioni, vedere [Procedura: Visualizzare i certificati con lo Snap-in MMC](how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="43aff-135">For more information, see [How to: View Certificates with the MMC Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>

2. <span data-ttu-id="43aff-136">Aprire la cartella in cui archiviare il certificato, **Computer locale** o **Utente corrente**.</span><span class="sxs-lookup"><span data-stu-id="43aff-136">Open the folder to store the certificate, either the **Local Computer** or the **Current User**.</span></span>

3. <span data-ttu-id="43aff-137">Aprire la cartella **Autorità di certificazione radice attendibili** .</span><span class="sxs-lookup"><span data-stu-id="43aff-137">Open the **Trusted Root Certification Authorities** folder.</span></span>

4. <span data-ttu-id="43aff-138">Fare clic con il pulsante destro del mouse sulla cartella **Certificati** , scegliere **Tutte le attività**, quindi fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="43aff-138">Right-click the **Certificates** folder and click **All Tasks**, then click **Import**.</span></span>

5. <span data-ttu-id="43aff-139">Seguire la procedura guidata le istruzioni per importare il RootCA.pfx nell'archivio.</span><span class="sxs-lookup"><span data-stu-id="43aff-139">Follow the on-screen wizard instructions to import the RootCA.pfx into the store.</span></span>

## <a name="using-certificates-with-wcf"></a><span data-ttu-id="43aff-140">Utilizzo di certificati con WCF</span><span class="sxs-lookup"><span data-stu-id="43aff-140">Using certificates With WCF</span></span>

<span data-ttu-id="43aff-141">Dopo avere impostato i certificati temporanei, è possibile usarli per sviluppare soluzioni WCF che specifichino i certificati come tipo di credenziali client.</span><span class="sxs-lookup"><span data-stu-id="43aff-141">Once you have set up the temporary certificates, you can use them to develop WCF solutions that specify certificates as a client credential type.</span></span> <span data-ttu-id="43aff-142">Nella configurazione XML seguente, ad esempio, vengono specificati la sicurezza dei messaggi e un certificato come tipo di credenziali client.</span><span class="sxs-lookup"><span data-stu-id="43aff-142">For example, the following XML configuration specifies message security and a certificate as the client credential type.</span></span>

### <a name="to-specify-a-certificate-as-the-client-credential-type"></a><span data-ttu-id="43aff-143">Per specificare un certificato come tipo di credenziali client</span><span class="sxs-lookup"><span data-stu-id="43aff-143">To specify a certificate as the client credential type</span></span>

1. <span data-ttu-id="43aff-144">Nel file di configurazione di un servizio usare l'XML seguente per impostare la modalità di sicurezza su messaggio e il tipo di credenziali client su certificato.</span><span class="sxs-lookup"><span data-stu-id="43aff-144">In the configuration file for a service, use the following XML to set the security mode to message, and the client credential type to certificate.</span></span>

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

2. <span data-ttu-id="43aff-145">Nel file di configurazione per un client, usare il seguente codice XML per specificare che il certificato è stato trovato nell'archivio dell'utente e che può essere trovato cercando il campo SubjectName per il valore "CohoWinery."</span><span class="sxs-lookup"><span data-stu-id="43aff-145">In the configuration file for a client, use the following XML to specify that the certificate is found in the user’s store, and can be found by searching the SubjectName field for the value "CohoWinery."</span></span>

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

<span data-ttu-id="43aff-146">Per altre informazioni sull'uso di certificati in WCF, vedere [Working with Certificates](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="43aff-146">For more information about using certificates in WCF, see [Working with Certificates](working-with-certificates.md).</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="43aff-147">.NET Framework (sicurezza)</span><span class="sxs-lookup"><span data-stu-id="43aff-147">.NET Framework security</span></span>

<span data-ttu-id="43aff-148">Assicurarsi di eliminare qualsiasi certificato temporaneo dell'autorità di radice dalle cartelle **Autorità di certificazione radice attendibili** e **Personale** facendo clic con il pulsante destro del mouse sul certificato e scegliendo **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="43aff-148">Be sure to delete any temporary root authority certificates from the **Trusted Root Certification Authorities** and **Personal** folders by right-clicking the certificate, then clicking **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="43aff-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43aff-149">See also</span></span>

- [<span data-ttu-id="43aff-150">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="43aff-150">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="43aff-151">Procedura: Visualizzare i certificati con lo Snap-in MMC</span><span class="sxs-lookup"><span data-stu-id="43aff-151">How to: View Certificates with the MMC Snap-in</span></span>](how-to-view-certificates-with-the-mmc-snap-in.md)
- [<span data-ttu-id="43aff-152">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="43aff-152">Securing Services and Clients</span></span>](securing-services-and-clients.md)
