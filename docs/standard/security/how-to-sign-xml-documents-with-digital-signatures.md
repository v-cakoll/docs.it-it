---
title: 'Procedura: firmare documenti XML con firme digitali'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signatures, XML signing
- System.Security.Cryptography.SignedXml class
- digital signatures, XML signing
- System.Security.Cryptography.RSACryptoServiceProvider class
- XML digital signatures
- XML signing
- signing XML
ms.assetid: 99692ac1-d8c9-42d7-b1bf-2737b01037e4
ms.openlocfilehash: 81fa5e4c503f26dc13758090f845fd8387287084
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84277180"
---
# <a name="how-to-sign-xml-documents-with-digital-signatures"></a>Procedura: firmare documenti XML con firme digitali
È possibile usare le classi dello spazio dei nomi <xref:System.Security.Cryptography.Xml> per firmare un documento XML o parte di esso con una firma digitale.  Le firme digitali XML (XMLDSIG) consentono di verificare che i dati non siano stati alterati dopo la firma.  Per ulteriori informazioni sullo standard XMLDSIG, vedere la pagina relativa all' [elaborazione e alla sintassi della firma XML](https://www.w3.org/TR/xmldsig-core/)del World Wide Web Consortium (W3C).  
  
 Nell'esempio di codice di questa procedura viene illustrato come firmare digitalmente un intero documento XML e come alleghi la firma al documento in un `Signature` elemento <>.  L'esempio crea una chiave di firma RSA, aggiunge la chiave a un contenitore di chiavi sicuro e usa quindi la chiave per firmare digitalmente un documento XML.  La chiave può successivamente essere recuperata per verificare la firma digitale XML oppure può essere usata per firmare un altro documento XML.  
  
 Per informazioni su come verificare una firma digitale XML creata con questa procedura, vedere [procedura: verificare le firme digitali dei documenti XML](how-to-verify-the-digital-signatures-of-xml-documents.md).  
  
### <a name="to-digitally-sign-an-xml-document"></a>Per firmare digitalmente un documento XML  
  
1. Creare un oggetto <xref:System.Security.Cryptography.CspParameters> e specificare il nome del contenitore di chiavi.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToSignXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#2)]  
  
2. Generare una chiave asimmetrica usando la classe <xref:System.Security.Cryptography.RSACryptoServiceProvider>.  La chiave viene salvata automaticamente nel contenitore di chiavi quando si passa l'oggetto <xref:System.Security.Cryptography.CspParameters> al costruttore della classe <xref:System.Security.Cryptography.RSACryptoServiceProvider>.  Questa chiave verrà usata per firmare il documento XML.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToSignXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#3)]  
  
3. Creare un oggetto <xref:System.Xml.XmlDocument> caricando un file XML dal disco.  L'oggetto <xref:System.Xml.XmlDocument> contiene l'elemento XML da crittografare.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToSignXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#4)]  
  
4. Creare un nuovo oggetto <xref:System.Security.Cryptography.Xml.SignedXml> e passare a esso l'oggetto <xref:System.Xml.XmlDocument>.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToSignXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#5)]  
  
5. Aggiungere la chiave di firma RSA all'oggetto <xref:System.Security.Cryptography.Xml.SignedXml>.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToSignXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#6)]  
  
6. Creare un oggetto <xref:System.Security.Cryptography.Xml.Reference> che descrive cosa firmare.  Per firmare l'intero documento, impostare la proprietà <xref:System.Security.Cryptography.Xml.Reference.Uri%2A> su `""`.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToSignXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#7)]  
  
7. Aggiungere un oggetto <xref:System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform> all'oggetto <xref:System.Security.Cryptography.Xml.Reference>.  Una trasformazione consente allo strumento di verifica di rappresentare i dati XML nello stesso modo usato da chi ha applicato la firma.  I dati XML possono essere rappresentati in modi diversi, pertanto questo passaggio è fondamentale per la verifica.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToSignXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#8)]  
  
8. Aggiungere l'oggetto <xref:System.Security.Cryptography.Xml.Reference> all'oggetto <xref:System.Security.Cryptography.Xml.SignedXml>.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#9)]
     [!code-vb[HowToSignXMLDocumentRSA#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#9)]  
  
9. Calcolare la firma chiamando il metodo <xref:System.Security.Cryptography.Xml.SignedXml.ComputeSignature%2A>.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#10)]
     [!code-vb[HowToSignXMLDocumentRSA#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#10)]  
  
10. Recuperare la rappresentazione XML della firma (un <`Signature` elemento>) e salvarla in un nuovo <xref:System.Xml.XmlElement> oggetto.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#11)]
     [!code-vb[HowToSignXMLDocumentRSA#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#11)]  
  
11. Aggiungere l'elemento all'oggetto <xref:System.Xml.XmlDocument>.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#12)]
     [!code-vb[HowToSignXMLDocumentRSA#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#12)]  
  
12. Salvare il documento.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#13)]
     [!code-vb[HowToSignXMLDocumentRSA#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#13)]  
  
## <a name="example"></a>Esempio  
 Questo esempio presuppone che sia presente un file denominato `test.xml` nella stessa directory del programma compilato  È possibile inserire il codice XML seguente in un file denominato `test.xml` e usarlo con questo esempio.  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToSignXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#1)]
 [!code-vb[HowToSignXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- Per compilare questo esempio, è necessario includere un riferimento a `System.Security.dll`.  
  
- Includere gli spazi dei nomi seguenti: <xref:System.Xml>, <xref:System.Security.Cryptography> e <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Non archiviare né trasferire mai in testo non crittografato la chiave privata di una coppia di chiavi asimmetriche.  Per ulteriori informazioni sulle chiavi crittografiche simmetriche e asimmetriche, vedere [generazione di chiavi per crittografia e decrittografia](generating-keys-for-encryption-and-decryption.md).  
  
 Non incorporare mai una chiave privata direttamente nel codice sorgente.  Le chiavi incorporate possono essere lette facilmente da un assembly tramite [Ildasm. exe (DISASSEMBLER il)](../../framework/tools/ildasm-exe-il-disassembler.md) oppure aprendo l'assembly in un editor di testo, ad esempio Blocco note.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.Cryptography.Xml>
- [Procedura: verificare le firme digitali dei documenti XML](how-to-verify-the-digital-signatures-of-xml-documents.md)
