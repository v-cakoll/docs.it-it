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
ms.openlocfilehash: 1ea7680d092a4270b8c0969c50db8accf7c23d49
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75963304"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a>Procedura: configurare una porta con un certificato SSL
Quando si crea un servizio self-hosted Windows Communication Foundation (WCF) con la classe <xref:System.ServiceModel.WSHttpBinding> che utilizza la sicurezza del trasporto, è inoltre necessario configurare una porta con un certificato X. 509. Se non si intende creare un servizio indipendente, è possibile ospitare il servizio in Internet Information Services (IIS). Per ulteriori informazioni, vedere la pagina relativa alla [sicurezza del trasporto http](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
 Per configurare una porta, lo strumento da usare dipende dal sistema operativo eseguito nel computer.  
  
 Se si esegue Windows Server 2003 o [!INCLUDE[wxp](../../../../includes/wxp-md.md)], usare lo strumento HttpCfg. exe. Con Windows Server 2003, questo strumento è installato. Con [!INCLUDE[wxp](../../../../includes/wxp-md.md)]è possibile scaricare lo strumento con gli [strumenti di supporto di Windows XP Service Pack 2](https://go.microsoft.com/fwlink/?LinkId=88606). Per ulteriori informazioni, vedere [Cenni preliminari su HttpCfg](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)). La [documentazione relativa agli strumenti di supporto di Windows](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) illustra la sintassi dello strumento HttpCfg. exe.  
  
 Se si esegue Windows Vista, utilizzare lo strumento Netsh. exe già installato.  
  
 In questo argomento viene descritto come eseguire diverse procedure:  
  
- Determinazione della configurazione corrente delle porte di un computer  
  
- Acquisizione dell'identificazione personale (necessaria per le due procedure seguenti) di un certificato  
  
- Binding di un certificato SSL alla configurazione di una porta  
  
- Binding di un certificato SSL alla configurazione di una porta e supporto di certificati client  
  
- Eliminazione di un certificato SSL da un numero di porta  
  
 Si noti che la modifica dei certificati archiviati nel computer richiede privilegi di amministrazione.  
  
### <a name="to-determine-how-ports-are-configured"></a>Per determinare la configurazione delle porte  
  
1. In Windows Server 2003 o [!INCLUDE[wxp](../../../../includes/wxp-md.md)]usare lo strumento HttpCfg. exe per visualizzare la configurazione corrente delle porte, usando le opzioni **query** e **SSL** , come illustrato nell'esempio seguente.  
  
    ```console
    httpcfg query ssl  
    ```  
  
2. In Windows Vista, utilizzare lo strumento Netsh. exe per visualizzare la configurazione della porta corrente, come illustrato nell'esempio seguente.  
  
    ```console  
    netsh http show sslcert  
    ```  
  
### <a name="to-get-a-certificates-thumbprint"></a>Per ottenere l'identificazione personale di un certificato  
  
1. Usare lo snap-in MMC Certificati per individuare un certificato X.509 che abbia come scopo previsto l'autenticazione client. Per altre informazioni, vedere [Procedura: visualizzare certificati con lo snap-in MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
2. Accedere all'identificazione personale del certificato. Per altre informazioni, vedere [Procedura: recuperare l'identificazione personale di un certificato](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
3. Copiare l'identificazione personale del certificato in un editor di testo, ad esempio Blocco note.  
  
4. Rimuovere tutti gli spazi tra i caratteri esadecimali. Per eseguire questa operazione, è possibile usare la funzionalità Trova e sostituisci dell'editor di testo per sostituire ogni spazio con un carattere null.  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number"></a>Per associare un certificato SSL a un numero di porta  
  
1. In Windows Server 2003 o [!INCLUDE[wxp](../../../../includes/wxp-md.md)]usare lo strumento HttpCfg. exe in modalità "set" nell'archivio Secure Sockets Layer (SSL) per associare il certificato a un numero di porta. Lo strumento usa l'identificazione personale per identificare il certificato, come illustrato nell'esempio seguente.  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - L'opzione **-i** presenta la sintassi di `IP`:`port` e indica allo strumento di impostare il certificato sulla porta 8012 del computer. I quattro zero che precedono il numero possono essere anche sostituiti dall'indirizzo IP effettivo del computer.  
  
    - L'opzione **-h** specifica l'identificazione personale del certificato.  
  
2. In Windows Vista, utilizzare lo strumento Netsh. exe, come illustrato nell'esempio seguente.  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    - Il parametro **certhash** specifica l'identificazione personale del certificato.  
  
    - Il parametro **ipport** specifica l'indirizzo IP e la porta e funziona esattamente come l'opzione **-i** dello strumento HttpCfg. exe descritto.  
  
    - Il parametro **AppID** è un GUID che può essere usato per identificare l'applicazione proprietaria.  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a>Per associare un certificato SSL a un numero di porta e ai certificati client supportati  
  
1. In Windows Server 2003 o [!INCLUDE[wxp](../../../../includes/wxp-md.md)]per supportare i client che eseguono l'autenticazione con certificati X. 509 a livello di trasporto, attenersi alla procedura precedente, ma passare un parametro della riga di comando aggiuntivo a HttpCfg. exe, come illustrato nell'esempio seguente.  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     L'opzione **-f** presenta la sintassi di `n` dove n è un numero compreso tra 1 e 7. Un valore di 2, come mostrato nell'esempio precedente, abilita certificati client a livello di trasporto. Il valore 3 attiva i certificati client e associa tali certificati a un account Windows. Per il comportamento di altri valori, vedere la Guida di HttpCfg.exe.  
  
2. In Windows Vista, per supportare i client che eseguono l'autenticazione con certificati X. 509 a livello di trasporto, attenersi alla procedura precedente, ma con un parametro aggiuntivo, come illustrato nell'esempio seguente.  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
### <a name="to-delete-an-ssl-certificate-from-a-port-number"></a>Per eliminare un certificato SSL da un numero di porta  
  
1. Usare lo strumento HttpCfg.exe o Netsh.exe per visualizzare le porte e le identificazioni personali di tutti i binding nel computer. Per stampare le informazioni su disco, usare il carattere di reindirizzamento ">", come illustrato nell'esempio seguente.  
  
    ```console  
    httpcfg query ssl>myMachinePorts.txt  
    ```
  
2. In Windows Server 2003 o [!INCLUDE[wxp](../../../../includes/wxp-md.md)]usare lo strumento HttpCfg. exe con le parole chiave **Delete** e **SSL** . Usare l'opzione **-i** per specificare il numero di `IP`:`port` e l'opzione **-h** per specificare l'identificazione personale.  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. In Windows Vista, utilizzare lo strumento Netsh. exe, come illustrato nell'esempio seguente.  
  
    ```console  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene illustrato come creare un servizio indipendente usando la classe <xref:System.ServiceModel.WSHttpBinding> per la protezione del trasporto. Quando si crea un'applicazione, specificare il numero di porta nell'indirizzo.  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Sicurezza del trasporto HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
