---
title: 'Procedura: Rendere accessibili a WCF i certificati X.509'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- X.509 certificates [WCF]
- certificates [WCF], making X.509 certificates accessible to WCF
- X.509 certificates [WCF], making accessible to WCF
ms.assetid: a54e407c-c2b5-4319-a648-60e43413664b
ms.openlocfilehash: 85f572f021f1613e0a2bb70cc090f58d2833182e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219915"
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a>Procedura: Rendere accessibili a WCF i certificati X.509
Per rendere accessibile da Windows Communication Foundation (WCF) un certificato X.509, il codice dell'applicazione deve specificare il nome dell'archivio certificati e il percorso. In alcuni casi l'identità del processo deve avere accesso al file contenente la chiave privata associata al certificato X.509. Per ottenere la chiave privata associata con un certificato X.509 in un archivio certificati, WCF deve avere l'autorizzazione per eseguire questa operazione. Per impostazione predefinita solo il proprietario e l'account di sistema possono accedere alla chiave privata di un certificato.  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a>Per rendere accessibili a WCF i certificati X.509  
  
1.  Assegnare all'account con cui WCF viene eseguito l'accesso in lettura al file contenente la chiave privata associata al certificato X.509.  
  
    1.  Determinare se WCF richiede l'accesso in lettura alla chiave privata del certificato X.509.  
  
         Nella tabella seguente viene indicato dettagliatamente se una chiave privata deve essere disponibile in caso di utilizzo di un certificato X.509.  
  
        |Utilizzo di certificati X.509|Chiave privata|  
        |---------------------------|-----------------|  
        |Firma digitale di un messaggio SOAP in uscita.|Yes|  
        |Verifica della firma di un messaggio SOAP in arrivo.|No|  
        |Crittografia di un messaggio SOAP in uscita.|No|  
        |Decrittografia di un messaggio SOAP in arrivo.|Yes|  
  
    2.  Determinare il percorso e il nome dell'archivio certificati in cui è archiviato il certificato.  
  
         L'archivio certificati nel quale il certificato è archiviato è specificato nel codice dell'applicazione o nella configurazione. Nel codice seguente, ad esempio, viene specificato che il certificato si trova nell'archivio certificati `CurrentUser` denominato `My`.  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3.  Determinare dove la chiave privata per il certificato si trova nel computer usando il [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) dello strumento.  
  
         Il [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) strumento richiede che il nome dell'archivio certificati, percorso dell'archivio certificati e un valore che identifica in modo univoco il certificato. Lo strumento accetta il nome del soggetto del certificato o l'identificazione digitale come identificatore univoco. Per altre informazioni su come determinare l'identificazione personale per un certificato, vedere [come: Recuperare l'identificazione personale di un certificato](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
         Il codice seguente viene illustrato come utilizzare il [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) dello strumento per determinare la posizione della chiave privata per un certificato nel `My` archiviare in `CurrentUser` con l'identificazione personale di `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.  
  
        ```  
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4.  Determinare l'account di cui WCF è in esecuzione.  
  
         Nella tabella seguente illustra in dettaglio l'account con cui WCF è in esecuzione per un determinato scenario.  
  
        |Scenario|Identità del processo|  
        |--------------|----------------------|  
        |Client (console o applicazione Windows Form).|Utente attualmente connesso.|  
        |Servizio indipendente.|Utente attualmente connesso.|  
        |Servizio ospitato in IIS 6.0 ([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) o IIS 7.0 ([!INCLUDE[wv](../../../../includes/wv-md.md)]).|SERVIZIO DI RETE|  
        |Servizio ospitato in IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]).|Controllato dall'elemento `<processModel>` nel file Machine.config. L'account predefinito è ASPNET.|  
  
    5.  Concedere l'accesso in lettura al file che contiene la chiave privata per l'account di cui WCF è in esecuzione, mediante uno strumento quale icacls.exe.  
  
         Esempio di codice seguente consente di modificare l'elenco di controllo di accesso discrezionale (DACL) per il file specificato concedere la lettura di account di servizio di rete (: R) l'accesso al file.  
  
        ```  
        icacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /grant "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a>Vedere anche

- [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)
- [Procedura: Recuperare l'identificazione personale di un certificato](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
- [Utilizzo dei certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
