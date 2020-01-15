---
title: 'Procedura: creare certificati temporanei da usare durante lo sviluppo'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: 9e01ccb29ad017a2657ab08b54d7f01ef4564481
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964544"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a>Procedura: creare certificati temporanei da usare durante lo sviluppo

Quando si sviluppa un servizio o un client sicuro usando Windows Communication Foundation (WCF), spesso è necessario fornire un certificato X. 509 da usare come credenziale. Il certificato in genere fa parte di una catena di certificati con autorità radice contenuta nell'archivio Autorità di certificazione radice attendibile del computer. La catena di certificati consente di definire l'ambito per un set di certificati quando in genere l'autorità radice è dell'organizzazione o dell'unità aziendale. Per emulare questo comportamento in fase di sviluppo, è possibile creare due certificati per soddisfare i requisiti di sicurezza. Il primo è un certificato autofirmato che si trova nell'archivio Autorità di certificazione radice attendibile, mentre il secondo certificato viene creato dal primo e si trova nell'archivio Personale del computer locale o dell'utente corrente. Questo argomento illustra i passaggi per creare questi due certificati usando il cmdlet PowerShell [New-SelfSignedCertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) .

> [!IMPORTANT]
> I certificati generati dal cmdlet New-SelfSignedCertificate vengono forniti solo a scopo di test. Quando si distribuisce un servizio o un client, assicurarsi di usare un certificato appropriato rilasciato da un'autorità di certificazione. Questo può provenire da un server di certificazione Windows Server nell'organizzazione o da terze parti.
>
> Per impostazione predefinita, il cmdlet [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) crea certificati autofirmati e questi certificati non sono sicuri. Inserendo i certificati autofirmati nell'archivio Autorità di certificazione radice attendibili, è possibile creare un ambiente di sviluppo che simula in modo più accurato l'ambiente di distribuzione.

 Per ulteriori informazioni sulla creazione e sull'utilizzo di certificati, vedere [Working with Certificates](working-with-certificates.md). Per ulteriori informazioni sull'utilizzo di un certificato come credenziale, vedere [protezione di servizi e client](securing-services-and-clients.md). Per un'esercitazione sull'uso della tecnologia Microsoft Authenticode, vedere [Panoramica di Authenticode ed esercitazioni](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537360(v=vs.85)).

## <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a>Per creare un certificato dell'autorità radice autofirmato ed esportare la chiave privata

Il comando che segue crea un certificato autofirmato con un nome soggetto "RootCA" nell'archivio personale dell'utente corrente.

```powershell
$rootcert = New-SelfSignedCertificate -CertStoreLocation Cert:\CurrentUser\My -DnsName "RootCA" -TextExtension @("2.5.29.19={text}CA=true") -KeyUsage CertSign,CrlSign,DigitalSignature
```

È necessario esportare il certificato in un file PFX, in modo che possa essere importato nel punto in cui è necessario in un passaggio successivo. Quando si esporta un certificato con la chiave privata, per proteggerla è necessaria una password. La password viene salvata in una `SecureString` e si usa il cmdlet [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) per esportare il certificato con la chiave privata associata in un file PFX. Viene anche salvato solo il certificato pubblico in un file CRT usando il cmdlet [Export-Certificate](/powershell/module/pkiclient/export-certificate) .

```powershell
[System.Security.SecureString]$rootcertPassword = ConvertTo-SecureString -String "password" -Force -AsPlainText
[String]$rootCertPath = Join-Path -Path 'cert:\CurrentUser\My\' -ChildPath "$($rootcert.Thumbprint)"
Export-PfxCertificate -Cert $rootCertPath -FilePath 'RootCA.pfx' -Password $rootcertPassword
Export-Certificate -Cert $rootCertPath -FilePath 'RootCA.crt'
```

## <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a>Per creare un nuovo certificato firmato mediante un certificato dell'autorità radice

Il comando che segue crea un certificato firmato dal `RootCA` con un nome soggetto "SignedByRootCA" usando la chiave privata dell'autorità emittente.

```powershell
$testCert = New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "SignedByRootCA" -KeyExportPolicy Exportable -KeyLength 2048 -KeyUsage DigitalSignature,KeyEncipherment -Signer $rootCert
```

Analogamente, si salva il certificato firmato con la chiave privata in un file PFX e solo la chiave pubblica in un file CRT.

```powershell
[String]$testCertPath = Join-Path -Path 'cert:\LocalMachine\My\' -ChildPath "$($testCert.Thumbprint)"
Export-PfxCertificate -Cert $testCertPath -FilePath testcert.pfx -Password $rootcertPassword
Export-Certificate -Cert $testCertPath -FilePath testcert.crt
```

## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a>Installazione di un certificato nell'archivio dell'Autorità di certificazione radice attendibili

Se è stato creato un certificato autofirmato, è possibile installarlo nell'archivio Autorità di certificazione radice attendibili. Qualsiasi certificato firmato con il certificato in questa fase viene considerato attendibile dal computer. Per questo motivo, eliminare il certificato dall'archivio quando non è più necessario. Quando si elimina questo certificato dell'autorità radice, tutti gli altri certificati che sono stati firmati mediante tale certificato diventano non autorizzati. I certificati dell'autorità radice sono semplicemente un meccanismo che consente di definire come necessario un gruppo di certificati. Ad esempio, nelle applicazioni peer-to-peer in genere non è necessaria un'autorità radice perché l'identità di un individuo viene ritenuta attendibile semplicemente sulla base del certificato fornito.

### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a>Per installare un certificato autofirmato nell'Autorità di certificazione radice attendibili

1. Aprire lo snap-in del certificato. Per altre informazioni, vedere [Procedura: visualizzare certificati con lo snap-in MMC](how-to-view-certificates-with-the-mmc-snap-in.md).

2. Aprire la cartella in cui archiviare il certificato, **Computer locale** o **Utente corrente**.

3. Aprire la cartella **Autorità di certificazione radice attendibili** .

4. Fare clic con il pulsante destro del mouse sulla cartella **Certificati** , scegliere **Tutte le attività**, quindi fare clic su **Importa**.

5. Seguire le istruzioni visualizzate nella procedura guidata per importare il file RootCA. pfx nell'archivio.

## <a name="using-certificates-with-wcf"></a>Utilizzo di certificati con WCF

Dopo avere impostato i certificati temporanei, è possibile usarli per sviluppare soluzioni WCF che specifichino i certificati come tipo di credenziali client. Nella configurazione XML seguente, ad esempio, vengono specificati la sicurezza dei messaggi e un certificato come tipo di credenziali client.

### <a name="to-specify-a-certificate-as-the-client-credential-type"></a>Per specificare un certificato come tipo di credenziali client

1. Nel file di configurazione di un servizio usare l'XML seguente per impostare la modalità di sicurezza su messaggio e il tipo di credenziali client su certificato.

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

2. Nel file di configurazione per un client, usare il codice XML seguente per specificare che il certificato si trova nell'archivio dell'utente e può essere trovato cercando il valore "CohoWinery" nel campo SubjectName.

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

Per altre informazioni sull'uso di certificati in WCF, vedere [Working with Certificates](working-with-certificates.md).

## <a name="net-framework-security"></a>.NET Framework (sicurezza)

Assicurarsi di eliminare qualsiasi certificato temporaneo dell'autorità di radice dalle cartelle **Autorità di certificazione radice attendibili** e **Personale** facendo clic con il pulsante destro del mouse sul certificato e scegliendo **Elimina**.

## <a name="see-also"></a>Vedere anche

- [Uso di certificati](working-with-certificates.md)
- [Procedura: Visualizzare certificati con lo snap-in MMC](how-to-view-certificates-with-the-mmc-snap-in.md)
- [Securing Services and Clients](securing-services-and-clients.md)
