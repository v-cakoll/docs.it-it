---
title: 'Procedura: rendere accessibili a WCF i certificati X.509'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- X.509 certificates [WCF]
- certificates [WCF], making X.509 certificates accessible to WCF
- X.509 certificates [WCF], making accessible to WCF
ms.assetid: a54e407c-c2b5-4319-a648-60e43413664b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b95ee7c28c67ff861dc401d1405306c78b9663de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a>Procedura: rendere accessibili a WCF i certificati X.509
Per rendere accessibile un certificato X.509 a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], è necessario che il codice dell'applicazione specifichi nome e percorso dell'archivio certificati. In alcuni casi l'identità del processo deve avere accesso al file contenente la chiave privata associata al certificato X.509. Per ottenere la chiave privata associata a un certificato X.509 contenuto in un archivio certificati, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] deve ricevere apposita autorizzazione. Per impostazione predefinita solo il proprietario e l'account di sistema possono accedere alla chiave privata di un certificato.  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a>Per rendere accessibili a WCF i certificati X.509  
  
1.  Concedere all'account di esecuzione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] l'accesso in lettura al file contenente la chiave privata associata al certificato X.509.  
  
    1.  Stabilire se per [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è necessario l'accesso in lettura alla chiave privata del certificato X.509.  
  
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
  
    3.  Determinare dove la chiave privata per il certificato si trova nel computer utilizzando il [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) strumento.  
  
         Il [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) strumento richiede il nome dell'archivio certificati, percorso dell'archivio certificati e un valore che identifica in modo univoco il certificato. Lo strumento accetta il nome del soggetto del certificato o l'identificazione digitale come identificatore univoco. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]come determinare l'identificazione personale di un certificato, vedere [procedura: recuperare l'identificazione personale del certificato](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
         Nell'esempio di codice viene illustrato come utilizzare il [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) strumento per determinare la posizione della chiave privata di un certificato nella `My` archiviare in `CurrentUser` con un'identificazione digitale di `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.  
  
        ```  
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4.  Determinare l'account di esecuzione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
         Nella tabella seguente viene dettagliato l'account nel quale [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è eseguito per un determinato scenario.  
  
        |Scenario|Identità del processo|  
        |--------------|----------------------|  
        |Client (console o applicazione Windows Form).|Utente attualmente connesso.|  
        |Servizio indipendente.|Utente attualmente connesso.|  
        |Servizio ospitato in IIS 6.0 ([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) o IIS 7.0 ([!INCLUDE[wv](../../../../includes/wv-md.md)]).|SERVIZIO DI RETE|  
        |Servizio ospitato in IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]).|Controllato dall'elemento `<processModel>` nel file Machine.config. L'account predefinito è ASPNET.|  
  
    5.  Concedere al file contenente la chiave privata l'accesso in lettura all'account di esecuzione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], utilizzando uno strumento come cacls.exe.  
  
         Nell'esempio di codice seguente viene modificato (/E) l'elenco di controllo di accesso (ACL) per il file specificato per concedere (/G) all'account NETWORK SERVICE l'accesso in lettura (:R) al file.  
  
        ```  
        cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a>Vedere anche  
 [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)  
 [Procedura: Recuperare l'identificazione personale di un certificato](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)  
 [Uso di certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
