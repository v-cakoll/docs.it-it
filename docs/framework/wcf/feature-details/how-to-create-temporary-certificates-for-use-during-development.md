---
title: 'Procedura: creare certificati temporanei da usare durante lo sviluppo'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: ca495c23b30144013b8efe22b7bf6f3cf38b16cd
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44509947"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a>Procedura: creare certificati temporanei da usare durante lo sviluppo
Quando si sviluppa un servizio sicuro o un client che utilizza Windows Communication Foundation (WCF), è spesso necessario fornire un certificato X.509 da usare come credenziali. Il certificato in genere fa parte di una catena di certificati con autorità radice contenuta nell'archivio Autorità di certificazione radice attendibile del computer. La catena di certificati consente di definire l'ambito per un set di certificati quando in genere l'autorità radice è dell'organizzazione o dell'unità aziendale. Per emulare questo comportamento in fase di sviluppo, è possibile creare due certificati per soddisfare i requisiti di sicurezza. Il primo è un certificato autofirmato che si trova nell'archivio Autorità di certificazione radice attendibile, mentre il secondo certificato viene creato dal primo e si trova nell'archivio Personale del computer locale o dell'utente corrente. In questo argomento descrive i passaggi per creare questi due certificati mediante Powershell [New-SelfSignedCertificate)](https://docs.microsoft.com/en-us/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps) cmdlet.  
  
> [!IMPORTANT]
>  I certificati che il cmdlet New-SelfSignedCertificate genera vengono forniti solo a scopo di test. Quando si distribuisce un servizio o un client, assicurarsi di usare un certificato appropriato rilasciato da un'autorità di certificazione. Ciò potrebbe provenire da un server di certificazione di Windows Server all'interno dell'organizzazione o di terze parti.  
>   
>  Per impostazione predefinita, il [New-SelfSignedCertificate](https://docs.microsoft.com/en-us/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps) cmdlet consente di creare certificati autofirmati e questi certificati sono non sicuri. Inserire i certificati autofirmati in Autorità di certificazione radice attendibili store consente di creare un ambiente di sviluppo che simula più da vicino l'ambiente di distribuzione.  
  
 Per altre informazioni sulla creazione e utilizzo dei certificati, vedere [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md). Per altre informazioni sull'uso di un certificato come credenziale, vedere [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md). Per un'esercitazione sull'uso della tecnologia Microsoft Authenticode, vedere [Panoramica di Authenticode ed esercitazioni](https://go.microsoft.com/fwlink/?LinkId=88919).  
  
### <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a>Per creare un certificato dell'autorità radice autofirmato ed esportare la chiave privata  
  
Il comando seguente crea un certificato autofirmato con un nome soggetto "RootCA" nell'archivio utente corrente personale. 
```
PS $rootCert = New-SelfSignedCertificate -CertStoreLocation cert:\CurrentUser\My -DnsName "RootCA" -TextExtension @("1.3.6.1.4.1.311.21.10={text}1.3.6.1.5.5.7.3.1,1.3.6.1.5.5.7.3.2")
```
È necessario esportare il certificato in un file PFX in modo che possa essere importato da dove è necessario in un passaggio successivo. Quando si esporta un certificato con la chiave privata, è necessaria una password per proteggerla. Si salva la password in un `SecureString` e usare il [Export-PfxCertificate](https://docs.microsoft.com/en-us/powershell/module/pkiclient/export-pfxcertificate?view=win10-ps) cmdlet per esportare il certificato con la chiave privata associata a un file PFX. È inoltre salvare solo il certificato pubblico in un file CRT usando il [Export-Certificate](https://docs.microsoft.com/en-us/powershell/module/pkiclient/export-certificate?view=win10-ps) cmdlet.
```
PS [System.Security.SecureString]$rootcertPassword = ConvertTo-SecureString -String "password" -Force -AsPlainText
PS [String]$rootCertPath = Join-Path -Path 'cert:\CurrentUser\My\' -ChildPath "$($rootcert.Thumbprint)"
PS Export-PfxCertificate -Cert $rootCertPath -FilePath 'RootCA.pfx' -Password $rootcertPassword
PS Export-Certificate -Cert $rootCertPath -FilePath 'RootCA.crt'
```

### <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a>Per creare un nuovo certificato firmato mediante un certificato dell'autorità radice  
  
Il comando seguente crea un certificato firmato mediante il `RootCA` con un nome soggetto "SignedByRootCA" usando la chiave privata dell'autorità emittente.
```
PS $testCert = New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "SignedByRootCA" -KeyExportPolicy Exportable -KeyLength 2048 -KeyUsage DigitalSignature,KeyEncipherment -Signer $rootCert 
```
Allo stesso modo, si salva il certificato firmato con la chiave privata in un file PFX e solo la chiave pubblica in un file CRT.
```
PS [String]$testCertPath = Join-Path -Path 'cert:\LocalMachine\My\' -ChildPath "$($testCert.Thumbprint)"
PS Export-PfxCertificate -Cert $testCertPath -FilePath testcert.pfx -Password $rootcertPassword 
PS Export-Certificate -Cert $testCertPath -FilePath testcert.crt        
```
  
## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a>Installazione di un certificato nell'archivio dell'Autorità di certificazione radice attendibili  
 Se è stato creato un certificato autofirmato, è possibile installarlo nell'archivio Autorità di certificazione radice attendibili. Qualsiasi certificato firmato con il certificato in questa fase viene considerato attendibile dal computer. Per questo motivo, eliminare il certificato dall'archivio quando non è più necessario. Quando si elimina questo certificato dell'autorità radice, tutti gli altri certificati che sono stati firmati mediante tale certificato diventano non autorizzati. I certificati dell'autorità radice sono semplicemente un meccanismo che consente di definire come necessario un gruppo di certificati. Ad esempio, nelle applicazioni peer-to-peer in genere non è necessaria un'autorità radice perché l'identità di un individuo viene ritenuta attendibile semplicemente sulla base del certificato fornito.  
  
#### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a>Per installare un certificato autofirmato nell'Autorità di certificazione radice attendibili  
  
1.  Aprire lo snap-in del certificato. Per altre informazioni, vedere [Procedura: visualizzare certificati con lo snap-in MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
2.  Aprire la cartella in cui archiviare il certificato, **Computer locale** o **Utente corrente**.  
  
3.  Aprire la cartella **Autorità di certificazione radice attendibili** .  
  
4.  Fare clic con il pulsante destro del mouse sulla cartella **Certificati** , scegliere **Tutte le attività**, quindi fare clic su **Importa**.  
  
5.  Seguire le istruzioni della procedura guidata per importare TempCa.cer nell'archivio.  
  
## <a name="using-certificates-with-wcf"></a>Uso dei certificati con WCF  
 Dopo avere impostato i certificati temporanei, è possibile usarli per sviluppare soluzioni WCF che specifichino i certificati come tipo di credenziali client. Nella configurazione XML seguente, ad esempio, vengono specificati la sicurezza dei messaggi e un certificato come tipo di credenziali client.  
  
#### <a name="to-specify-a-certificate-as-the-client-credential-type"></a>Per specificare un certificato come tipo di credenziali client  
  
-   Nel file di configurazione di un servizio usare l'XML seguente per impostare la modalità di sicurezza su messaggio e il tipo di credenziali client su certificato.  
  
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
  
 Nel file di configurazione per un client, usare il seguente codice XML per specificare che il certificato è stato trovato nell'archivio dell'utente e che può essere trovato cercando il campo SubjectName per il valore "CohoWinery."  
  
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
  
 Per altre informazioni sull'uso di certificati in WCF, vedere [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Assicurarsi di eliminare qualsiasi certificato temporaneo dell'autorità di radice dalle cartelle **Autorità di certificazione radice attendibili** e **Personale** facendo clic con il pulsante destro del mouse sul certificato e scegliendo **Elimina**.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Procedura: Visualizzare certificati con lo snap-in MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)  
 [Protezione di servizi e client](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
