---
title: 'Procedura: crittografare gli elementi XML con certificati X.509'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET Framework], X.509 certificates
- cryptography [.NET Framework], X.509 certificates
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: 761f1c66-631c-47af-aa86-ad9c50cfa453
ms.openlocfilehash: 9cdd8e52be11eeba86ec406510f40f1a08809ff8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84277219"
---
# <a name="how-to-encrypt-xml-elements-with-x509-certificates"></a>Procedura: crittografare gli elementi XML con certificati X.509
È possibile usare le classi dello spazio dei nomi <xref:System.Security.Cryptography.Xml> per crittografare un elemento all'interno di un documento XML.  La crittografia XML consente di scambiare o archiviare dati XML crittografati in modo standard, garantendo un'adeguata protezione dei dati da letture non autorizzate.  Per ulteriori informazioni sullo standard di crittografia XML, vedere la specifica World Wide Web Consortium (W3C) per la crittografia XML disponibile all'indirizzo <https://www.w3.org/TR/xmldsig-core/> .  
  
 È possibile usare la crittografia XML per sostituire qualsiasi elemento o documento XML con un elemento <`EncryptedData`> contenente i dati XML crittografati. Nell'elemento <`EncryptedData`> possono essere inclusi sottoelementi in cui sono incluse informazioni sulle chiavi e sui processi usati durante la crittografia.  La crittografia XML consente a un documento di contenere più elementi crittografati e consente a un elemento di essere crittografato più volte.  L'esempio di codice relativo a questa procedura illustra come creare un elemento <`EncryptedData`> insieme a diversi altri sottoelementi utilizzabili in un secondo momento durante la decrittografia.  
  
 Questo esempio crittografa un elemento XML mediante due chiavi. Genera un certificato X.509 di test usando lo [Strumento di creazione dei certificati (Makecert.exe)](/windows/desktop/SecCrypto/makecert) e lo salva in un archivio certificati. Questo esempio richiama il certificato a livello di codice e lo usa per crittografare un elemento XML mediante il metodo <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A>. Internamente, il metodo <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> crea una chiave di sessione separata e la usa per crittografare il documento XML. La chiave di sessione viene crittografata da questo metodo e salvata insieme ai dati XML crittografati all'interno di un nuovo elemento <`EncryptedData`>.  
  
 Per decrittografare l'elemento XML, chiamare semplicemente il metodo <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>, che richiama automaticamente il certificato X.509 dall'archivio ed esegue la descrizione necessaria.  Per altre informazioni su come decrittografare un elemento XML che era stato crittografato tramite questa procedura, vedere [Procedura: Decrittografare gli elementi XML con certificati X.509](how-to-decrypt-xml-elements-with-x-509-certificates.md).  
  
 Questo esempio è adatto per situazioni in cui più applicazioni devono condividere dati crittografati o in cui un'applicazione deve salvare dati crittografati tra un'esecuzione e l'altra.  
  
### <a name="to-encrypt-an-xml-element-with-an-x509-certificate"></a>Per crittografare un elemento XML con un certificato X.509  
  
1. Usare lo [Strumento di creazione dei certificati (Makecert.exe)](/windows/desktop/SecCrypto/makecert) per generare un certificato X.509 di test e inserirlo nell'archivio utente locale. Si deve generare una chiave di scambio e si deve rendere esportabile la chiave. Eseguire il comando seguente:  
  
    ```console  
    makecert -r -pe -n "CN=XML_ENC_TEST_CERT" -b 01/01/2005 -e 01/01/2010 -sky exchange -ss my  
    ```  
  
2. Creare un oggetto <xref:System.Security.Cryptography.X509Certificates.X509Store> e inizializzarlo per aprire l'archivio utente corrente.  
  
     [!code-csharp[HowToEncryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#2)]  
  
3. Aprire l'archivio in modalità di sola lettura.  
  
     [!code-csharp[HowToEncryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#3)]  
  
4. Inizializzare un <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> con tutti i certificati dell'archivio.  
  
     [!code-csharp[HowToEncryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#4)]  
  
5. Enumerare i certificati dell'archivio e trovare il certificato con il nome appropriato.  In questo esempio il certificato è denominato `"CN=XML_ENC_TEST_CERT"`.  
  
     [!code-csharp[HowToEncryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#5)]  
  
6. Chiudere l'archivio dopo l'individuazione del certificato.  
  
     [!code-csharp[HowToEncryptXMLElementX509#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementX509#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#6)]  
  
7. Creare un oggetto <xref:System.Xml.XmlDocument> caricando un file XML dal disco.  L'oggetto <xref:System.Xml.XmlDocument> contiene l'elemento XML da crittografare.  
  
     [!code-csharp[HowToEncryptXMLElementX509#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementX509#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#7)]  
  
8. Individuare l'elemento specificato nell'oggetto <xref:System.Xml.XmlDocument> e creare un nuovo oggetto <xref:System.Xml.XmlElement> per rappresentare l'elemento che si vuole crittografare.  In questo esempio l'elemento `"creditcard"` è crittografato.  
  
     [!code-csharp[HowToEncryptXMLElementX509#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementX509#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#8)]  
  
9. Creare una nuova istanza della classe <xref:System.Security.Cryptography.Xml.EncryptedXml> e usarla per crittografare l'elemento specificato mediante il certificato X.509.  Il metodo <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> restituisce l'elemento crittografato come un oggetto <xref:System.Security.Cryptography.Xml.EncryptedData>.  
  
     [!code-csharp[HowToEncryptXMLElementX509#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementX509#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#9)]  
  
10. Sostituire l'elemento dall'oggetto <xref:System.Xml.XmlDocument> originale con l'elemento <xref:System.Security.Cryptography.Xml.EncryptedData>.  
  
     [!code-csharp[HowToEncryptXMLElementX509#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementX509#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#10)]  
  
11. Salvare l'oggetto <xref:System.Xml.XmlDocument>.  
  
     [!code-csharp[HowToEncryptXMLElementX509#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementX509#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#11)]  
  
## <a name="example"></a>Esempio  
 Questo esempio presuppone che sia presente un file denominato `"test.xml"` nella stessa directory del programma compilato  e che `"test.xml"` contenga un elemento `"creditcard"`.  È possibile inserire il codice XML seguente in un file denominato `test.xml` e usarlo con questo esempio.  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- Per compilare questo esempio, è necessario includere un riferimento a `System.Security.dll`.  
  
- Includere gli spazi dei nomi seguenti: <xref:System.Xml>, <xref:System.Security.Cryptography> e <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Il certificato X.509 usato in questo esempio è solo a scopo di test.  Le applicazioni devono usare un certificato X.509 generato da un'autorità di certificazione attendibile o usare un certificato generato dal server di certificazione Microsoft Windows.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.Cryptography.Xml>
- [Procedura: decrittografare gli elementi XML con certificati X.509](how-to-decrypt-xml-elements-with-x-509-certificates.md)
