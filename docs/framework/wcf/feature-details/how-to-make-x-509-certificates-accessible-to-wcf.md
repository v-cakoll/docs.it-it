---
title: 'Procedura: rendere accessibili a WCF i certificati X.509'
description: Informazioni su come rendere un certificato X. 509 accessibile a WCF. Il codice dell'applicazione deve specificare il nome e il percorso dell'archivio certificati. Potrebbero essere presenti altri requisiti.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- X.509 certificates [WCF]
- certificates [WCF], making X.509 certificates accessible to WCF
- X.509 certificates [WCF], making accessible to WCF
ms.assetid: a54e407c-c2b5-4319-a648-60e43413664b
ms.openlocfilehash: 5cc1118640bcf1262d88cb8cdb39939ae315cae3
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246870"
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a>Procedura: rendere accessibili a WCF i certificati X.509
Per rendere accessibile un certificato X. 509 a Windows Communication Foundation (WCF), il codice dell'applicazione deve specificare il nome e il percorso dell'archivio certificati. In alcuni casi l'identità del processo deve avere accesso al file contenente la chiave privata associata al certificato X.509. Per ottenere la chiave privata associata a un certificato X. 509 in un archivio certificati, WCF deve disporre delle autorizzazioni necessarie. Per impostazione predefinita solo il proprietario e l'account di sistema possono accedere alla chiave privata di un certificato.  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a>Per rendere accessibili a WCF i certificati X.509  
  
1. Assegnare all'account con cui WCF esegue l'accesso in lettura al file che contiene la chiave privata associata al certificato X. 509.  
  
    1. Determinare se WCF richiede l'accesso in lettura alla chiave privata per il certificato X. 509.  
  
         Nella tabella seguente viene indicato dettagliatamente se una chiave privata deve essere disponibile in caso di utilizzo di un certificato X.509.  
  
        |Utilizzo di certificati X.509|Chiave privata|  
        |---------------------------|-----------------|  
        |Firma digitale di un messaggio SOAP in uscita.|Sì|  
        |Verifica della firma di un messaggio SOAP in arrivo.|No|  
        |Crittografia di un messaggio SOAP in uscita.|No|  
        |Decrittografia di un messaggio SOAP in arrivo.|Sì|  
  
    2. Determinare il percorso e il nome dell'archivio certificati in cui è archiviato il certificato.  
  
         L'archivio certificati nel quale il certificato è archiviato è specificato nel codice dell'applicazione o nella configurazione. Nel codice seguente, ad esempio, viene specificato che il certificato si trova nell'archivio certificati `CurrentUser` denominato `My`.  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3. Determinare dove si trova la chiave privata per il certificato nel computer utilizzando lo strumento [FindPrivateKey](../samples/findprivatekey.md) .  
  
         Lo strumento [FindPrivateKey](../samples/findprivatekey.md) richiede il nome dell'archivio certificati, il percorso dell'archivio certificati e un elemento che identifica in modo univoco il certificato. Lo strumento accetta il nome del soggetto del certificato o l'identificazione digitale come identificatore univoco. Per altre informazioni su come determinare l'identificazione personale per un certificato, vedere [procedura: recuperare l'identificazione personale di un certificato](how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
         Nell'esempio di codice seguente viene usato lo strumento [FindPrivateKey](../samples/findprivatekey.md) per determinare il percorso della chiave privata per un certificato nell' `My` archivio in `CurrentUser` con un'identificazione personale di `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d` .  
  
        ```console
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4. Determinare l'account con cui viene eseguito WCF.  
  
         La tabella seguente illustra in dettaglio l'account con cui viene eseguito WCF per uno scenario specifico.  
  
        |Scenario|Identità del processo|  
        |--------------|----------------------|  
        |Client (console o applicazione Windows Form).|Utente attualmente connesso.|  
        |Servizio indipendente.|Utente attualmente connesso.|  
        |Servizio ospitato in IIS 6,0 (Windows Server 2003) o IIS 7,0 (Windows Vista).|NETWORK SERVICE|  
        |Servizio ospitato in IIS 5. X (Windows XP).|Controllato dall'elemento `<processModel>` nel file Machine.config. L'account predefinito è ASPNET.|  
  
    5. Concedere l'accesso in lettura al file che contiene la chiave privata all'account con cui viene eseguito WCF, usando uno strumento come icacls.exe.  
  
         Nell'esempio di codice seguente viene modificato l'elenco di controllo di accesso discrezionale (DACL) per il file specificato per concedere all'account del servizio di rete l'accesso in lettura (: R) al file.  
  
        ```console
        icacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /grant "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a>Vedere anche

- [FindPrivateKey](../samples/findprivatekey.md)
- [Procedura: recuperare l'identificazione personale di un certificato](how-to-retrieve-the-thumbprint-of-a-certificate.md)
- [Working with Certificates](working-with-certificates.md)
