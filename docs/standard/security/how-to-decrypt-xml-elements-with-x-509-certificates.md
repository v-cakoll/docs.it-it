---
title: 'Procedura: Decrittografare gli elementi XML con certificati X.509'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- decryption
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: bd015722-d88d-408d-8ca8-e4e475c441ed
ms.openlocfilehash: 46fbefbf7a427ec0d60a34ecc2166f8499d08575
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708888"
---
# <a name="how-to-decrypt-xml-elements-with-x509-certificates"></a>Procedura: Decrittografare gli elementi XML con certificati X.509
È possibile usare le classi dello spazio dei nomi <xref:System.Security.Cryptography.Xml> per crittografare e decrittografare un elemento all'interno di un documento XML.  La crittografia XML consente di scambiare o archiviare dati XML crittografati in modo standard, garantendo un'adeguata protezione dei dati da letture non autorizzate.  Per ulteriori informazioni sullo standard di crittografia XML, vedere la specifica World Wide Web Consortium (W3C) per la crittografia XML disponibile in <https://www.w3.org/TR/xmldsig-core/>.  
  
 Questo esempio decrittografa un elemento XML crittografato usando i metodi descritti in [procedura: crittografare gli elementi XML con certificati X. 509](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md).  Trova un elemento <`EncryptedData`>, decrittografa l'elemento e quindi sostituisce l'elemento con l'elemento XML originale in testo non crittografato.  
  
 L'esempio di codice in questa procedura decrittografa un elemento XML usando un certificato X.509 dall'archivio certificati locale dell'account utente corrente.  Nell'esempio viene utilizzato il metodo <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> per recuperare automaticamente il certificato X. 509 e decrittografare una chiave di sessione archiviata nell'elemento <`EncryptedKey`> dell'elemento <`EncryptedData`>.  Il metodo <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> usa quindi automaticamente la chiave della sessione per decrittografare l'elemento XML.  
  
 Questo esempio è adatto per situazioni in cui più applicazioni devono condividere dati crittografati o in cui un'applicazione deve salvare dati crittografati tra un'esecuzione e l'altra.  
  
### <a name="to-decrypt-an-xml-element-with-an-x509-certificate"></a>Per decrittografare un elemento XML con un certificato X.509  
  
1. Creare un oggetto <xref:System.Xml.XmlDocument> caricando un file XML dal disco.  L'oggetto <xref:System.Xml.XmlDocument> contiene l'elemento XML da decrittografare.  
  
     [!code-csharp[HowToDecryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#2)]  
  
2. Creare un nuovo oggetto <xref:System.Security.Cryptography.Xml.EncryptedXml> passando l'oggetto <xref:System.Xml.XmlDocument> al costruttore.  
  
     [!code-csharp[HowToDecryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#3)]  
  
3. Decrittografare il documento XML usando il metodo <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>.  
  
     [!code-csharp[HowToDecryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToDecryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#4)]  
  
4. Salvare l'oggetto <xref:System.Xml.XmlDocument>.  
  
     [!code-csharp[HowToDecryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#5)]  
  
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
  
 [!code-csharp[HowToDecryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- Per compilare questo esempio, è necessario includere un riferimento a `System.Security.dll`.  
  
- Includere gli spazi dei nomi seguenti: <xref:System.Xml>, <xref:System.Security.Cryptography> e <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Il certificato X.509 usato in questo esempio è solo a scopo di test.  Le applicazioni devono usare un certificato X.509 generato da un'autorità di certificazione attendibile o usare un certificato generato dal server di certificazione Microsoft Windows.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.Cryptography.Xml>
- [Procedura: Crittografare gli elementi XML con certificati X.509](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md)
