---
title: 'Procedura: configurare una porta con un certificato SSL'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
ms.openlocfilehash: 90d5424e12bb770dc3da85e1b2738206f4777c0c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185102"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a>Procedura: configurare una porta con un certificato SSL

Quando si crea un servizio Windows Communication Foundation <xref:System.ServiceModel.WSHttpBinding> (WCF) self-hosted con la classe che utilizza la sicurezza del trasporto, è inoltre necessario configurare una porta con un certificato X.509.When creating a self-hosted Windows Communication Foundation (WCF) service with the class that uses transport security, you must also configure a port with an X.509 certificate. Se non si intende creare un servizio indipendente, è possibile ospitare il servizio in Internet Information Services (IIS). Per ulteriori informazioni, vedere [Protezione del trasporto HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
 Per configurare una porta, lo strumento da usare dipende dal sistema operativo eseguito nel computer.  
  
 Se si esegue Windows Server 2003, utilizzare lo strumento HttpCfg.exe. In Windows Server 2003, questo strumento è installato. Per ulteriori informazioni, vedere [Cenni preliminari su Httpcfg](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)). Nella [documentazione relativa](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) agli Strumenti di supporto di Windows viene illustrata la sintassi dello strumento Httpcfg.exe.  
  
 Se si esegue Windows Vista, utilizzare lo strumento Netsh.exe già installato.
  
> [!NOTE]
> La modifica dei certificati archiviati nel computer richiede privilegi amministrativi.  
  
## <a name="determine-how-ports-are-configured"></a>Determinare la modalità di configurazione delle porte  
  
1. In Windows Server 2003 o Windows XP, utilizzare lo strumento HttpCfg.exe per visualizzare la configurazione della porta corrente, utilizzando le opzioni **query** e **ssl,** come illustrato nell'esempio seguente.  
  
    ```console
    httpcfg query ssl  
    ```  
  
2. In Windows Vista, utilizzare lo strumento Netsh.exe per visualizzare la configurazione della porta corrente, come illustrato nell'esempio seguente.  
  
    ```console  
    netsh http show sslcert  
    ```  
  
## <a name="get-a-certificates-thumbprint"></a>Ottenere l'identificazione personale di un certificatoGet a certificate's thumbprint  
  
1. Usare lo snap-in MMC Certificati per individuare un certificato X.509 che abbia come scopo previsto l'autenticazione client. Per altre informazioni, vedere [Procedura: Visualizzare certificati con lo snap-in MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
2. Accedere all'identificazione personale del certificato. Per altre informazioni, vedere [Procedura: recuperare l'identificazione personale di un certificato](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
3. Copiare l'identificazione personale del certificato in un editor di testo, ad esempio Blocco note.  
  
4. Rimuovere tutti gli spazi tra i caratteri esadecimali. Per eseguire questa operazione, è possibile usare la funzionalità Trova e sostituisci dell'editor di testo per sostituire ogni spazio con un carattere null.  
  
## <a name="bind-an-ssl-certificate-to-a-port-number"></a>Associare un certificato SSL a un numero di portaBind an SSL certificate to a port number  
  
1. In Windows Server 2003 o Windows XP, utilizzare lo strumento HttpCfg.exe in modalità "set" nell'archivio SSL (Secure Sockets Layer) per associare il certificato a un numero di porta. Lo strumento usa l'identificazione personale per identificare il certificato, come illustrato nell'esempio seguente.  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - L'opzione **-i** ha `IP``port` la sintassi di : e indica allo strumento di impostare il certificato sulla porta 8012 del computer. I quattro zero che precedono il numero possono essere anche sostituiti dall'indirizzo IP effettivo del computer.  
  
    - L'opzione **-h** specifica l'identificazione personale del certificato.  
  
2. In Windows Vista, utilizzare lo strumento Netsh.exe, come illustrato nell'esempio seguente.  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}
    ```  
  
    - Il parametro **certhash** consente di specificare l'identificazione personale del certificato.  
  
    - Il parametro **ipport** consente di specificare l'indirizzo IP e la porta e funziona come l'opzione **-i** dello strumento Httpcfg.exe descritto.  
  
    - Il parametro **appid** è un GUID che può essere utilizzato per identificare l'applicazione proprietaria.  
  
## <a name="bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a>Associare un certificato SSL a un numero di porta e supportare i certificati clientBind an SSL certificate to a port number and support client certificates  
  
1. In Windows Server 2003 o Windows XP, per supportare i client che eseguono l'autenticazione con certificati X.509 a livello di trasporto, seguire la procedura precedente ma passare un parametro della riga di comando aggiuntivo a HttpCfg.exe, come illustrato nell'esempio seguente.  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     L'opzione **-f** ha `n` la sintassi di dove n è un numero compreso tra 1 e 7. Un valore di 2, come mostrato nell'esempio precedente, abilita certificati client a livello di trasporto. Il valore 3 attiva i certificati client e associa tali certificati a un account Windows. Per il comportamento di altri valori, vedere la Guida di HttpCfg.exe.  
  
2. In Windows Vista, per supportare i client che eseguono l'autenticazione con certificati X.509 a livello di trasporto, seguire la procedura precedente, ma con un parametro aggiuntivo, come illustrato nell'esempio seguente.  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
## <a name="delete-an-ssl-certificate-from-a-port-number"></a>Eliminare un certificato SSL da un numero di portaDelete an SSL certificate from a port number  
  
1. Usare lo strumento HttpCfg.exe o Netsh.exe per visualizzare le porte e le identificazioni personali di tutti i binding nel computer. Per stampare le informazioni su disco, utilizzare il carattere di reindirizzamento ">", come illustrato nell'esempio seguente.  
  
    ```console  
    httpcfg query ssl>myMachinePorts.txt  
    ```
  
2. In Windows Server 2003 o Windows XP, utilizzare lo strumento HttpCfg.exe con le parole chiave **delete** e **ssl.** Utilizzare l'opzione **-i** per specificare il `IP`numero :`port` e l'opzione **-h** per specificare l'identificazione personale.  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. In Windows Vista, utilizzare lo strumento Netsh.exe, come illustrato nell'esempio seguente.  
  
    ```console  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a>Esempio  

 Nel codice seguente viene illustrato come creare un servizio indipendente usando la classe <xref:System.ServiceModel.WSHttpBinding> per la protezione del trasporto. Quando si crea un'applicazione, specificare il numero di porta nell'indirizzo.  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Protezione del trasporto HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
